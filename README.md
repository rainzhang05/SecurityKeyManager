# Feitian SK Manager

Web-based management tool for Feitian security keys. The project includes a React web UI, a Manifest V3 Chrome extension, and a Rust native messaging host.

## Requirements

- Node.js 18+ and npm 9+
- Rust and Cargo
- Chrome or another Chromium-based browser

## Setup

Install dependencies and build the project:

```bash
npm install
npm run build
```

Start the web UI:

```bash
npm run dev
```

Open the URL shown by Vite, usually `http://localhost:5173`.

To load the extension locally:

1. Open `chrome://extensions`.
2. Enable **Developer mode**.
3. Select **Load unpacked**.
4. Choose the repository's `extension/` directory.

The native host must be built and registered before the extension can communicate with a security key:

```bash
npm run build:native
./setup-native-host.sh
```

`setup-native-host.sh` currently targets Chrome on macOS. For other platforms, see [`native/README.md`](native/README.md).

## Commands

```bash
npm run build       # Build the web UI and native host
npm run test        # Run web and native tests
npm run lint        # Run web and native linters
npm run format      # Format web and native code
```

## Supported devices

Feitian devices with vendor ID `0x096e` are supported. The native host communicates with devices through HID and PC/SC.

## License

MIT — see [`LICENSE`](LICENSE).