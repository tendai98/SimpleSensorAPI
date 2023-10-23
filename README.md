## Prerequisites

Before using this application, make sure you have the following prerequisites:

- Node.js installed
- Firebase account and Firebase App SDK credentials configured (refer to the `fb.js` file)
- Knowledge of Express.js and Firebase Realtime Database

## Setup

1. Clone the repository to your local machine:

   ```
   git clone https://github.com/your-repo-url.git
   cd your-repo-directory
   ```

2. Install the required Node.js modules:

   ```
   npm install
   ```

3. Configure Firebase:
   - Ensure you have a Firebase account.
   - Update the `fb.js` file with your Firebase Admin SDK credentials.

## Code Overview

This Express server handles HTTP requests related to sensor data and channel data and integrates with Firebase Realtime Database.

- The `SENSOR_ID` variable is set to a unique identifier for your sensor.
- The server listens on the port defined in the `process.env.PORT` variable.

### Routes

- **GET /api**: This endpoint is used to receive sensor data, parse it, and store it in the Firebase Realtime Database. The data is sent as a query parameter `value`.
- **GET /data**: This endpoint sends the current state value stored in the `stateValue` variable.

- **GET /api-1**: This endpoint is used to receive data related to channel-1, parse it, and store it.
- **GET /data-1**: This endpoint sends the current state value of channel-1 stored in the `channelValue1` variable.

### Usage

1. To start the server, run the following command:

   ```
   node app.js
   ```

2. The server will start listening on the specified port, and you can make requests to the defined endpoints.

3. Use the `/api` and `/api-1` endpoints to send data to the server. The data should be included as a query parameter with the key `value`.

4. Use the `/data` and `/data-1` endpoints to retrieve the stored state values.

### Error Handling

The code includes basic error handling for data parsing and Firebase operations. Any errors encountered during these processes are logged to the console.

