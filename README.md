<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Whimsical Corner 🍓</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@500;600;700;800&family=Quicksand:wght@500;600;700&display=swap" rel="stylesheet">

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: "Quicksand", sans-serif;
      color: #7d4962;

      background:
        radial-gradient(circle at 10% 15%, rgba(255,255,255,.75) 0 25px, transparent 26px),
        radial-gradient(circle at 90% 12%, rgba(255,255,255,.6) 0 18px, transparent 19px),
        linear-gradient(135deg, #ffd9e8, #fff0f6, #ffd3e5);
    }

    .page {
      width: 92%;
      max-width: 900px;
      margin: auto;
      padding: 30px 0 60px;
    }

    header {
      text-align: center;
      margin-bottom: 28px;
    }

    .logo {
      font-family: "Baloo 2", cursive;
      font-size: clamp(40px, 10vw, 65px);
      line-height: 1;
      font-weight: 800;
      color: #c95783;
      margin: 10px 0;
    }

    .tagline {
      font-size: 17px;
      font-weight: 700;
      color: #986078;
    }

    .box {
      background: rgba(255,255,255,.82);
      border: 2px solid rgba(255,255,255,.9);
      border-radius: 30px;
      padding: 25px;
      margin-bottom: 25px;
      box-shadow: 0 12px 35px rgba(180,75,120,.13);
      backdrop-filter: blur(8px);
    }

    .upload-title {
      margin: 0 0 5px;
      text-align: center;
      font-family: "Baloo 2", cursive;
      font-size: 31px;
      color: #c95783;
    }

    .upload-subtitle {
      text-align: center;
      margin: 0 0 20px;
      font-size: 14px;
      font-weight: 600;
    }

    .file-wrap {
      display: flex;
      justify-content: center;
    }

    input[type="file"] {
      width: 100%;
      max-width: 500px;
      padding: 13px;
      border: 2px dashed #e8a2bd;
      border-radius: 18px;
      background: #fff8fb;
      font-family: "Quicksand", sans-serif;
      color: #80516a;
    }

    .upload-btn {
      display: block;
      margin: 17px auto 0;
      padding: 13px 30px;
      border: none;
      border-radius: 999px;
      background: #df78a2;
      color: white;
      font-family: "Baloo 2", cursive;
      font-size: 21px;
      font-weight: 700;
      cursor: pointer;
      box-shadow: 0 7px 18px rgba(200,80,125,.22);
      transition: .2s;
    }

    .upload-btn:hover {
      transform: translateY(-2px);
      background: #d76592;
    }

    .upload-btn:disabled {
      opacity: .6;
      cursor: not-allowed;
      transform: none;
    }

    #status {
      text-align: center;
      min-height: 24px;
      margin-top: 14px;
      font-size: 14px;
      font-weight: 700;
    }

    .section-title {
      font-family: "Baloo 2", cursive;
      color: #c95783;
      text-align: center;
      font-size: 34px;
      margin: 5px 0 20px;
    }

    .videos {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
    }

    .video-card {
      background: rgba(255,255,255,.92);
      border-radius: 25px;
      padding: 13px;
      box-shadow: 0 9px 25px rgba(180,75,120,.12);
      overflow: hidden;
    }

    video {
      width: 100%;
      display: block;
      border-radius: 18px;
      background: #f5d9e5;
    }

    .video-name {
      margin: 12px 5px;
      font-family: "Baloo 2", cursive;
      font-size: 21px;
      font-weight: 700;
      color: #a94d74;
      word-break: break-word;
    }

    .download-btn {
      display: block;
      width: 100%;
      padding: 11px;
      text-align: center;
      text-decoration: none;
      border-radius: 999px;
      background: #ef96b7;
      color: white;
      font-family: "Baloo 2", cursive;
      font-size: 18px;
      font-weight: 700;
      transition: .2s;
    }

    .download-btn:hover {
      background: #dd789e;
      transform: translateY(-1px);
    }

    .empty {
      text-align: center;
      background: rgba(255,255,255,.7);
      border-radius: 25px;
      padding: 28px 15px;
      font-weight: 700;
      color: #9c637d;
    }

    footer {
      text-align: center;
      margin-top: 35px;
      font-size: 14px;
      font-weight: 600;
      color: #99647c;
    }

    @media (max-width: 600px) {
      .page {
        width: 94%;
        padding-top: 18px;
      }

      .box {
        padding: 18px;
        border-radius: 24px;
      }

      .upload-btn {
        width: 100%;
      }
    }
  </style>
</head>

<body>

  <main class="page">

    <header>
      <div class="logo">Whimsical Corner 🍓</div>
      <div class="tagline">
        Cute little videos, all in one place ☘️🦭🐶🐰🪽🍄
      </div>
    </header>


    <!-- UPLOAD -->
    <section class="box">

      <h2 class="upload-title">Upload a Video 🪽</h2>

      <p class="upload-subtitle">
        Choose a video and add it to your corner 🍓
      </p>

      <div class="file-wrap">
        <input
          type="file"
          id="videoFile"
          accept="video/*"
        >
      </div>

      <button
        class="upload-btn"
        id="uploadBtn"
        type="button"
      >
        Upload Video 🍓
      </button>

      <div id="status"></div>

    </section>


    <!-- VIDEO GALLERY -->
    <section>

      <h2 class="section-title">
        Free Videos 🐰
      </h2>

      <div id="videos" class="videos"></div>

    </section>


    <footer>
      Whimsical Corner ☘️🍓🪽
    </footer>

  </main>


  <script>

    /* =====================================================
       CLOUDINARY SETTINGS
       ===================================================== */

    const CLOUD_NAME = "obptrfov";

    /*
      IMPORTANT:
      YAHAN APNA CLOUDINARY UNSIGNED UPLOAD PRESET LIKHO.

      Example:
      const UPLOAD_PRESET = "my_unsigned_preset";
    */

    const UPLOAD_PRESET = "YOUR_UNSIGNED_UPLOAD_PRESET";


    /* =====================================================
       EXISTING VIDEO
       ===================================================== */

    const existingVideos = [
      {
        name: "My Video 🍄",
        url: "https://res.cloudinary.com/obptrfov/video/upload/InShot_20260905_002656864.mp4"
      }
    ];


    /* =====================================================
       ELEMENTS
       ===================================================== */

    const fileInput = document.getElementById("videoFile");
    const uploadBtn = document.getElementById("uploadBtn");
    const status = document.getElementById("status");
    const videosContainer = document.getElementById("videos");


    /* =====================================================
       SHOW EXISTING VIDEO
       ===================================================== */

    function showExistingVideos() {

      videosContainer.innerHTML = "";

      if (existingVideos.length === 0) {
        showEmptyMessage();
        return;
      }

      existingVideos.forEach(function(video) {
        createVideoCard(video.url, video.name);
      });

    }


    /* =====================================================
       EMPTY MESSAGE
       ===================================================== */

    function showEmptyMessage() {

      videosContainer.innerHTML = `
        <div class="empty">
          Abhi koi video nahi hai 🦭<br>
          Upar se apna first video upload karo 🍓
        </div>
      `;

    }


    /* =====================================================
       CREATE VIDEO CARD
       ===================================================== */

    function createVideoCard(url, name) {

      const card = document.createElement("div");
      card.className = "video-card";

      const video = document.createElement("video");
      video.controls = true;
      video.preload = "metadata";

      const source = document.createElement("source");
      source.src = url;
      source.type = "video/mp4";

      video.appendChild(source);


      const title = document.createElement("div");
      title.className = "video-name";
      title.textContent = name + " 🍄";


      const download = document.createElement("a");
      download.className = "download-btn";
      download.href = url;
      download.target = "_blank";
      download.rel = "noopener";
      download.textContent = "Download Video 🐰";


      card.appendChild(video);
      card.appendChild(title);
      card.appendChild(download);

      videosContainer.prepend(card);

    }


    /* =====================================================
       UPLOAD VIDEO
       ===================================================== */

    uploadBtn.addEventListener("click", async function() {

      const file = fileInput.files[0];

      if (!file) {
        status.textContent = "Pehle ek video choose karo 🐶";
        return;
      }


      if (UPLOAD_PRESET === "YOUR_UNSIGNED_UPLOAD_PRESET") {

        status.textContent =
          "Cloudinary Upload Preset code mein add karo 🍓";

        return;
      }


      uploadBtn.disabled = true;
      uploadBtn.textContent = "Uploading... 🪽";
      status.textContent = "Video upload ho raha hai...";


      try {

        const formData = new FormData();

        formData.append("file", file);
        formData.append("upload_preset", UPLOAD_PRESET);


        const response = await fetch(
          `https://api.cloudinary.com/v1_1/${CLOUD_NAME}/video/upload`,
          {
            method: "POST",
            body: formData
          }
        );


        const data = await response.json();


        if (!response.ok) {
          throw new Error(
            data.error?.message || "Cloudinary upload failed"
          );
        }


        const videoUrl = data.secure_url;


        /*
          Uploaded video ko turant gallery mein add karo
        */

        createVideoCard(
          videoUrl,
          file.name
        );


        status.textContent =
          "Yay! Video upload ho gaya 🍓🪽";

        fileInput.value = "";


      } catch (error) {

        console.error(error);

        status.textContent =
          "Upload nahi hua. Cloudinary Upload Preset check karo 🦭";

      }


      uploadBtn.disabled = false;
      uploadBtn.textContent = "Upload Video 🍓";

    });


    /* =====================================================
       START PAGE
       ===================================================== */

    showExistingVideos();

  </script>

</body>
</html>
