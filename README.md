<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Smart Station Navigation</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f0f0f0; display:flex; justify-content:center; padding:50px; }
    .container { background:white; padding:30px; border-radius:15px; box-shadow:0 0 15px rgba(0,0,0,0.1); width:350px; text-align:center; }
    input { width:80%; padding:10px; margin-bottom:10px; border-radius:5px; border:1px solid #ccc; }
    button { padding:10px 20px; border:none; border-radius:5px; background:#007bff; color:white; cursor:pointer; }
    button:hover { background:#0056b3; }
    a.qr { display:block; margin-top:15px; text-decoration:none; color:#007bff; }
  </style>
</head>
<body>
  <div class="container">
    <h1>Smart Station Navigation</h1>
    <input type="text" id="destination" placeholder="Enter Destination (e.g., Platform 3)">
    <br>
    <button onclick="goToGoogle()">Go to Google Maps</button>
    <a id="qrLink" class="qr" target="_blank" href=""></a>
  </div>

  <script>
    function goToGoogle() {
      const destination = document.getElementById("destination").value.trim();
      if(destination === "") {
        alert("Please enter a destination!");
        return;
      }

      // Open Google Maps in new tab
      const mapsUrl = "https://www.google.com/maps/search/" + encodeURIComponent(destination);
      window.open(mapsUrl, "_blank");

      // Show QR link (can be scanned from phone)
      const qrLink = document.getElementById("qrLink");
      qrLink.href = mapsUrl;
      qrLink.textContent = "Or scan QR / open link: " + mapsUrl;
    }
  </script>
</body>
</html>
