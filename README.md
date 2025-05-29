# 🎥 Video Conferencing Web Application

A real-time video conferencing web application built using **vanilla HTML, CSS, and JavaScript**, integrated with the **AgoraRTC SDK** to enable seamless video and audio communication.

## 🚀 Features

- **Join Video Call**: One-click entry into a video conference, initiating local video and audio streams.
- **Dynamic Video Streams**: Auto-updating grid layout displaying all active participants.
- **Stream Controls**: Intuitive buttons to toggle mic/camera and leave the call.
- **Responsive Design**: Optimized for desktops, tablets, and mobile devices.
- **Real-Time Communication**: Powered by AgoraRTC for low-latency video/audio streaming.

## 🛠️ Technologies Used

- **HTML**: Defines layout and structural elements.
- **CSS**: Modern dark-themed UI with a black and blue color scheme and smooth animations.
- **JavaScript**: Core logic for stream management, DOM updates, and SDK event handling.
- **AgoraRTC SDK**: Real-time audio/video communication.

## 📁 Project Structure

video-conference-app/
├── index.html # Main HTML file
├── css/
│ └── styles.css # UI styling
├── js/
│ └── main.js # Core JavaScript (Agora + DOM logic)
└── README.md # Project documentation

markdown
Copy
Edit

## ⚙️ How It Works

- **HTML (`index.html`)**  
  Defines the video grid (`#video-streams`) and control panel (`#controls`). Loads the Agora SDK via CDN.

- **CSS (`styles.css`)**  
  Responsive grid layout, hover animations, and a black/blue color theme.

- **JavaScript (`main.js`)**  
  - Initializes Agora client.
  - Creates and plays local tracks.
  - Publishes to the channel.
  - Dynamically creates/removes video elements.
  - Listens for Agora events (user joined/left, published).

## 🔧 Setup and Usage

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/video-conference-app.git
   cd video-conference-app
Serve the App
Use a local server (e.g., VS Code Live Server or Python)

bash
Copy
Edit
# Python 3
python -m http.server
Configure AgoraRTC
Replace the placeholders in main.js:

javascript
Copy
Edit
const APP_ID = "YOUR_APP_ID";
const TOKEN = "YOUR_TEMP_TOKEN";
const CHANNEL = "YOUR_CHANNEL_NAME";
Test the App

Open in multiple browser tabs/devices.

Click "Join Stream" to enter the call.

Use mic/camera toggle and "Leave Stream" to exit.

🧩 Example Code Snippets
📄 HTML (index.html)
html
Copy
Edit
<div id="video-streams"></div>
<div id="controls">
  <button id="join-btn">Join Stream</button>
  <button id="leave-btn">Leave Stream</button>
  <button id="mic-btn">Mic On</button>
  <button id="camera-btn">Camera On</button>
</div>
🎨 CSS (styles.css)
css
Copy
Edit
#video-streams {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  background: #1a1a1a;
  padding: 20px;
}
.video-container {
  border: 2px solid #1e90ff;
  border-radius: 10px;
  transition: transform 0.3s;
}
.video-container:hover {
  transform: scale(1.05);
}
⚙️ JavaScript (main.js)
javascript
Copy
Edit
const client = AgoraRTC.createClient({ mode: 'rtc', codec: 'vp8' });
let localTracks = [];

async function joinAndDisplayLocalStream() {
  const UID = await client.join(APP_ID, CHANNEL, TOKEN, null);
  localTracks = await AgoraRTC.createMicrophoneAndCameraTracks();

  const container = document.createElement('div');
  container.className = 'video-container';
  container.id = `user-container-${UID}`;

  const player = document.createElement('div');
  player.className = 'video-player';
  player.id = `user-${UID}`;

  container.appendChild(player);
  document.getElementById('video-streams').appendChild(container);

  localTracks[1].play(`user-${UID}`);
  await client.publish(localTracks);
}
🌟 Future Improvements
Add user authentication

Implement screen sharing

Add real-time chat during the call

Improve error handling for network/SDK issues

UI themes and animations

📸 Screenshots
Add screenshots here showing the dark UI, responsive grid layout, and control panel.

🔗 Live Demo
Host the app using GitHub Pages, Netlify, or Vercel and include the link here.

⚠️ Notes
Replace your Agora credentials (APP_ID, TOKEN, and CHANNEL) in the code.

Never commit private keys or tokens to the repository.

📄 License
This project is licensed under the MIT License.

