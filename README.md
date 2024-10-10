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

```bash
git clone https://github.com/yourusername/twitter-api-go.git
cd twitter-api-go
2. Install Dependencies
Install the necessary Go dependencies using go mod:

bash
Copy code
go mod tidy
3. Set Up Environment Variables
Create a .env file in the root of the project and add your Twitter API credentials as follows:

env
Copy code
CONSUMER_KEY=your_consumer_key
CONSUMER_SECRET=your_consumer_secret
ACCESS_TOKEN=your_access_token
ACCESS_TOKEN_SECRET=your_access_token_secret
4. Run the Server
Run the Go application:

bash
Copy code
go run main.go
The server will start running on http://localhost:8080.

Usage
1. Send a POST Request
You can use Postman or cURL to send a POST request to the /tweet endpoint to post a tweet. Here's an example request body that contains the tweet text.

Postman Example:
Method: POST
URL: http://localhost:8080/tweet
Body: (raw, JSON)
json
Copy code
{
    "tweet_text": "Hello, this is a tweet from Postman!"
}
cURL Example:
bash
Copy code
curl -X POST http://localhost:8080/tweet \
-H "Content-Type: application/json" \
-d '{"tweet_text": "Hello, this is a tweet from cURL!"}'
2. Response
If successful, the server will return the tweet ID and a success message:

json
Copy code
{
    "message": "Tweet posted successfully",
    "tweet_id": "1456789123456789123"
}
Troubleshooting
Common Issues
400 Bad Request: This typically indicates an issue with the tweet text or the request format. Make sure the tweet text is less than 280 characters.
401 Unauthorized: This could mean invalid OAuth credentials. Double-check the Twitter API keys and tokens in the .env file.
Debugging
You can add logging statements in the Go code to output the OAuth headers, request body, and response data to assist in debugging any issues with the Twitter API request.
License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgements
Twitter API Documentation
OAuth1 Library for Go
markdown
Copy code

### Key Sections:

- **Prerequisites**: Lists the requirements to run the project.
- **Setup**: Explains how to clone the repository, set up the environment, and run the server.
- **Usage**: Shows how to send POST requests using Postman or cURL.
- **Troubleshooting**: Provides guidance on common issues like `400 Bad Request` or `401 Unauthorized`.
- **Acknowledgements**: Credits the external resources used in the project.

Feel free to customize it according to your specific project setup and additional details.