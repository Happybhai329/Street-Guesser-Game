# 🌍 Street Guesser Game

An interactive, responsive geography-guessing web game inspired by GeoGuessr, built with the **Google Maps JavaScript API**, **Street View Service**, and vanilla **JavaScript**. Players are dropped into an unknown 360° panoramic Street View location and must explore their surroundings, identify visual clues, and pinpoint their location on an interactive world map.

[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Google Maps API](https://img.shields.io/badge/Google%20Maps-API-4285F4?style=for-the-badge&logo=googlemaps&logoColor=white)](https://developers.google.com/maps/documentation/javascript)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![Bootstrap 4](https://img.shields.io/badge/Bootstrap-4.1.3-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![GitHub Pages](https://img.shields.io/badge/Deployed%20on-GitHub%20Pages-222222?style=for-the-badge&logo=githubpages&logoColor=white)](https://happybhai329.github.io/Street-Guesser-Game/)

---

## 🌐 Live Demo

Experience the game directly in your browser:

🔗 **[https://happybhai329.github.io/Street-Guesser-Game/](https://happybhai329.github.io/Street-Guesser-Game/)**

---

## 🚀 Features

- **🧭 Immersive 360° Street View Navigation**:
  - Full panoramic exploration with pan, tilt, pitch, and zoom capabilities.
  - Interactive road traversal to read street signs, landmarks, architecture, and environmental clues.
- **🗺️ Interactive Map Guessing**:
  - Side-by-side interactive Google Map allowing intuitive pin placement anywhere in the region.
  - One-click marker repositioning before locking in the final guess.
- **📐 High-Precision Distance Computation (Haversine Formula)**:
  - Accurately computes the spherical distance between the player's guess coordinates and the true Street View origin in kilometers.
- **🎯 Visual Trajectory & Target Reveal**:
  - Automatically draws a dotted geodesic line connecting the guess marker to the actual location pin upon guess submission.
  - Pans and zooms the map to clearly present the distance gap.
- **🎉 Animated Feedback & Confetti Celebration**:
  - Dynamic score commentary categorized into accuracy tiers (*"You nailed it!"*, *"Close call!"*, *"Keep exploring!"*, *"Did you guess from outer space?"*).
  - High-accuracy guesses trigger a colorful canvas-based confetti particle explosion (`confetti.js`).
- **🏙️ City Geocoding & Modal Greeting**:
  - Integrated introductory modal welcoming players and explaining game mechanics.
  - Built-in geocoding support to dynamically center and sample coordinates around specified metropolitan regions.
- **📱 Responsive Dual-Pane Viewport**:
  - Dynamic 50/50 split-screen layout for desktop monitors.
  - Automatically adapts to stacked top/bottom panes on mobile devices and narrow viewports.

---

## 🛠️ Tech Stack

| Category | Technology | Description |
|---|---|---|
| **Core Language** | [JavaScript (ES6+)](https://developer.mozilla.org/en-US/docs/Web/JavaScript) | Core game loops, map event listeners, coordinate generation, and scoring |
| **Mapping Engine** | [Google Maps JavaScript API](https://developers.google.com/maps/documentation/javascript) | Vector map rendering, custom markers, polyline drawing, and geocoding |
| **Panorama Engine** | [Google Street View Service](https://developers.google.com/maps/documentation/javascript/streetview) | 360-degree interactive street-level imagery and positioning |
| **Styling & Layout** | HTML5, CSS3, [Bootstrap 4](https://getbootstrap.com/) | Responsive split-screen grid, modern buttons, and modal dialogs |
| **Animation** | Canvas Confetti (`confetti.js`) | Client-side physics particle effect for celebratory victories |
| **Hosting** | [GitHub Pages](https://pages.github.com/) | Continuous static hosting and deployment |

---

## 🎮 How to Play

1. **Launch**: Open the game in any modern web browser. Review the introduction modal and start the session.
2. **Scout**: Look around in the Street View pane. Pan 360 degrees, zoom in on signs, observe language, road markings, landscape, and climate.
3. **Pinpoint**: Click on the interactive map pane to drop your guess pin. You can click again to adjust your pin position anytime before submitting.
4. **Submit Guess**: Click the **Guess** button.
5. **Review Score**: The game reveals the true location, draws a dotted line indicating the distance in kilometers, evaluates your accuracy with a performance phrase, and unleashes celebratory confetti for pinpoint guesses!

---

## 📂 Project Structure

```text
Street-Guesser-Game/
├── confetti.js       # Canvas-based celebratory particle confetti animation
├── config.js         # Configuration file holding the Google Maps API key
├── index.html        # Main HTML entrypoint, dual-pane layout, modal & CDN scripts
├── logic.js          # Core game logic: map initialization, Haversine formula, bounds & markers
├── style.css         # Split-screen responsive layout styling and button aesthetics
└── README.md         # Comprehensive project documentation
```

---

## 📋 Prerequisites

To run or develop this project locally, you need:
- A modern web browser (Google Chrome, Mozilla Firefox, Safari, Microsoft Edge).
- A **Google Maps Platform API Key** with the following APIs enabled:
  - **Maps JavaScript API**
  - **Street View Static / JavaScript API**
  - **Geocoding API**
- *(Optional)* A local HTTP server (such as Python's `http.server`, Node.js `serve`, or the VS Code Live Server extension).

---

## ⚙️ Installation & Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Happybhai329/Street-Guesser-Game.git
   cd Street-Guesser-Game
   ```

2. **Configure your Google Maps API Key**
   Open [`config.js`](config.js) in your text editor and insert your Google Maps API key:
   ```javascript
   const config = {
       googleMapsApiKey: 'YOUR_ACTUAL_GOOGLE_MAPS_API_KEY'
   };

   function getGoogleMapsApiKey() {
       return config.googleMapsApiKey;
   }
   ```

3. **Launch the Application Locally**

   Since Google Maps JavaScript API requires an HTTP/HTTPS origin (or local server) for certain assets, serve the files using any lightweight static server:

   - **Using Python 3**:
     ```bash
     python -m http.server 8000
     ```
     Navigate to: `http://localhost:8000`

   - **Using Node.js (`npx serve`)**:
     ```bash
     npx serve .
     ```

   - **Using VS Code**:
     Install the **Live Server** extension, right-click `index.html`, and select **"Open with Live Server"**.

---

## 🔒 API Key Security Best Practice

When hosting this project publicly on platforms like GitHub Pages, client-side API keys are visible in the browser source. To safeguard your Google Cloud account against unauthorized usage and quota consumption:

1. Navigate to the **[Google Cloud Console > Credentials](https://console.cloud.google.com/apis/credentials)** page.
2. Select your API Key and navigate to **Application restrictions**.
3. Choose **Websites** (HTTP referrers) and specify your allowed domain patterns:
   - `https://yourusername.github.io/*`
   - `http://localhost:*/*` (for local development)
4. Under **API restrictions**, select **Restrict key** and enable only:
   - *Maps JavaScript API*
   - *Geocoding API*

---

## 📐 Mathematical Methodology

Distance between the guessed location and the actual coordinates is calculated using the **Haversine Formula**, which determines the great-circle distance between two points on a spherical surface given their latitudes and longitudes:

$$\Delta\sigma = 2 \cdot \arcsin\left(\sqrt{\sin^2\left(\frac{\Delta\phi}{2}\right) + \cos(\phi_1)\cos(\phi_2)\sin^2\left(\frac{\Delta\lambda}{2}\right)}\right)$$

$$d = R \cdot \Delta\sigma$$

Where:
- $\phi_1, \phi_2$ are the latitudes of the two coordinates in radians.
- $\Delta\phi = \phi_2 - \phi_1$ is the latitude difference.
- $\Delta\lambda = \lambda_2 - \lambda_1$ is the longitude difference.
- $R$ is Earth's mean radius ($\approx 6{,}371\text{ km}$).

Implemented in [`logic.js`](logic.js):
```javascript
function haversineDistance(lat1, lon1, lat2, lon2) {
    const R = 6371; // Earth's radius in kilometers
    const dLat = degToRad(lat2 - lat1);
    const dLon = degToRad(lon2 - lon1);

    const a = Math.sin(dLat / 2) * Math.sin(dLat / 2) +
              Math.cos(degToRad(lat1)) * Math.cos(degToRad(lat2)) *
              Math.sin(dLon / 2) * Math.sin(dLon / 2);
    const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a));

    return R * c; // Distance in km
}
```

---

## 🔮 Future Roadmap

- [ ] **Timed Challenge Mode**: Add a countdown timer per round for competitive play.
- [ ] **Multi-Round Game Sessions**: Implement a 5-round game system with cumulative point scoring (up to 5,000 points per round).
- [ ] **Hardcore Mode**: Disable movement and panning in Street View for difficulty scaling.
- [ ] **Custom Maps & Themed Playlists**: Select specific countries, famous monuments, or capital cities.
- [ ] **Global Leaderboard**: Save and compare top scores with persistent backend storage or Firebase.

---

## 🤝 Contributing

Contributions, feature suggestions, and enhancements are welcome!

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/NewFeature`)
3. Commit your changes (`git commit -m "Add NewFeature"`)
4. Push to the branch (`git push origin feature/NewFeature`)
5. Open a Pull Request

---

## 📄 License

This project is open source. Please refer to repository headers or contact the author for specific licensing permissions.

---

## 👤 Author

**Happy Bhasin**
- GitHub: [@Happybhai329](https://github.com/Happybhai329)
- Academic: B.Tech CSE (AI Minor)
