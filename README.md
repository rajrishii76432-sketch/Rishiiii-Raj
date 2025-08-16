<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>My Love Letter to Kitty 💌</title>
<style>
  :root { --bg:#0f0f14; --fg:#fff; --pink:#ff4d88; }
  body {
    margin:0; padding:0;
    min-height:100vh;
    display:flex; justify-content:center; align-items:center;
    background: radial-gradient(circle at top, #1a1a22, #0f0f14);
    font-family: "Georgia", serif; color: var(--fg);
    overflow:hidden;
  }
  .card {
    max-width:700px; padding:32px 28px;
    background:rgba(255,255,255,0.05);
    border-radius:20px; backdrop-filter:blur(10px);
    box-shadow:0 10px 40px rgba(0,0,0,.6);
    position:relative; text-align:left;
    z-index:1;
  }
  h1 { font-size:2rem; text-align:center; color:var(--pink); margin-bottom:1rem; }
  p { line-height:1.6; font-size:1.05rem; margin:0 0 1rem; }
  .counter { margin-top:1rem; text-align:center; font-style:italic; color:#ccc; }
  .footer { margin-top:1.2rem; text-align:right; font-weight:bold; color:var(--pink);}
  /* Floating hearts */
  .float { position:absolute; inset:0; overflow:hidden; pointer-events:none; z-index:0; }
  .float span {
    position:absolute; font-size:18px; color:var(--pink);
    animation:fall 8s linear infinite;
    opacity:.85;
  }
  @keyframes fall {
    0% { transform:translateY(-20vh) rotate(0deg); opacity:0; }
    10%{ opacity:1; }
    100%{ transform:translateY(120vh) rotate(360deg); opacity:0.9; }
  }
</style>
</head>
<body>
  <div class="card">
    <h1>For My Kitty 💖</h1>
    <p>Sometimes, words seem so small compared to what I feel for you, but I’ll try my best to capture the love that fills my heart whenever I think of you. You’re not only my girlfriend but also my partner, my inspiration, and my constant.</p>
    <p>Every day, I find more reasons to appreciate you, admire you, and, most importantly, love you even more.</p>
    <p>When I say “I love you,” I mean that I see everything beautiful in you—your kindness, your dreams, and even your unique quirks. I love how thoughtful you are, how you push yourself despite your struggles, and how you constantly strive to be your best.</p>
    <p>You remind me of the strength and resilience it takes to face challenges head-on, and I’m so proud of you for everything you accomplish, even if you can’t always see it yourself.</p>
    <p class="counter" id="counter"></p>
    <div class="footer">Forever yours,<br>Bubu 💕</div>
  </div>
  <div class="float" id="float"></div>

<script>
  // Personalize
  const herName  = "Kitty";
  const fromName = "Bubu";
  const sinceISO = "2024-10-19";

  // Days counter
  function daysSince(iso){
    const start = new Date(iso+"T00:00:00");
    const now   = new Date();
    const msPerDay = 24*60*60*1000;
    return Math.floor((now - start) / msPerDay);
  }
  const d = daysSince(sinceISO);
  const sinceDate = new Date(sinceISO+"T00:00:00");
  const niceDate = sinceDate.toLocaleDateString(undefined,{day:"2-digit",month:"short",year:"numeric"});
  document.getElementById("counter").textContent =
    `We’ve been us for ${d} day${d===1?"":"s"} — since ${niceDate}. 💞`;

  // Floating hearts
  const float = document.getElementById("float");
  const glyphs = ["💗","💞","💘","💕","💖","🌸","✨","⭐️"];
  function drop(){
    const s = document.createElement("span");
    s.textContent = glyphs[Math.floor(Math.random()*glyphs.length)];
    s.style.left = Math.random()*100 + "%";
    s.style.animationDuration = (5 + Math.random()*5) + "s";
    s.style.fontSize = (16 + Math.random()*26) + "px";
    float.appendChild(s);
    setTimeout(()=>s.remove(), 10000);
  }
  setInterval(drop, 250);
</script>
</body>
</html>
