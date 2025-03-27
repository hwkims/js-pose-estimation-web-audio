# JavaScript Pose Estimation with Web Audio Feedback (js-pose-estimation-web-audio)

[![GitHub](https://img.shields.io/badge/GitHub-hwkims-blue?logo=github)](https://github.com/hwkims)

This project demonstrates real-time human pose estimation in the browser using a webcam feed. It utilizes TensorFlow.js with the MoveNet model to detect body keypoints. When a specific pose (raising the right hand above the shoulder) is detected, it triggers a sine wave sound generated using the Web Audio API.

The entire application is contained within a single HTML file (`index.html` 또는 `motion_sound.html`).

## ✨ Features

*   Real-time pose estimation from webcam video using TensorFlow.js and MoveNet.
*   Visualization of detected keypoints and skeleton on an HTML Canvas.
*   Detection of a specific pose: Right hand raised above the shoulder.
*   Generation and playback of a sine wave sound using the Web Audio API upon pose detection (no external audio files needed).
*   Client-side implementation (runs entirely in the user's browser).
*   Simple and contained within a single HTML file.

## 🛠️ Technologies Used

*   HTML5 (Webcam via `getUserMedia`, Canvas)
*   CSS3 (Basic Styling)
*   JavaScript (ES6+)
*   [TensorFlow.js](https://www.tensorflow.org/js) - Core library for machine learning in JavaScript.
*   [TensorFlow.js Pose Detection API (MoveNet)](https://github.com/tensorflow/tfjs-models/tree/master/pose-detection) - Pre-trained model for efficient pose estimation.
*   [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) - For generating and playing sounds directly in the browser.

## 🚀 How to Run

1.  **Clone or Download:**
    *   Clone this repository:
        ```bash
        git clone https://github.com/hwkims/js-pose-estimation-web-audio.git
        cd js-pose-estimation-web-audio
        ```
    *   Or, download the `index.html` (or `motion_sound.html`) file directly.

2.  **Run a Local Web Server:**
    *   Due to browser security restrictions (CORS, `getUserMedia`), you need to run this HTML file from a local web server. You cannot simply open the file directly using the `file://` protocol.
    *   **Using Python 3:**
        ```bash
        python -m http.server
        ```
    *   **Using Node.js (requires `http-server` installed globally):**
        ```bash
        npm install -g http-server # If not already installed
        http-server .
        ```
    *   **Using VS Code:** Use the "Live Server" extension.

3.  **Open in Browser:**
    *   Open your web browser and navigate to the local server address (e.g., `http://localhost:8000`, `http://127.0.0.1:8000`, or the address provided by Live Server).

4.  **Grant Camera Permission:**
    *   Allow the browser to access your webcam when prompted.

5.  **Interact:**
    *   Stand in front of the camera. You should see your skeleton overlayed on the video feed.
    *   **Raise your right hand clearly above your right shoulder.** A sine wave sound should play briefly.

## 📝 Notes

*   Performance may vary depending on your device's hardware.
*   The MoveNet 'Thunder' model is used for better accuracy, but 'Lightning' can be used for potentially faster performance on lower-end devices (you can change this in the `loadDetector` function in the script).
*   Audio playback might require an initial user interaction (like clicking anywhere on the page) in some browsers due to autoplay policies. The code includes a listener to attempt resuming the `AudioContext` on the first click.
*   Pose detection sensitivity can be adjusted by changing the `minConfidence` variable or the pose checking logic in `checkRightHandUp`.

##📄 License

This project is open source and available under the [MIT License](LICENSE). (추후 LICENSE 파일을 추가하거나 원하시는 라이선스를 명시하세요)

---

Feel free to contribute or suggest improvements!
