# Just Radio Player (JRP)

Web application for listening to online radio streams, built with React using React Native Web.

## 📋 Description

Just Radio Player is a modern web application for playing internet radio streams. The application allows users to:

- Play radio streams by URL
- Save favorite radio stations
- View station metadata (ICY headers)
- Adjust playback volume
- Manage favorite stations list

## 🚀 Tech Stack

- **React** 19.2.0
- **React Native Web** 0.21.2
- **TypeScript** 5.9.3
- **Webpack** 5.102.1
- **React Router DOM** 7.9.5
- **Babel** (for transpilation)
- **Webpack Obfuscator** (for code obfuscation in production)

## 📁 Project Structure

```
onlineRadio/
├── client/                    # Client code
│   ├── app/                   # Application initialization
│   │   ├── App.tsx           # Main application component
│   │   ├── web_Init.tsx      # Web version initialization
│   │   └── web_Navigation.tsx # Navigation
│   ├── core/                  # Application core
│   │   ├── services/          # Services
│   │   │   ├── providers/    # React providers
│   │   │   ├── storage/      # Data storage service
│   │   │   └── utils/        # Utilities
│   │   ├── types/            # TypeScript types
│   │   └── ui/               # UI components and styles
│   └── modules/              # Application modules
│       └── radioPlayer/      # Radio player module
│           ├── player.tsx    # Main player component
│           ├── audioModule.tsx # Audio module
│           └── routes.ts    # Module routes
├── public/                    # Built files
├── index-web.ts              # Entry point for web version
├── webpack.config.js         # Webpack configuration
├── tsconfig.json             # TypeScript configuration
└── package.json              # Project dependencies
```

## 🛠️ Installation and Setup

### Prerequisites

- Node.js (version 18+ recommended)
- npm or yarn

### Installing Dependencies

```bash
npm install
```

### Development Mode

Start dev server with hot reload:

```bash
npm run client:start:dev
```

Or use the ready-made batch file:

```bash
App_client_start_dev.bat
```

The application will be available at: `http://localhost:12345` (or the port specified in the `DEV_PORT` environment variable)

### Development Build

```bash
npm run client:build:dev
```

Or:

```bash
App_client_build_dev.bat
```

### Production Build

```bash
npm run client:build:prod
```

Or:

```bash
App_client_build_prod.bat
```

Built files will be located in the `public/` directory.

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the project root for configuration:

```env
DEV_PORT=12345
NODE_ENV=development
```

### Webpack

Webpack configuration is located in `webpack.config.js`. Key features:

- Code splitting into chunks (modules, services, components, styles, locales)
- Code obfuscation in production mode
- CSS and JavaScript minification
- Source maps in development mode
- Hot reload and live reload

### TypeScript

TypeScript configuration in `tsconfig.json` includes:

- Strict type checking mode
- Path aliases for convenient imports (`@client/*`, `@ui/*`, etc.)
- React JSX support
- Declaration file generation

## 🎵 Usage

1. **Playing a radio stream:**
   - Enter the radio stream URL in the input field
   - Click the "Play" button to start playback
   - Use the slider to adjust volume

2. **Saving to favorites:**
   - Enter the radio stream URL
   - Click the star button (★)
   - Enter the station name (or use the automatically retrieved one)
   - Click "Save"

3. **Managing favorites:**
   - Click on a saved station to play it
   - Long press to delete a station

4. **Viewing metadata:**
   - Station metadata (name, genre, description) is displayed automatically if available through ICY headers

## 🔧 Main Components

### RadioPlayer

Main player component (`client/modules/radioPlayer/player.tsx`):

- Playback control
- Storing favorite stations in localStorage
- Retrieving and displaying ICY metadata
- Volume control

### AudioWebModule

Audio module for stream playback (`client/modules/radioPlayer/audioModule.tsx`):

- Audio stream processing
- Playback state management
- Volume control

### Providers

The application uses a provider system for state management:

- `SuperProvider` - main provider
- `SystemDataProvider` - system data
- `LanguageProvider` - localization
- `StyleProvider` - styles
- `NotificationProvider` - notifications

## 📦 Dependencies

### Main Dependencies

- `react` - UI library
- `react-dom` - React for DOM
- `react-native` - React Native (for cross-platform support)
- `react-native-web` - React Native for web
- `react-router-dom` - routing
- `@react-native-async-storage/async-storage` - local storage
- `@react-native-community/slider` - slider component

### Dev Dependencies

- `webpack` - module bundler
- `typescript` - TypeScript compiler
- `babel-loader` - Babel loader
- `html-webpack-plugin` - HTML generation
- `mini-css-extract-plugin` - CSS extraction
- `webpack-obfuscator` - code obfuscation

## 🎨 Features

- **Dark theme** with golden accents
- **Responsive design** based on React Native components
- **Local storage** for favorite stations
- **Automatic metadata retrieval** for radio stations
- **Notification system** for user feedback
- **Optimized build** with code splitting into chunks

## 📝 Scripts

- `client:start:dev` - start dev server
- `client:build:dev` - development build
- `client:build:prod` - production build
- `client:build:devFull` - full build with profiling

## 🔒 Security

In production mode:

- Code is obfuscated to protect against reverse engineering
- console.log and debugger statements are removed
- All resources are minified
- Comments are removed from code

## 📄 License

ISC

## 👤 Author

Project created for portfolio.

---

**Note:** For radio streams to work, ensure that streams support CORS or use a proxy server if necessary.
