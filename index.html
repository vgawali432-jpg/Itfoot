
<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>WORLD BRAIN AI</title>
<style>
body {
  margin:0; padding:20px;
  background:#07111f; color:#eaf6ff;
  font-family:Arial,sans-serif;
}
h1 {color:#42d9ff;text-align:center}
.card {
  background:#10243a; padding:16px;
  border-radius:15px; margin:14px 0;
}
button,input {
  padding:13px; border:0; border-radius:9px;
  font-size:16px; margin:5px;
}
button {background:#13bde8;color:#001321}
input {width:90%;background:#eaf6ff}
#answer {white-space:pre-wrap;line-height:1.6}
.small {color:#9bb6ca;font-size:13px}
</style>
</head>
<body>

<h1>🌍 WORLD BRAIN AI</h1>
<p style="text-align:center">Your Personal World Intelligence</p>

<div class="card">
<h3>🎙️ Voice Assistant</h3>
<button onclick="listen()">बोलकर पूछो</button>
<p id="heard">आपकी आवाज का इंतजार है...</p>
</div>

<div class="card">
<h3>⌨️ Ask WORLD BRAIN</h3>
<input id="question" placeholder="जैसे: Weather in Mumbai">
<button onclick="ask()">ASK</button>
</div>

<div class="card">
<h3>🧠 WORLD BRAIN RESPONSE</h3>
<p id="answer">नमस्ते! मुझसे दुनिया के बारे में पूछो।</p>
</div>

<div class="card">
<h3>🕒 World Clock</h3>
<div id="clocks"></div>
</div>

<p class="small">Weather data: Open-Meteo | Knowledge: Wikipedia</p>

<script>
const answer = document.getElementById("answer");

function speak(text) {
  if (!("speechSynthesis" in window)) return;
  speechSynthesis.cancel();
  let msg = new SpeechSynthesisUtterance(text);
  msg.lang = "hi-IN";
  speechSynthesis.speak(msg);
}

function show(text) {
  answer.innerText = text;
  speak(text);
}

function updateClocks() {
  const places = [
    ["India","Asia/Kolkata"],
    ["London","Europe/London"],
    ["New York","America/New_York"],
    ["Tokyo","Asia/Tokyo"],
    ["Dubai","Asia/Dubai"],
    ["Sydney","Australia/Sydney"]
  ];
  document.getElementById("clocks").innerHTML =
    places.map(p => p[0] + ": " +
    new Intl.DateTimeFormat("en-IN", {
      timeZone:p[1], hour:"2-digit",
      minute:"2-digit",second:"2-digit"
    }).format(new Date())).join("<br>");
}
updateClocks();
setInterval(updateClocks,1000);

async function weather(city) {
  show(city + " का मौसम खोज रहा हूँ...");
  try {
    const geo = await fetch(
      "https://geocoding-api.open-meteo.com/v1/search?name=" +
      encodeURIComponent(city) + "&count=1&language=en&format=json"
    ).then(r=>r.json());

    if (!geo.results?.length) {
      show("यह शहर नहीं मिला। शहर का नाम दोबारा बोलो।");
      return;
    }

    const p = geo.results[0];
    const data = await fetch(
      `https://api.open-meteo.com/v1/forecast?latitude=${p.latitude}&longitude=${p.longitude}&current=temperature_2m,relative_humidity_2m,apparent_temperature,wind_speed_10m`
    ).then(r=>r.json());

    const c = data.current;
    show(`${p.name}, ${p.country}
तापमान: ${c.temperature_2m}°C
महसूस होने वाला तापमान: ${c.apparent_temperature}°C
नमी: ${c.relative_humidity_2m}%
हवा की गति: ${c.wind_speed_10m} km/h`);
  } catch(e) {
    show("मौसम डेटा नहीं मिल पाया। इंटरनेट जाँचो।");
  }
}

async function knowledge(query) {
  try {
    const url = "https://en.wikipedia.org/w/api.php?action=query&list=search&srsearch=" +
      encodeURIComponent(query) +
      "&format=json&origin=*";
    const result = await fetch(url).then(r=>r.json());
    const item = result.query.search[0];
    if (!item) {
      show("इस विषय की जानकारी नहीं मिली।");
      return;
    }
    const summary = await fetch(
      "https://en.wikipedia.org/api/rest_v1/page/summary/" +
      encodeURIComponent(item.title)
    ).then(r=>r.json());

    show(summary.extract || "जानकारी उपलब्ध नहीं है।");
  } catch(e) {
    show("जानकारी लाने में समस्या हुई।");
  }
}

async function ask() {
  const q = document.getElementById("question").value.trim();
  if (!q) return;

  const lower = q.toLowerCase();

  if (lower.includes("weather") ||
      lower.includes("temperature") ||
      lower.includes("मौसम") ||
      lower.includes("तापमान")) {
    let city = q.replace(
      /weather|temperature|मौसम|तापमान|in|का|में|है|\?/gi,""
    ).trim();
    if (!city) city = "Mumbai";
    await weather(city);
  }
  else if (lower.includes("time") ||
           lower.includes("समय") ||
           lower.includes("बजे")) {
    show("World Clock में अलग-अलग शहरों का लाइव समय देखो।");
  }
  else {
    await knowledge(q);
  }
}

function listen() {
  const SR = window.SpeechRecognition ||
             window.webkitSpeechRecognition;

  if (!SR) {
    show("इस ब्राउज़र में Voice Recognition उपलब्ध नहीं है। Chrome में कोशिश करो।");
    return;
  }

  const rec = new SR();
  rec.lang = "hi-IN";
  rec.interimResults = false;

  document.getElementById("heard").innerText =
    "🎙️ सुन रहा हूँ...";

  rec.onresult = e => {
    const text = e.results[0][0].transcript;
    document.getElementById("heard").innerText = text;
    document.getElementById("question").value = text;
    ask();
  };

  rec.onerror = () => {
    document.getElementById("heard").innerText =
      "आवाज नहीं समझ पाया। दोबारा कोशिश करो।";
  };

  rec.start();
}
</script>
</body>
</html>
