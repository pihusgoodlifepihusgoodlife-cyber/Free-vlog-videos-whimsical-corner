<!DOCTYPE html>
<html>
<head>
  <title>Free Videos</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
</head>

<body>

  <h1>🎬 Free Videos</h1>
  <p>Welcome! Free videos yahan milenge.</p>

  <h2>Upload Video</h2>

  <input type="file" id="videoFile" accept="video/*">
  <button onclick="showVideo()">Add Video</button>

  <div id="videoBox"></div>

  <script>
    function showVideo() {
      const file = document.getElementById("videoFile").files[0];

      if (!file) {
        alert("Pehle video select karo.");
        return;
      }

      const url = URL.createObjectURL(file);

      document.getElementById("videoBox").innerHTML = `
        <h2>${file.name}</h2>

        <video width="100%" controls>
          <source src="${url}" type="${file.type}">
        </video>

        <br><br>

        <a href="${url}" download="${file.name}">
          ⬇️ Download Video
        </a>
      `;
    }
  </script>

</body>
</html>
