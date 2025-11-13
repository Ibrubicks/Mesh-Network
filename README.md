📡 Mesh-Network — Offline Host-Client Chat & SOS Communication

Mesh-Network is a Flutter-based offline communication system that enables real-time chat and SOS broadcasting without internet, Wi-Fi, or mobile data.
It uses Bluetooth / Wi-Fi Direct (Nearby Connections API) to create a host–client mesh-like communication setup suitable for:

Natural disaster zones

Remote areas without network coverage

Emergency rescue teams

Offline group communication

The app allows devices to host a hotspot-like session or join as a client, exchange messages, and broadcast critical SOS alerts across connected devices instantly.

🚀 Features
🔥 Offline Host–Client Networking

No mobile data or Wi-Fi required

Uses Bluetooth + Wi-Fi Direct (Nearby Connections)

Any device can create a host, others can discover and join

💬 Real-Time Chat

Send and receive messages between host & multiple clients

Host automatically forwards messages between clients

System messages included (connected, disconnected, etc.)

🆘 SOS Broadcasting

Send an emergency SOS alert with:

Sender name

Timestamp

Full-screen pulsing red alert screen (auto-dismiss in 5 secs)

Alerts are forwarded to all devices instantly

🎨 Custom Dark UI Theme

A clean, minimalistic dark theme with accent colors

Custom fonts & responsive layout

🔒 Permission Handling

Automatically requests:

Bluetooth

Location

Wi-Fi Direct / Nearby Devices

🧠 Architecture Overview
Flutter App
│
├── core/
│   ├── network_manager.dart     # Handles Nearby API, discovery, ads, connections
│   └── message_manager.dart     # ChatMessage JSON encoding/decoding
│
├── models/
│   └── chat_message.dart        # Model for chat + SOS messages
│
├── pages/
│   ├── home_page.dart
│   ├── chat_page.dart
│   └── sos_page.dart
│
└── main.dart                    # UI, navigation, state machine, SOS UI logic

🔗 Communication Flow

Host starts advertising

Clients start discovering

Client chooses a host and connects

Host maintains list of connected clients

Chat/SOS messages are encoded → sent → decoded

Host broadcasts messages to all other clients

Clients send only to host (host routes further)

📱 Getting Started
1. Clone the Repository
git clone https://github.com/Ibrubicks/Mesh-Network.git
cd Mesh-Network

2. Install Dependencies
flutter pub get

3. Run the App
flutter run

🛠️ Requirements

Flutter 3.x+

Android device with:

Bluetooth

Nearby/Wi-Fi Direct permissions

iOS support depends on Nearby Connections availability (limited)

Recommended: Android-to-Android for best stability.

🎮 How It Works (User Flow)
🟩 Host

Tap Create Host

Host starts advertising

Clients join automatically after requesting

Host sees connected clients list

Chat + SOS fully enabled

🟦 Client

Tap Join as Client

Device scans for hosts

User selects host → connect

Once connected → messaging enabled

🆘 Sending SOS

Tap the SOS icon

A broadcast message is sent

All connected devices show:

Full-screen red SOS ring

Sender name

Timestamp

🧩 Key Components Explained
📡 NetworkManager

Handles all Nearby Connections API actions:

Start/stop advertising

Start/stop discovery

Accept/reject connections

Send payload (messages)

Stop endpoints

💬 MessageManager

Encodes ChatMessage → JSON

Decodes JSON → ChatMessage

📨 ChatMessage

Represents:

Normal chat messages

System messages

SOS messages

🛑 Limitations / Future Improvements

Currently uses Host–Client (star topology), not full peer-to-peer mesh

Add encryption for secure communication

Add offline logs / message persistence

Add GPS coordinates when sending SOS

Add vibrations + sound alerts

Add device naming instead of random IDs

🤝 Contributing

Pull requests are welcome!
Feel free to open issues for enhancements or bug reports.

📜 License

This project is licensed under the MIT License.

👤 Author

Mohammed Ibrahim (Ibrubicks)
GitHub: https://github.com/Ibrubicks
