# Twitter API Integration with Go

This is a Go application that interacts with the Twitter API to post tweets. The application sets up a local HTTP server and provides an API endpoint (`/tweet`) that accepts POST requests. You can use tools like Postman to send a request to this endpoint and post a tweet on Twitter.

## Features

- Post a tweet to Twitter using OAuth 1.0a for authentication.
- Load API credentials from a `.env` file.
- Send a POST request to a Go server to publish a tweet.

## Prerequisites

To run this application, you need to have the following:

- Go (Golang) installed on your machine.
- A Twitter Developer account with API keys and access tokens.
- [Postman](https://www.postman.com/downloads/) or cURL for sending POST requests.
- A `.env` file for storing your Twitter API credentials.

## Twitter API Credentials

You will need the following credentials from the [Twitter Developer Portal](https://developer.twitter.com/):

- **Consumer Key** (`CONSUMER_KEY`)
- **Consumer Secret** (`CONSUMER_SECRET`)
- **Access Token** (`ACCESS_TOKEN`)
- **Access Token Secret** (`ACCESS_TOKEN_SECRET`)


## Setup

### 1. Clone the Repository

Clone this repository to your local machine:

```
git clone https://github.com/yourusername/twitter-api-go.git
cd twitter-api-go
```

### 2. Install Dependencies
Install the necessary Go dependencies using go mod:

```
go mod tidy
```

### 3. Set Up Environment Variables
Create a .env file in the root of the project and add your Twitter API credentials as follows:

```
env
Copy code
CONSUMER_KEY=your_consumer_key
CONSUMER_SECRET=your_consumer_secret
ACCESS_TOKEN=your_access_token
ACCESS_TOKEN_SECRET=your_access_token_secret
```

### 4. Run the Server
Run the Go application:
```
go run main.go

```
The server will start running on http://localhost:8080.

### Usage
1. Send a POST Request
You can use Postman or cURL to send a POST request to the /tweet endpoint to post a tweet. Here's an example request body that contains the tweet text.

Postman Example:
- Method: POST
- URL: http://localhost:8080/tweet
- Body: (raw, JSON)
```
    "tweet_text": "Hello, this is a tweet from Postman!"
```

### 2. Response
If successful, the server will return the tweet ID and a success message:

```
    "message": "Tweet posted successfully",
    "tweet_id": "1456789123456789123"
```