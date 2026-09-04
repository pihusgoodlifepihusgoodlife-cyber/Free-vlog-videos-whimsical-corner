<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Pink Vlog Videos</title>

  <style>
    @import url('https://fonts.googleapis.com/css2?family=Baloo+2:wght@400;500;600;700&family=Quicksand:wght@400;500;600;700&display=swap');

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      background: #ffe8f1;
      color: #6b4052;
      font-family: "Quicksand", sans-serif;
    }

    header {
      text-align: center;
      padding: 45px 20px 30px;
    }

    header h1 {
      margin: 0;
      font-family: "Baloo 2", cursive;
      font-size: 42px;
      color: #c75b82;
    }

    header p {
      margin: 5px 0 0;
      font-size: 17px;
    }

    .container {
      max-width: 850px;
      margin: auto;
      padding: 20px;
    }

    .upload-box {
      background: #fff7fa;
      padding: 25px;
      border-radius: 25px;
      border: 2px solid #f7c7d8;
      box-shadow: 0 8px 25px rgba(180, 90, 120, 0.12);
      margin-bottom: 30px;
      text-align: center;
    }

    .upload-box h2 {
      margin-top: 0;
      font-family: "Baloo 2", cursive;
      color: #c75b82;
      font-size: 28px;
    }

    input[type="file"] {
      width: 100%;
      padding: 12px;
      background: white;
      border: 2px dashed #e9a8c0;
      border-radius: 15px;
      font-family: "Quicksand", sans-serif;
    }

    button {
      width: 100%;
      padding: 13px;
      margin-top: 12px;
      border: none;
      border-radius: 15px;
      background: #e989ad;
      color: white;
      font-family: "Baloo 2", cursive;
      font-size: 20px;
      cursor: pointer;
    }

    button:hover {
      background: #d96f98;
    }

    #status {
      margin-top: 12px;
      font-size: 14px;
    }

    .video-card {
      background: #fff7fa;
      padding: 17px;
      border-radius: 25px;
      border: 2px solid #f7c7d8;
      box-shadow: 0 8px 25px rgba(180, 90, 120, 0.12);
      margin-bottom: 25px;
    }

    video {
      width: 100%;
      border-radius: 18px;
      display: block;
    }

    .video-card h2 {
      font-family: "Baloo 2", cursive;
      color: #b95178;
      margin: 15px 5px 5px;
      font-size: 24px;
    }

    .download {
      display: block;
      text-align: center;
      background: #e989ad;
      color: white;
      text-decoration: none;
      padding: 12px;
      border-radius: 15px;
      margin-top: 10px;
      font-family: "Baloo 2", cursive;
      font-size: 19px;
    }

    .download:hover {
      background: #d96f98;
    }

    footer {
      text-align: center;
      padding: 35px 20px;
      font-size: 14px;
    }
  </style>
</head>

<body>

<header>
  <h1>🍓 Pink Vlog Videos</h1>
  <p>Pinteresty • Cute • Aesthetic 🪽</p>
</header>

<div class="container">

  <div class="upload-box">

    <h2>Upload your video 🐰</h2>

    <input
      type="file"
      id="videoFile"
      accept="video/*"
    >

    <button onclick="uploadVideo()">
      Upload Video 🍓
    </button>

    <div id="status"></div>

  </div>

  <div id="videoList"></div>

</div>

<footer>
  Made with love & creativity 🍄
</footer>


<script>

  // =========================
  // CLOUDINARY SETTINGS
  // =========================

  const CLOUD_NAME = "obptrfov";

  const UPLOAD_PRESET = "YOUR_UNSIGNED_UPLOAD_PRESET";


  // =========================
  // UPLOAD
  // =========================

  async function uploadVideo() {

    const file =
      document.getElementById("videoFile").files[0];

    const status =
      document.getElementById("status");

    if (!file) {
      alert("Please select a video first 🐰");
      return;
    }

    status.innerText =
      "Uploading... please wait 🪽";


    const formData =
      new FormData();

    formData.append("file", file);

    formData.append(
      "upload_preset",
      UPLOAD_PRESET
    );


    try {

      const response =
        await fetch(
          `https://api.cloudinary.com/v1_1/${CLOUD_NAME}/video/upload`,
          {
            method: "POST",
            body: formData
          }
        );


      const data =
        await response.json();


      if (!data.secure_url) {
        throw new Error("Upload failed");
      }


      addVideo(
        data.secure_url,
        file.name
      );


      status.innerText =
        "Uploaded successfully! 🍓";


      document.getElementById(
        "videoFile"
      ).value = "";

    }

    catch (error) {

      console.error(error);

      status.innerText =
        "Upload failed. Please try again.";

    }

  }


  // =========================
  // SHOW VIDEO
  // =========================

  function addVideo(url, name) {

    const card =
      document.createElement("div");

    card.className =
      "video-card";


    card.innerHTML = `

      <video controls>
        <source
          src="${url}"
          type="video/mp4">
      </video>

      <h2>${name}</h2>

      <a
        class="download"
        href="${url}"
        download>
        🪽 Download Video
      </a>

    `;


    document
      .getElementById("videoList")
      .prepend(card);

  }

</script>

</body>
</html>
