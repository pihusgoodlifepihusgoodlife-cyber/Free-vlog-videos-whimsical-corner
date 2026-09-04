<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Whimsical Corner 🍓</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

  <link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@400;500;600;700;800&family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: "Quicksand", sans-serif;

      background:
        radial-gradient(circle at 10% 10%, #ffffff 0 5%, transparent 6%),
        radial-gradient(circle at 90% 20%, #ffffff 0 4%, transparent 5%),
        linear-gradient(135deg, #ffd6e7, #ffe8f1, #ffd0e3);

      color: #7b3f5f;
    }

    .container {
      width: 92%;
      max-width: 850px;
      margin: auto;
      padding: 35px 0 60px;
    }

    header {
      text-align: center;
      padding: 25px 15px 35px;
    }

    h1 {
      margin: 0;
      font-family: "Baloo 2", cursive;
      font-size: 48px;
      font-weight: 800;
      color: #c94f82;
    }

    .subtitle {
      margin-top: 5px;
      font-size: 18px;
      font-weight: 600;
      color: #9a5273;
    }

    .upload-box {
      background: rgba(255, 255, 255, 0.85);
      border: 3px dashed #e99abc;
      border-radius: 25px;
      padding: 30px 20px;
      text-align: center;
      box-shadow: 0 10px 30px rgba(180, 80, 120, 0.12);
      margin-bottom: 30px;
    }

    .upload-box h2 {
      font-family: "Baloo 2", cursive;
      font-size: 28px;
      margin: 0 0 15px;
      color: #c94f82;
    }

    input[type="file"] {
      display: block;
      width: 100%;
      max-width: 500px;
      margin: 15px auto;
      padding: 12px;
      border-radius: 15px;
      border: 2px solid #f0b2ca;
      background: #fff7fa;
      font-family: "Quicksand", sans-serif;
    }

    button {
      border: none;
      border-radius: 50px;
      padding: 13px 28px;
      font-family: "Baloo 2", cursive;
      font-size: 20px;
      font-weight: 700;
      cursor: pointer;

      background: #e875a4;
      color: white;

      box-shadow: 0 6px 15px rgba(201, 79, 130, 0.25);
      transition: 0.2s;
    }

    button:hover {
      transform: translateY(-2px);
      background: #d95f91;
    }

    button:disabled {
      opacity: 0.6;
      cursor: not-allowed;
      transform: none;
    }

    #status {
      margin-top: 15px;
      font-weight: 600;
      min-height: 25px;
    }

    .videos {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 22px;
    }

    .video-card {
      background: rgba(255, 255, 255, 0.9);
      border-radius: 25px;
      padding: 15px;
      box-shadow: 0 8px 25px rgba(180, 80, 120, 0.13);
      overflow: hidden;
    }

    .video-card video {
      width: 100%;
      display: block;
      border-radius: 18px;
      background: #f7dce7;
    }

    .video-card h3 {
      font-family: "Baloo 2", cursive;
      font-size: 22px;
      margin: 12px 5px;
      color: #a74670;
      word-break: break-word;
    }

    .download {
      display: block;
      text-align: center;
      text-decoration: none;
      background: #f19abb;
      color: white;
      padding: 11px;
      border-radius: 30px;
      font-family: "Baloo 2", cursive;
      font-size: 18px;
      font-weight: 700;
      transition: 0.2s;
    }

    .download:hover {
      background: #df78a1;
    }

    footer {
      text-align: center;
      margin-top: 40px;
      font-size: 15px;
      font-weight: 600;
      color: #9b607c;
    }

    @media (max-width: 600px) {
      h1 {
        font-size: 38px;
      }

      .subtitle {
        font-size: 16px;
      }

      .container {
        padding-top: 15px;
      }
    }
  </style>
</head>

<body>

  <div class="container">

    <header>
      <h1>Whimsical Corner 🍓</h1>
      <div class="subtitle">
        Free little videos for everyone ☘️🦭🐶🐰🪽🍄
      </div>
    </header>

    <!-- UPLOAD SECTION -->
    <section class="upload-box">

      <h2>Upload
