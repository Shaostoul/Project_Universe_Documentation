# Adding User Accounts and Anonymous Chat

## Basic Approach
We want:
1. **Authenticated users** (via WordPress or a shared database).
2. **Anonymous** users who can still type (their name shows as "anon").

### 1. Authenticated Users
- If we have a WordPress site, we can store user info in the WP database. 
- The chat front end can pass a **JWT** or **session token** to the GraphQL server, letting the server know “this user is WordPressUser123.”
- Then in `sendMessage`, if a valid user is identified, use their actual name. If not, fallback to “anon.”

### 2. Anonymous
- If no credentials are provided, the `context` is `'anon'`.
- Example in `server.js` (Apollo context):
```js
  const apolloServer = new ApolloServer({
    schema,
    context: ({ req }) => {
      // Suppose we read a token from headers:
      const token = req.headers.authorization || '';
      // Validate token or query WP database
      const user = validateTokenOrGetUser(token) || { name: 'anon' };
      return { user };
    },
    // ...
  });
```

- Then in `resolvers.js`:
    
    ```js
    sendMessage: (_, { roomName, text }, context) => {
      const sender = context.user.name || 'anon';
      // ...
    }
    ```
    

### 3. WordPress Integration Example

- On the WP side, generate a short-lived JWT whenever a logged-in user loads the chat page.
- Pass it to the chat client’s JS code:
    
    ```js
    // front-end example
    fetch('https://shaostoul.com/get-chat-token').then(res => res.json()).then(data => {
      const token = data.token; // e.g., your WP site returns a JWT
      // use it in your GraphQL headers
      const httpLink = new HttpLink({
        uri: 'https://chat.shaostoul.com/graphql',
        headers: {
          authorization: token ? `Bearer ${token}` : ''
        }
      });
    });
    ```
    
- On the server, decode the JWT to get the user’s WP ID or username.

### 4. Distinguishing Anonymous

- If there’s **no** valid token or it fails to decode, set `context.user = { name: 'anon' }`.
- This approach allows both real WP users and anonymous users to type messages in the same system.

### Conclusion

By combining the **WordPress-based authentication** (for registered users) with a **fallback to “anon”** if no valid credentials are provided, you can accommodate both **authenticated** and **anonymous** participants in the same chat system. The GraphQL server’s **context** determines which mode to use at runtime, and your subscription/mutation resolvers then label each message sender accordingly.

This approach keeps your chat flexible—letting official user accounts (from WordPress or elsewhere) participate with unique names, while also allowing anyone else to join as “anon” without a full login.