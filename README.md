<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GHOST SEARCH - Private</title>
<style>
body{margin:0;background:#080a0f;color:#fff;font-family:sans-serif;min-height:100vh;display:flex;flex-direction:column}
.top{padding:14px 16px;border-bottom:1px solid #1a1f2e;display:flex;justify-content:space-between;align-items:center}
.logo{font-weight:900;letter-spacing:2px}
.logo span{color:#00ffd0}
.vpn{font-size:11px;border:1px solid #00ffd044;background:#0f1a15;padding:5px 10px;border-radius:20px}
.hero{flex:1;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:20px;text-align:center}
h1{font-size:32px;margin:0 0 10px} h1 b{color:#00ffd0}
.box{width:100%;max-width:600px;background:#121624;border:1px solid #232a42;border-radius:14px;display:flex;padding:5px;margin-top:20px}
.box input{flex:1;background:transparent;border:none;outline:none;color:#fff;font-size:16px;padding:12px}
.box button{background:#00ffd0;color:#000;border:none;border-radius:10px;padding:0 20px;font-weight:bold}
.opts{margin-top:15px;display:flex;gap:8px;flex-wrap:wrap;justify-content:center;font-size:12px}
.pill{background:#121624;border:1px solid #232a42;padding:6px 12px;border-radius:20px}
select{background:transparent;color:#fff;border:none}
.foot{padding:15px;text-align:center;color:#555;font-size:11px}
</style>
</head>
<body>
<div class="top">
<div class="logo">GHOST <span>SEARCH</span></div>
<div class="vpn">🟢 VPN: SG • 185.199.xxx • No Log</div>
</div>
<div class="hero">
<h1>Cari <b>Bebas</b> Tanpa Jejak</h1>
<p style="color:#8b95b0;font-size:13px">Tanpa SafeSearch • Tanpa History • 100% tidak disimpan</p>
<div class="box">
<input id="q" placeholder="Ketik pencarian bebas..." autocomplete="off">
<button onclick="search()">CARI</button>
</div>
<div class="opts">
<div class="pill">🚫 SafeSearch: OFF</div>
<div class="pill">🕵️ History: OFF</div>
<div class="pill">Engine: 
<select id="engine">
<option value="duck">DuckDuckGo</option>
<option value="brave">Brave</option>
<option value="google">Google</option>
</select>
</div>
</div>
</div>
<div class="foot">Frontend only - tidak pakai localStorage. Refresh = hilang.</div>
<script>
function search(){
let q=document.getElementById('q').value;
let e=document.getElementById('engine').value;
if(!q)return;
let url="";
if(e=="duck") url=`https://duckduckgo.com/?q=${encodeURIComponent(q)}&kp=-2`;
else if(e=="brave") url=`https://search.brave.com/search?q=${encodeURIComponent(q)}&safesearch=off`;
else url=`https://www.google.com/search?q=${encodeURIComponent(q)}&safe=off&pws=0`;
window.open(url,'_blank');
document.getElementById('q').value="";
}
document.getElementById('q').addEventListener('keydown',function(a){if(a.key=="Enter")search()});
</script>
</body>
</html>
