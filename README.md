# Zowie6.github.io
<!doctype html>
<html lang="en">
<head>
  <title>&lt;model-viewer&gt; template</title>
  <meta charset="utf-8">
  <meta name="description" content="&lt;model-viewer&gt; template">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link type="text/css" href="./styles.css" rel="stylesheet"/>
  <style>
    body {
      background-color: #939F9F;
      margin: 0;
    }
    .control-panel {
      position: absolute;
      bottom: 20px;
      left: 20px;
      background-color: #f0f0f0;
      border-radius: 12px;
      padding: 16px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
      font-family: sans-serif;
      display: flex;
      flex-direction: column;
      gap: 12px;
      z-index: 10;
    }

    .control-section {
      display: flex;
      flex-direction: column;
      gap: 8px;
    }

    .control-section h3 {
      margin: 0;
      font-size: 14px;
      color: #333;
    }

    .control-section button {
      padding: 8px 12px;
      background-color: #ccc;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 14px;
      transition: background-color 0.2s ease;
    }

    .control-section button:hover {
      background-color: #bbb;
    }
  </style>
</head>
<body>
  <model-viewer src="Untitled3.glb" ar ar-modes="webxr scene-viewer quick-look" camera-controls tone-mapping="neutral" poster="poster.png" shadow-intensity="1" animation-name="Final(1B16A8B0-E0B9-440D-99A0-4057841DA726)Action" camera-orbit="-179.1deg 71.47deg 0.5471m" field-of-view="30deg" id="Jonix">

    <!-- Hotspots -->
    <button class="Hotspot" slot="hotspot-5" data-surface="34 0 2334 2335 2344 0.246 0.138 0.616" data-visibility-attribute="visible">
      <div class="HotspotAnnotation">Printer</div>
    </button>
    <button class="Hotspot" slot="hotspot-6" data-surface="20 0 645 164 646 0.334 0.144 0.522" data-visibility-attribute="visible">
      <div class="HotspotAnnotation">Stand</div>
    </button>
    <button class="Hotspot" slot="hotspot-8" data-surface="59 0 2956 2958 2989 0.225 0.765 0.010" data-visibility-attribute="visible">
      <div class="HotspotAnnotation">Buttons</div>
    </button>
    <button class="Hotspot" slot="hotspot-9" data-surface="69 0 135 108 226 0.321 0.259 0.420" data-visibility-attribute="visible">
      <div class="HotspotAnnotation">Storage</div>
    </button>

    <div class="progress-bar hide" slot="progress-bar">
      <div class="update-bar"></div>
    </div>
    <button slot="ar-button" id="ar-button">View in your space</button>
    <div id="ar-prompt"><img src="ar_hand_prompt.png"></div>
  </model-viewer>

  <!-- Modern Aesthetic Button Panel -->
  <div class="control-panel">
    <div class="control-section">
      <h3>Materials</h3>
      <button onclick="M1()">M1</button>
      <button onclick="M2()">M2</button>
      <button onclick="M3()">M3</button>
    </div>

    <div class="control-section">
      <h3>Views</h3>
      <button onclick="setOrbit('-179.1deg 71.47deg 0.5471m')">Front</button>
      <button onclick="setOrbit('-179.8deg 0.0000573deg 0.5471m')">Top</button>
      <button onclick="setOrbit('-89.7deg 87.81deg 0.5471m')">Side</button>
    </div>

    <div class="control-section">
      <h3>Animations</h3>
      <button onclick="playPrinter()">Printer</button>
      <button onclick="playStorage()">Storage</button>
      <button onclick="pause()">Pause</button>
    </div>
  </div>

  <!-- JS Functions -->
  <script>
    function setOrbit(orbit) {
      document.getElementById('Jonix').cameraOrbit = orbit;
    }

    function M1() {
      document.getElementById("Jonix").variantName = "M1";
    }

    function M2() {
      document.getElementById("Jonix").variantName = "M2";
    }

    function M3() {
      document.getElementById("Jonix").variantName = "M3";
    }

    function playPrinter() {
      document.getElementById('Jonix').animationName = "Final(E07CEDD3-8BB7-42E8-A43F-361EB5C98FE5)Action";
      document.getElementById('Jonix').play();
    }

    function playStorage() {
      document.getElementById('Jonix').animationName = "Final(1B16A8B0-E0B9-440D-99A0-4057841DA726)Action";
      document.getElementById('Jonix').play();
    }

    function pause() {
      document.getElementById('Jonix').pause();
    }
  </script>

  <script src="script.js"></script>
  <script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/4.0.0/model-viewer.min.js"></script>
</body>
</html>

