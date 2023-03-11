## System Design

### Functional Requirements

1. Create Tweets (text, images, videos, etc)
2. View Timeline
3. Like tweets
4. Retweet / Quote Retweet
5. Follow others

### Non-Functional Requirements
1. Scalable & Efficient
2. High Availability

### Optional Requirements
1. Metrics and analytics
2. Notifications

### API
- Create Tweets

```graphql
createTweet(userID: String!, text: String!, mediaURL: String): bool
```

- View Timeline

```graphql
getTimeline(userID: String!): Tweet[]
```

- Like Tweet

```graphql
likeTweet(tweetID: String!): bool
unlikeTweet(tweetID: String!): bool
```

- Retweet

```graphql
retweet(tweetID: String!, text: String, mediaURL: String): bool
```

If `text` and `mediaURL` is provided than it is a Quote Retweet

- Follow others

```graphql
followUser(followerID: String!, followingID: String!): bool
unfollowUser(followerID: String!, followingID: String!): bool
```