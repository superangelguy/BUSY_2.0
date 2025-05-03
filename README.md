# Focus Timer Device Control

A web application for controlling a physical focus timer device with LED display. This application provides a user interface to manage device status, display messages, and control timers.

## Features

- Real-time device status monitoring
- Custom status message display
- Focus timer and Pomodoro timer functionality
- Device mode control (Focus, Pomodoro, Busy)
- Battery level monitoring
- MQTT integration for device communication

## Prerequisites

- Node.js (v14 or higher)
- npm (v6 or higher)
- MQTT broker (for device communication)

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd focus-timer-device
```

2. Install server dependencies:
```bash
npm install
```

3. Install client dependencies:
```bash
cd client
npm install
cd ..
```

4. Create a `.env` file in the root directory with the following variables:
```
PORT=3001
MQTT_BROKER_URL=mqtt://your-mqtt-broker-url
```

## Running the Application

1. Start the server:
```bash
npm run server
```

2. In a new terminal, start the client:
```bash
npm run client
```

The application will be available at `http://localhost:3000`.

## Development

- Server runs on port 3001
- Client runs on port 3000
- MQTT broker should be running and accessible

## Project Structure

```
focus-timer-device/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/    # React components
│   │   ├── types.ts       # TypeScript interfaces
│   │   └── App.tsx        # Main application component
│   └── package.json
├── server/                 # Node.js backend
│   └── index.ts           # Express server and MQTT client
├── package.json
└── README.md
```

## API Endpoints

- `GET /api/status` - Get current device status
- `POST /api/status` - Update device status

## MQTT Topics

- `device/status` - Device status updates
- `device/display` - Display message updates

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details. 
