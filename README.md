# Focus Timer Device Control

A web application for controlling a physical focus timer device with LED display. This application provides a user interface to manage device status, display messages, and control timers.

## Features

- Real-time device status monitoring
- Custom status message display
- Focus timer and Pomodoro timer functionality
- Device mode control (Focus, Pomodoro, Busy)
- Battery level monitoring
- MQTT integration for device communication
- Smart home integration via Matter protocol
- Cross-platform sync
- Integration with calendar events and calls

## Technical Specifications

- 72x16 RGB LED matrix display
- 3250 mAh battery (2 weeks standby, 8 hours active)
- USB Type-C connectivity
- Wi-Fi 6 and Bluetooth 5.4 support
- Physical controls (buttons and scroll wheel)

## Prerequisites

- Node.js (v14 or higher)
- npm (v6 or higher)
- MQTT broker (for device communication)
- TypeScript (v4.9 or higher)

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

### Project Structure

```
focus-timer-device/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/    # React components
│   │   │   ├── DeviceControl.tsx
│   │   │   ├── StatusDisplay.tsx
│   │   │   └── TimerControl.tsx
│   │   ├── types.ts       # TypeScript interfaces
│   │   └── App.tsx        # Main application component
│   ├── package.json
│   └── tsconfig.json
├── server/                 # Node.js backend
│   └── index.ts           # Express server and MQTT client
├── package.json
├── tsconfig.json
└── README.md
```

### API Endpoints

- `GET /api/status` - Get current device status
- `POST /api/status` - Update device status

### MQTT Topics

- `device/status` - Device status updates
- `device/display` - Display message updates

### Smart Home Integration

The device supports integration with:
- Google Home
- Apple Home
- Home Assistant

### Device Modes

1. **Focus Mode**
   - Blocks distractions
   - Displays focus timer
   - Custom status messages

2. **Pomodoro Mode**
   - 25-minute work sessions
   - 5-minute breaks
   - Customizable durations

3. **Busy Mode**
   - Custom status messages
   - Distraction blocking
   - Calendar integration

### Development Workflow

1. **Setting up the development environment**
   ```bash
   # Install dependencies
   npm install
   cd client && npm install && cd ..

   # Start development servers
   npm run dev
   ```

2. **Making changes**
   - Server code is in `server/index.ts`
   - Client components are in `client/src/components/`
   - Types are defined in `client/src/types.ts`

3. **Testing**
   - Run client tests: `cd client && npm test`
   - Test MQTT communication using an MQTT client

4. **Building for production**
   ```bash
   # Build client
   npm run build

   # Start production server
   npm start
   ```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Material-UI for the component library
- Socket.IO for real-time communication
- MQTT.js for MQTT protocol implementation
- React for the frontend framework
- TypeScript for type safety 
