# Project Universe Chat Setup (Redis + GraphQL Subscriptions)

**Date**: December 31, 2024  
**Context**: We have a Node.js-based chat server using Redis for PubSub with GraphQL Subscriptions, behind an Nginx reverse proxy on Debian.  

## Overview

1. **Redis** powers the PubSub layer (via `graphql-redis-subscriptions`).
2. **Node / Apollo Server** for GraphQL queries, mutations, and subscriptions.
3. **Nginx** reverse-proxies traffic from HTTPS (port 443) to Node (port 4000).
4. **WordPress** site on `shaostoul.com`; chat subdomain `chat.shaostoul.com` pointing to VPS.

## File Structure

```
shaostoul-chat/
├── schema.graphql # GraphQL schema definitions
├── schema.js # Reads schema.graphql -> typeDefs
├── resolvers.js # Contains RedisPubSub logic, subscription resolvers
├── server.js # Express + ApolloServer + SubscriptionServer setup
├── package.json # Node dependencies
└── 
```

## Key Points

1. **Redis**  
   - Installed via `sudo apt-get install redis-server`.
   - Service name often `redis-server.service` on Debian.

2. **graphql-redis-subscriptions**  
   - Provides a `RedisPubSub` class with `.asyncIterator()` for subscriptions.
   - Requires `ioredis` as a dependency.

3. **Nginx Config** (chat.shaostoul.com.conf):
   ```nginx
   server {
       listen 80;
       server_name chat.shaostoul.com;
       return 301 https://$host$request_uri;
   }

   server {
       listen 443 ssl http2;
       server_name chat.shaostoul.com;

       ssl_certificate /etc/letsencrypt/live/chat.shaostoul.com/fullchain.pem;
       ssl_certificate_key /etc/letsencrypt/live/chat.shaostoul.com/privkey.pem;
       include /etc/letsencrypt/options-ssl-nginx.conf;
       ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem;

       location / {
           proxy_pass http://127.0.0.1:4000;
           proxy_http_version 1.1;
           proxy_set_header Upgrade $http_upgrade;
           proxy_set_header Connection "upgrade";
           proxy_set_header Host $host;
       }
   }
```

4. **Chat Flow**
    
    - `sendMessage(roomName, text)` mutation updates an in-memory record and publishes to Redis.
    - `messageAdded(roomName)` subscription listens for messages on `MESSAGE_ADDED_<roomName>` channel.
    - The front-end (WordPress page or direct HTML snippet) points to `https://chat.shaostoul.com/graphql` for queries/mutations and `wss://chat.shaostoul.com/graphql` for subscriptions.
5. **PM2**
    
    - We typically keep the server running with PM2:
        
        ```bash
        pm2 start server.js --name shaostoul-chat
        pm2 logs shaostoul-chat
        pm2 restart shaostoul-chat
        pm2 save
        ```
        

## Testing

1. **GraphQL Playground** at `https://chat.shaostoul.com/graphql`
2. **Subscribe** in one tab:
    
    ```graphql
    subscription {
      messageAdded(roomName: "master") {
        sender
        text
        timestamp
      }
    }
    ```

3. **Send** a message in another tab:

```graphql
mutation {
	sendMessage(roomName: "master", text: "Hello from Playground!") {
		sender
		text
		timestamp
      }
    }
```

4. The subscription tab shows the new message in real time.

