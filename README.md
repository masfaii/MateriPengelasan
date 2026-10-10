<!DOCTYPE html>
<html lang="id">
<head>
<base target="_top">
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Belajar Las</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{--p:#4a1a78;--p2:#7a3fb6;--lav:#e8dcf8;--bg:#f5f1fa;--ink:#24113b;--mute:#7d7190;--ok:#2e9b62}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
body{margin:0;background:var(--p);font-family:Poppins,"Segoe UI",Arial,sans-serif;color:var(--ink);min-height:100vh;display:flex;justify-content:center}
#app{width:100%;max-width:460px;min-height:100vh;background:var(--bg);position:relative;padding:22px 20px 100px}
@media(min-width:600px){body{align-items:center;padding:24px}#app{min-height:0;height:min(880px,calc(100vh - 48px));overflow:auto;border-radius:34px;box-shadow:0 30px 70px rgba(0,0,0,.35)}}
.top{display:flex;justify-content:space-between;align-items:center}
.logo{width:42px;height:42px;border-radius:14px;background:var(--p);display:grid;place-items:center;font-size:21px}
.avatar{width:42px;height:42px;border-radius:50%;background:var(--lav);display:grid;place-items:center;font-size:20px}
h1{font-size:25px;font-weight:700;margin:20px 0 2px}
.sub{color:var(--mute);margin:0 0 16px;font-size:14px}
.search{display:flex;align-items:center;gap:10px;background:#fff;border:1.5px solid var(--lav);border-radius:16px;padding:0 14px}
.search input{border:0;outline:0;flex:1;padding:13px 0;font:inherit;font-size:14px;background:none}
.search:focus-within{border-color:var(--p2)}
.banner{margin:18px 0;background:var(--p);color:#fff;border-radius:22px;padding:20px;position:relative;overflow:hidden;min-height:140px}
.banner:before{content:"";position:absolute;right:-30px;bottom:-50px;width:190px;height:190px;border-radius:50%;background:var(--p2)}
.banner .em{position:absolute;right:22px;bottom:14px;font-size:68px}
.banner h2{margin:0 0 4px;font-size:21px;position:relative}
.banner p{margin:0 0 14px;font-size:13px;max-width:62%;opacity:.9;position:relative}
.pill{border:0;border-radius:12px;padding:7px 16px;font:inherit;font-size:12px;font-weight:600;background:var(--lav);color:var(--p);cursor:pointer;position:relative}
.row{display:flex;justify-content:space-between;align-items:baseline;margin-top:6px}
h3{margin:0;font-size:19px}
.chips{display:flex;gap:8px;overflow-x:auto;padding:12px 0;scrollbar-width:none}
.chips::-webkit-scrollbar{display:none}
.chip{flex:none;border:1.5px solid var(--lav);background:#fff;color:var(--mute);border-radius:20px;padding:6px 16px;font:inherit;font-size:13px;cursor:pointer}
.chip.on{background:var(--p);border-color:var(--p);color:#fff}
.card{display:flex;align-items:center;gap:14px;width:100%;text-align:left;background:#fff;border:0;border-radius:18px;padding:14px;margin-bottom:12px;cursor:pointer;font:inherit;box-shadow:0 4px 14px rgba(74,26,120,.07)}
.ic{flex:none;width:54px;height:54px;border-radius:16px;background:var(--lav);display:grid;place-items:center;font-size:26px}
.card b{display:block;font-size:14.5px;line-height:1.35}
.meta{font-size:12px;color:var(--mute);margin-top:3px}
.meta i{font-style:normal;color:#e0a21d}
.dn{margin-left:auto;color:var(--ok);font-size:20px}
nav{position:sticky;bottom:-100px}
.bar{position:fixed;bottom:0;left:50%;transform:translateX(-50%);width:100%;max-width:460px;background:#fff;display:flex;justify-content:space-around;padding:10px 0 14px;border-radius:24px 24px 0 0;box-shadow:0 -6px 20px rgba(74,26,120,.1);z-index:5}
@media(min-width:600px){.bar{position:sticky;bottom:-100px;left:0;transform:none;margin:0 -20px -100px;width:auto;max-width:none}}
.bar button{border:0;background:none;font:inherit;font-size:11.5px;color:var(--mute);display:flex;flex-direction:column;align-items:center;gap:2px;cursor:pointer;padding:4px 26px}
.bar button span{font-size:22px;filter:grayscale(1);opacity:.6}
.bar button.on{color:var(--p);font-weight:600}.bar button.on span{filter:none;opacity:1}
.back{border:0;background:#fff;width:40px;height:40px;border-radius:14px;font-size:18px;cursor:pointer;color:var(--p)}
.tag{display:inline-block;background:var(--lav);color:var(--p);font-size:12px;font-weight:600;border-radius:10px;padding:3px 12px;margin-top:16px}
.dh{font-size:23px;line-height:1.3;margin:8px 0}
.sum{background:var(--p);color:#fff;border-radius:18px;padding:16px;font-size:14px;margin:12px 0 16px}
.pt{display:flex;gap:12px;background:#fff;border-radius:14px;padding:12px 14px;margin-bottom:9px;font-size:14px;line-height:1.55}
.pt u{flex:none;width:24px;height:24px;border-radius:50%;background:var(--lav);color:var(--p);display:grid;place-items:center;font-size:12px;font-weight:700;text-decoration:none}
.tip{background:#fff6dc;border-radius:14px;padding:12px 14px;font-size:13.5px;margin:14px 0}
.cta{width:100%;border:0;border-radius:16px;padding:15px;font:inherit;font-weight:600;font-size:15px;background:var(--p);color:#fff;cursor:pointer;margin-top:6px}
.cta.alt{background:var(--lav);color:var(--p)}
.nx{display:flex;gap:10px;margin-top:10px}.nx .cta{margin:0}
.big{font-size:42px;font-weight:700;color:var(--p);margin:6px 0}
.pb{height:10px;background:var(--lav);border-radius:6px;overflow:hidden;margin:6px 0 4px}.pb i{display:block;height:100%;background:var(--p2);border-radius:6px;transition:width .3s}
.pg{background:#fff;border-radius:18px;padding:14px 16px;margin-bottom:12px;font-size:14px}
.empty{text-align:center;color:var(--mute);padding:30px 0;font-size:14px}
button:focus-visible{outline:3px solid var(--p2);outline-offset:2px}
@media(prefers-reduced-motion:reduce){*{transition:none!important}}
</style>
</head>
<body>
<div id="app"><div class="empty">Memuat materi...</div></div>
<script>
const ICON={Dasar:'🔥',Persiapan:'🧰',Proses:'⚡',Teknik:'🎯',Mutu:'🔍',Selesai:'✅'};
let D=[],tab='home',stage='Semua',q='',det=-1,done={};
const A=document.getElementById('app');
const esc=s=>String(s==null?'':s).replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
try{done=JSON.parse(localStorage.getItem('las_done')||'{}')}catch(e){}
const save=()=>{try{localStorage.setItem('las_done',JSON.stringify(done))}catch(e){}};
const nDone=()=>D.filter(m=>done[m.no]).length;

google.script.run.withSuccessHandler(d=>{D=d;draw()})
 .withFailureHandler(e=>{A.innerHTML='<div class="empty">Gagal memuat materi.<br>'+esc(e.message)+'<br>Jalankan setupSheet() lalu muat ulang.</div>'})
 .getMateri();

function bar(){return '<div class="bar"><button data-t="home" class="'+(tab==='home'?'on':'')+'"><span>🏠</span>Beranda</button><button data-t="prog" class="'+(tab==='prog'?'on':'')+'"><span>📈</span>Progres</button></div>'}
function card(m,i){return '<button class="card" data-i="'+i+'"><div class="ic">'+(ICON[m.tahap]||'🔧')+'</div><div><b>'+esc(m.judul)+'</b><div class="meta"><i>★</i> '+esc(m.tahap)+' &middot; '+m.poin.length+' poin</div></div>'+(done[m.no]?'<span class="dn">✓</span>':'')+'</button>'}

function draw(){
  if(det>=0)return drawDet();
  if(tab==='prog')return drawProg();
  const stages=['Semua',...new Set(D.map(m=>m.tahap))];
  const next=D.findIndex(m=>!done[m.no]);
  let list=D.map((m,i)=>[m,i]).filter(([m])=>(stage==='Semua'||m.tahap===stage)&&(!q||(m.judul+m.ringkasan+m.poin.join(' ')).toLowerCase().includes(q)));
  A.innerHTML='<div class="top"><div class="logo">🔥</div><div class="avatar">👷</div></div>'
  +'<h1>Halo, Calon Welder!</h1><p class="sub">Mau belajar las apa hari ini?</p>'
  +'<label class="search">🔎<input id="q" type="search" placeholder="Cari materi, mis. porositas" value="'+esc(q)+'"></label>'
  +'<div class="banner"><h2>'+(next<0?'Hebat, semua selesai!':(nDone()?'Lanjutkan belajar':'Materi baru!'))+'</h2><p>'+(next<0?'Ulangi materi kapan saja.':esc(D[next].judul))+'</p><button class="pill" id="go">'+(next<0?'Lihat progres':'Mulai sekarang')+'</button><div class="em">🧑‍🏭</div></div>'
  +'<div class="row"><h3>Materi</h3></div><div class="chips">'+stages.map(s=>'<button class="chip '+(s===stage?'on':'')+'" data-s="'+s+'">'+s+'</button>').join('')+'</div>'
  +(list.length?list.map(([m,i])=>card(m,i)).join(''):'<div class="empty">Tidak ada materi yang cocok.</div>')+bar();
  bind();
  const qi=document.getElementById('q');qi.oninput=()=>{q=qi.value.toLowerCase();const p=qi.selectionStart;draw();const n=document.getElementById('q');n.focus();n.setSelectionRange(p,p)};
  document.getElementById('go').onclick=()=>next<0?(tab='prog',draw()):open(next);
}
function bind(){
  A.querySelectorAll('[data-t]').forEach(b=>b.onclick=()=>{tab=b.dataset.t;det=-1;draw();A.scrollTop=0});
  A.querySelectorAll('[data-s]').forEach(b=>b.onclick=()=>{stage=b.dataset.s;draw()});
  A.querySelectorAll('[data-i]').forEach(b=>b.onclick=()=>open(+b.dataset.i));
}
function open(i){det=i;draw();A.scrollTop=0;window.scrollTo(0,0)}
function drawDet(){
  const m=D[det],d=!!done[m.no];
  A.innerHTML='<div class="top"><button class="back" id="bk" aria-label="Kembali">←</button><div class="avatar">'+(ICON[m.tahap]||'🔧')+'</div></div>'
  +'<span class="tag">'+esc(m.tahap)+'</span><h2 class="dh">'+esc(m.judul)+'</h2><div class="sum">'+esc(m.ringkasan)+'</div>'
  +m.poin.map((p,k)=>'<div class="pt"><u>'+(k+1)+'</u><span>'+esc(p)+'</span></div>').join('')
  +(m.tips?'<div class="tip">💡 <b>Tips:</b> '+esc(m.tips)+'</div>':'')
  +'<button class="cta '+(d?'alt':'')+'" id="mk">'+(d?'✓ Selesai (ketuk untuk batal)':'Tandai selesai')+'</button>'
  +'<div class="nx"><button class="cta alt" id="pv"'+(det===0?' disabled style="opacity:.4"':'')+'>Sebelumnya</button><button class="cta" id="nx"'+(det===D.length-1?' disabled style="opacity:.4"':'')+'>Berikutnya</button></div>'+bar();
  bind();
  document.getElementById('bk').onclick=()=>{det=-1;draw()};
  document.getElementById('mk').onclick=()=>{done[m.no]=!done[m.no];save();draw()};
  document.getElementById('pv').onclick=()=>det>0&&open(det-1);
  document.getElementById('nx').onclick=()=>det<D.length-1&&open(det+1);
}
function drawProg(){
  const n=nDone(),pc=D.length?Math.round(n/D.length*100):0,st=[...new Set(D.map(m=>m.tahap))];
  A.innerHTML='<div class="top"><div class="logo">📈</div><div class="avatar">👷</div></div><h1>Progres belajar</h1><p class="sub">'+n+' dari '+D.length+' materi selesai</p>'
  +'<div class="pg"><div class="big">'+pc+'%</div><div class="pb"><i style="width:'+pc+'%"></i></div></div>'
  +st.map(s=>{const a=D.filter(m=>m.tahap===s),b=a.filter(m=>done[m.no]).length;return '<div class="pg"><b>'+(ICON[s]||'🔧')+' '+esc(s)+'</b><div class="pb"><i style="width:'+(b/a.length*100)+'%"></i></div><span class="meta">'+b+' / '+a.length+' materi</span></div>'}).join('')+bar();
  bind();
}
</script>
</body>
</html>
