<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Cyber Terminal</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      background: black;
      color: #00ff66;
      font-family: "Courier New", monospace;
      overflow: hidden;
    }

    .terminal {
      padding: 20px;
      max-width: 900px;
      margin: auto;
      margin-top: 50px;
      border: 2px solid #00ff66;
      box-shadow: 0 0 20px #00ff66;
    }

    .title {
      font-size: 24px;
      text-align: center;
      margin-bottom: 20px;
      text-shadow: 0 0 10px #00ff66;
    }

    .line {
      white-space: pre-wrap;
      line-height: 1.5;
    }

    .cursor {
      display: inline-block;
      width: 10px;
      background: #00ff66;
      margin-left: 5px;
      animation: blink 1s infinite;
    }

    @keyframes blink {
      0%, 50%, 100% { opacity: 1; }
      25%, 75% { opacity: 0; }
    }

    footer {
      text-align: center;
      margin-top: 30px;
      font-size: 12px;
      opacity: 0.7;
    }
  </style>
</head>
<body>

  <div class="terminal">
    <div class="title">ACCESS TERMINAL v1.0</div>
    <div id="output" class="line"></div>
    <span class="cursor"></span>

    <footer>
      © 2026 | Cyber Security Interface
    </footer>
  </div>

  <script>
    const text = [
      "Initializing system...",
      "Loading security modules...",
      "Bypassing firewall... [SIMULATION]",
      "Access granted.",
      "",
      "Welcome, User.",
      "Status: ONLINE",
      "Mode: PROFESSIONAL DEMO",
      "",
      "This is a visual hacker-style interface.",
      "No illegal actions performed.",
      "",
      ">_"
    ];

    let index = 0;
    let charIndex = 0;
    const speed = 40;
    const output = document.getElementById("output");

    function typeText() {
      if (index < text.length) {
        if (charIndex < text[index].length) {
          output.innerHTML += text[index].charAt(charIndex);
          charIndex++;
          setTimeout(typeText, speed);
        } else {
          output.innerHTML += "<br>";
          index++;
          charIndex = 0;
          setTimeout(typeText, 300);
        }
      }
    }

    typeText();
  </script>

</body>
</html>
