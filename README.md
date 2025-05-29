# 🎥 Video Conferencing Web Application

A Real-time video conferencing web application built using **vanilla HTML, CSS, and JavaScript**, integrated with the **AgoraRTC SDK** to enable seamless video and audio communication.

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
   ```
   git clone https://github.com/your-username/video-conference-app.git
   cd video-conference-app

**Serve the App**
Use a local server (e.g., VS Code Live Server or Python)

'''
# Python 3
python -m http.server







**🧩 Example Code Snippets**
**📄 HTML (index.html)**

**🎨 CSS (styles.css)**

**⚙️ JavaScript (main.js)**


**🌟 Future Improvements**
**Add user authentication**

- Implement screen sharing

- Add real-time chat during the call

- Improve error handling for network/SDK issues

- UI themes and animations

**⚠️ Notes**
Replace your Agora credentials (APP_ID, TOKEN, and CHANNEL) in the code.

Never commit private keys or tokens to the repository.

**📄 License**
This project is licensed under the MIT License.

