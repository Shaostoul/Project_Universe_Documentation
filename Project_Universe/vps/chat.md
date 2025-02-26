TEST SUBSCRIPTION

subscription TestSubscription {
  messageAdded(roomName: "master") {
    sender
    text
    timestamp
  }
}

TEST MUTATION

mutation TestMutation {
  sendMessage(roomName: "master", text: "Hello from Playground!") {
    sender
    text
    timestamp
  }
}