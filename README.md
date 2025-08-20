<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Hello World Futuristik React</title>
  <style>
    body {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: radial-gradient(circle at center, #0f2027, #203a43, #2c5364);
      font-family: 'Courier New', monospace;
      overflow: hidden;
    }

    h1 {
      color: #0ff;
      font-size: 3em;
      letter-spacing: 3px;
      position: relative;
      text-shadow: 0 0 5px #0ff, 0 0 10px #0ff, 0 0 20px #00f, 0 0 40px #0ff;
      white-space: nowrap;
      overflow: hidden;
      border-right: 3px solid #0ff;
      margin-top: 20px;
    }

    /* Efek glitch */
    h1::before, h1::after {
      content: attr(data-text);
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      overflow: hidden;
      clip: rect(0, 900px, 0, 0);
    }

    h1::before {
      color: #f0f;
      animation: glitchTop 2s infinite linear alternate-reverse;
    }

    h1::after {
      color: #0f0;
      animation: glitchBottom 2s infinite linear alternate-reverse;
    }

    @keyframes glitchTop {
      0% { clip: rect(0, 9999px, 0, 0); }
      10% { clip: rect(0, 9999px, 20px, 0); transform: translate(-2px, -2px); }
      20% { clip: rect(0, 9999px, 0, 0); }
      30% { clip: rect(0, 9999px, 20px, 0); transform: translate(2px, 2px); }
      100% { clip: rect(0, 9999px, 0, 0); }
    }

    @keyframes glitchBottom {
      0% { clip: rect(0, 9999px, 0, 0); }
      10% { clip: rect(20px, 9999px, 40px, 0); transform: translate(2px, 2px); }
      20% { clip: rect(0, 9999px, 0, 0); }
      30% { clip: rect(20px, 9999px, 40px, 0); transform: translate(-2px, -2px); }
      100% { clip: rect(0, 9999px, 0, 0); }
    }

    /* Logo React animasi */
    .react-logo {
      width: 120px;
      height: 120px;
      animation: spin 10s linear infinite;
      filter: drop-shadow(0 0 15px #0ff);
    }

    @keyframes spin {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }
  </style>
</head>
<body>
  <!-- Logo React -->
  <img src="https://upload.wikimedia.org/wikipedia/commons/a/a7/React-icon.svg" 
       alt="React Logo" class="react-logo">

  <!-- Hello World -->
  <h1 id="hello" data-text="Hello World"></h1>

  <script>
    const text = "Hello World";
    const hello = document.getElementById("hello");
    let i = 0;

    function typeWriter() {
      if (i < text.length) {
        hello.innerHTML += text.charAt(i);
        i++;
        setTimeout(typeWriter, 120); // kecepatan ketik
      } else {
        hello.style.borderRight = "none"; // hilangkan cursor setelah selesai
      }
    }

    setTimeout(typeWriter, 500);
  </script>
</body>
</html>
