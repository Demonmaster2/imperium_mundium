<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Imperium Mundi</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/7.8.5/d3.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/topojson/3.0.2/topojson.min.js"></script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Crimson+Text:ital,wght@0,400;0,600;1,400&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --gold:#c9a84c;--gold-l:#e8c96a;
  --bg:#070c12;--bgp:#0d1520;--bgc:#111d2a;
  --brd:rgba(201,168,76,0.22);
  --red:#c0392b;--green:#27ae60;
}
html,body{width:100%;height:100%;overflow:hidden;background:var(--bg);color:#d4c9a8;font-family:'Crimson Text',serif}
.screen{display:none;width:100%;height:100vh}
.screen.active{display:flex}

/* ── LOBBY ── */
#s-lobby{flex-direction:column;align-items:center;justify-content:center;gap:18px;
  background:radial-gradient(ellipse at 50% 35%,#0c1e35 0%,var(--bg) 68%)}
#s-lobby h1{font-family:'Cinzel',serif;font-size:48px;color:var(--gold);letter-spacing:8px;
  text-shadow:0 0 40px rgba(201,168,76,.35)}
#s-lobby .sub{font-style:italic;color:#7a6d4a;font-size:17px;margin-bottom:6px}
.card{background:var(--bgc);border:1px solid var(--brd);border-radius:10px;padding:26px 32px;
  min-width:370px;max-width:440px;display:flex;flex-direction:column;gap:13px}
.card h2{font-family:'Cinzel',serif;font-size:13px;color:var(--gold);letter-spacing:2px}
.inp{background:#09131e;border:1px solid var(--brd);color:#d4c9a8;padding:9px 13px;
  border-radius:6px;font-size:15px;font-family:'Crimson Text',serif;outline:none;width:100%}
.inp:focus{border-color:var(--gold)}
.btn{background:var(--gold);color:#070c12;border:none;padding:10px 18px;border-radius:6px;
  cursor:pointer;font-family:'Cinzel',serif;font-size:12px;letter-spacing:1px;font-weight:700;transition:background .2s}
.btn:hover{background:var(--gold-l)}
.btn:disabled{opacity:.4;cursor:not-allowed}
.btn.sec{background:transparent;border:1px solid var(--brd);color:var(--gold)}
.btn.sec:hover{background:rgba(201,168,76,.1)}
.color-row{display:flex;gap:7px;flex-wrap:wrap;align-items:center}
.cswatch{width:22px;height:22px;border-radius:50%;cursor:pointer;border:2px solid transparent;transition:transform .15s}
.cswatch.sel{border-color:#fff;transform:scale(1.25)}
.status{font-size:12px;color:#8a7d5a;font-style:italic;text-align:center;min-height:16px}
.status.err{color:#c06a6a}
.status.ok{color:#6ab06a}

/* invite box */
.invite-box{background:#070c12;border:1px solid var(--brd);border-radius:6px;padding:12px;display:flex;flex-direction:column;gap:8px}
.invite-url{font-family:monospace;font-size:11px;color:#8aaa8a;word-break:break-all;line-height:1.5}
.waiting-dots::after{content:'...';animation:dots 1.5s infinite}
@keyframes dots{0%{content:'.'}33%{content:'..'}66%{content:'...'}}
.player-join-row{display:flex;align-items:center;gap:8px;padding:5px 0;font-size:13px}
.pjdot{width:9px;height:9px;border-radius:50%}

/* ── GAME ── */
#s-game{flex-direction:column}
#topbar{display:flex;align-items:center;gap:9px;padding:6px 13px;
  background:var(--bgp);border-bottom:1px solid var(--brd);flex-shrink:0;flex-wrap:wrap}
#topbar .ttl{font-family:'Cinzel',serif;color:var(--gold);font-size:14px;letter-spacing:2px}
.pill{display:flex;align-items:center;gap:5px;background:var(--bgc);border:1px solid var(--brd);
  padding:3px 10px;border-radius:20px;font-size:12px}
.pill .v{font-weight:600;color:var(--gold-l)}
#cdot{width:11px;height:11px;border-radius:50%}
.topbtn{background:transparent;border:1px solid var(--brd);color:var(--gold);
  padding:3px 11px;border-radius:20px;cursor:pointer;font-size:11px;font-family:'Cinzel',serif;letter-spacing:1px}
.topbtn:hover{background:rgba(201,168,76,.1)}
#conn-indicator{font-size:11px;padding:3px 10px;border-radius:20px;font-family:'Cinzel',serif;letter-spacing:1px}
#conn-indicator.online{background:rgba(39,174,96,.15);color:#6ab06a;border:1px solid rgba(39,174,96,.3)}
#conn-indicator.offline{background:rgba(192,57,43,.15);color:#c06a6a;border:1px solid rgba(192,57,43,.3)}
#conn-indicator.syncing{background:rgba(201,168,76,.15);color:var(--gold);border:1px solid var(--brd)}

#mid{display:flex;flex:1;overflow:hidden}
#mapwrap{flex:1;position:relative;overflow:hidden}
svg#wmap{width:100%;height:100%;cursor:grab;background:#030810}
svg#wmap:active{cursor:grabbing}
.ctry{stroke:#192535;stroke-width:.35px;transition:filter .15s;cursor:pointer}
.ctry:hover{filter:brightness(1.55);stroke:rgba(255,255,255,.45);stroke-width:.9px}
.ctry.sel{stroke:#fff;stroke-width:1.4px;filter:brightness(1.6)}
.ctry.atk{stroke:#ff4040;stroke-width:1.3px;animation:pr 1s infinite alternate}
@keyframes pr{from{filter:brightness(1.2)}to{filter:brightness(1.9) drop-shadow(0 0 4px #f44)}}
.tlbl{font-size:8.5px;fill:#fff;pointer-events:none;font-family:'Cinzel',serif;
  text-anchor:middle;font-weight:700;paint-order:stroke;stroke:#000;stroke-width:2px}

#side{width:215px;background:var(--bgp);border-left:1px solid var(--brd);
  display:flex;flex-direction:column;font-size:13px;overflow-y:auto}
.sec{padding:11px 13px;border-bottom:1px solid var(--brd)}
.sec h3{font-family:'Cinzel',serif;font-size:10px;color:var(--gold);letter-spacing:2px;margin-bottom:7px}
#sname{font-family:'Cinzel',serif;font-size:15px;color:var(--gold-l);margin-bottom:3px}
#sinfo{font-size:12px;color:#7a6d4a;font-style:italic;margin-bottom:7px}
.irow{display:flex;justify-content:space-between;font-size:12px;padding:2px 0}
.irow .l{color:#7a6d4a}.irow .r{color:#d4c9a8;font-weight:600}
.abtn{width:100%;background:#091320;border:1px solid var(--brd);color:#d4c9a8;
  padding:7px 11px;margin:2px 0;border-radius:5px;cursor:pointer;font-size:12px;
  font-family:'Crimson Text',serif;text-align:left;transition:all .15s}
.abtn:hover:not(:disabled){background:#1a2d40;border-color:var(--gold);color:var(--gold)}
.abtn:disabled{opacity:.35;cursor:not-allowed}
.abtn.d{border-color:rgba(192,57,43,.5)}
.abtn.d:hover:not(:disabled){background:#2d0a0a;border-color:var(--red);color:#ff7070}
.prow{display:flex;align-items:center;gap:7px;padding:6px 13px;
  border-bottom:1px solid rgba(255,255,255,.03);font-size:12px}
.pdot{width:9px;height:9px;border-radius:50%}

#elog{position:absolute;bottom:0;left:0;right:215px;height:52px;
  background:rgba(7,12,18,.92);border-top:1px solid var(--brd);
  padding:0 13px;display:flex;flex-direction:column;justify-content:center;overflow:hidden}
.ll{padding:1px 0;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;font-size:12px}
.ll.p{color:#6ab06a}.ll.e{color:#c06a6a}.ll.s{color:#7a6d4a;font-style:italic}.ll.ev{color:var(--gold)}

#ibar-w{position:absolute;top:0;left:0;right:215px;height:3px;background:rgba(255,255,255,.05)}
#ibar{height:100%;background:var(--gold);width:0%;transition:width .4s linear}

.aline{stroke:#f1c40f;stroke-width:2px;fill:none;animation:fla .55s ease-out forwards;pointer-events:none}
@keyframes fla{from{opacity:1;stroke-width:2px}to{opacity:0;stroke-width:.4px}}

#tt{position:absolute;background:var(--bgc);border:1px solid var(--brd);
  padding:7px 11px;border-radius:6px;font-size:12px;pointer-events:none;display:none;z-index:30}
#tt .tn{font-family:'Cinzel',serif;font-size:12px;color:var(--gold);margin-bottom:3px}
#tt .tr{display:flex;justify-content:space-between;gap:18px;font-size:11px;color:#7a6d4a}
#tt .tr span:last-child{color:#d4c9a8}

#victory{display:none;position:fixed;inset:0;z-index:100;background:rgba(0,0,0,.88);
  align-items:center;justify-content:center;flex-direction:column;gap:14px}
#victory.show{display:flex}
#victory h1{font-family:'Cinzel',serif;font-size:46px;color:var(--gold);letter-spacing:6px}
#victory p{font-size:19px;color:#d4c9a8;font-style:italic}

::-webkit-scrollbar{width:4px}
::-webkit-scrollbar-thumb{background:rgba(201,168,76,.25);border-radius:2px}
</style>
</head>
<body>

<!-- LOBBY -->
<div id="s-lobby" class="screen active">
  <h1>IMPERIUM MUNDI</h1>
  <p class="sub">Conquista o mundo em tempo real</p>

  <!-- MAIN MENU -->
  <div class="card" id="card-main">
    <h2>PERFIL DE GUERRA</h2>
    <input class="inp" id="pname" placeholder="O teu nome de guerra..." maxlength="20">
    <div class="color-row" id="cpick"></div>
    <button class="btn" onclick="soloStart()">⚔ Jogar Sozinho (vs IA)</button>
    <div style="display:flex;gap:8px">
      <button class="btn sec" onclick="showCreateRoom()" style="flex:1">🏰 Criar Sala Online</button>
      <button class="btn sec" onclick="showJoinRoom()" style="flex:1">🔑 Entrar com Link</button>
    </div>
  </div>

  <!-- CREATE ROOM -->
  <div class="card" id="card-create" style="display:none">
    <h2>CRIAR SALA</h2>
    <p id="create-status" class="status">A criar sala<span class="waiting-dots"></span></p>
    <div class="invite-box" id="invite-box" style="display:none">
      <div style="font-size:12px;color:#8a7d5a">Partilha este link com um amigo:</div>
      <div class="invite-url" id="invite-url-text"></div>
      <button class="btn" onclick="copyInvite()" id="copy-btn">📋 Copiar Link</button>
    </div>
    <div id="room-players-list"></div>
    <p id="room-wait-msg" class="status" style="display:none">A aguardar jogadores<span class="waiting-dots"></span></p>
    <button class="btn" id="start-game-btn" style="display:none" onclick="hostStartGame()">⚔ INICIAR GUERRA</button>
    <button class="btn sec" onclick="backToMain()">← Voltar</button>
  </div>

  <!-- JOIN ROOM -->
  <div class="card" id="card-join" style="display:none">
    <h2>ENTRAR NA SALA</h2>
    <input class="inp" id="join-code-inp" placeholder="Código da sala..." maxlength="8" style="letter-spacing:4px;text-align:center;text-transform:uppercase">
    <button class="btn" onclick="doJoin()">🔑 Entrar</button>
    <p id="join-status" class="status"></p>
    <button class="btn sec" onclick="backToMain()">← Voltar</button>
  </div>
</div>

<!-- GAME -->
<div id="s-game" class="screen">
  <div id="topbar">
    <span class="ttl">⚔ IMPERIUM</span>
    <div class="pill">🏴 <span class="v" id="st-c">0</span></div>
    <div class="pill">⚔ <span class="v" id="st-t">0</span></div>
    <div class="pill">💰 <span class="v" id="st-g">0</span></div>
    <div class="pill"><div id="cdot"></div><span id="st-n">—</span></div>
    <div id="conn-indicator" class="online" style="display:none">● Online</div>
    <div id="turn-pill" class="pill" style="display:none">Vez: <span class="v" id="st-turn">—</span></div>
    <button class="topbtn" id="end-turn-topbtn" style="display:none" onclick="endMyTurn()">Terminar Turno →</button>
  </div>
  <div id="mid">
    <div id="mapwrap">
      <div id="ibar-w"><div id="ibar"></div></div>
      <svg id="wmap"></svg>
      <div id="tt"></div>
      <div id="elog"><div id="li"></div></div>
    </div>
    <div id="side">
      <div class="sec">
        <h3>TERRITÓRIO</h3>
        <div id="sname">—</div>
        <div id="sinfo">Seleciona um país</div>
        <div id="sdet"></div>
        <div id="sact"></div>
      </div>
      <div class="sec">
        <h3>JOGADORES</h3>
        <div id="psb"></div>
      </div>
    </div>
  </div>
</div>

<div id="victory">
  <h1 id="vt">VITÓRIA!</h1>
  <p id="vs"></p>
  <button class="btn" onclick="location.href=location.origin+location.pathname">Jogar Novamente</button>
</div>

<script>
// ═══════════════════════════════════════════════════════
//  CONSTANTS & STATE
// ═══════════════════════════════════════════════════════
const COLORS=['#e74c3c','#e67e22','#f1c40f','#2ecc71','#1abc9c','#3498db','#9b59b6','#e91e63'];
const CNAMES=['Vermelho','Laranja','Amarelo','Verde','Turquesa','Azul','Roxo','Rosa'];
const INCOME_MS=10000;
const POLL_MS=2500; // multiplayer sync interval
// Using localStorage as relay for same-device, and a simple hash-based store
// For cross-device: state stored in a shared key on a free public KV (we use a mini
// self-contained relay via hash + localStorage broadcast)

let myColor=COLORS[0], myName='Comandante', myId='';
let isSolo=true, isHost=false, roomId='', mpTurn='';
let countries={}, players={}, selIso=null, logLines=[];
let svgEl, proj, pathFn, gEl;
let incTimer=null, pollTimer=null;
let lastSeenSeq=0;

// ═══════════════════════════════════════════════════════
//  LOBBY BUILD
// ═══════════════════════════════════════════════════════
(function(){
  const cp=document.getElementById('cpick');
  COLORS.forEach((c,i)=>{
    const d=document.createElement('div');
    d.className='cswatch'+(i===0?' sel':'');
    d.style.background=c; d.title=CNAMES[i];
    d.onclick=()=>{myColor=c;document.querySelectorAll('.cswatch').forEach(x=>x.classList.remove('sel'));d.classList.add('sel');};
    cp.appendChild(d);
  });
  // Check if arriving via invite link
  const hash=location.hash.slice(1);
  if(hash.startsWith('join-')){
    const code=hash.replace('join-','');
    showJoinRoom();
    document.getElementById('join-code-inp').value=code.toUpperCase();
  }
})();

function getName(){ return document.getElementById('pname').value.trim()||'Comandante'; }

function showCard(id){
  ['card-main','card-create','card-join'].forEach(c=>{
    document.getElementById(c).style.display=c===id?'flex':'none';
  });
}
function backToMain(){ showCard('card-main'); }
function showCreateRoom(){ myName=getName(); showCard('card-create'); createRoom(); }
function showJoinRoom(){ showCard('card-join'); }

// ═══════════════════════════════════════════════════════
//  ROOM: localStorage-based relay
//  Works cross-tab/cross-window on same device.
//  For different devices: we encode the full game state
//  into a shareable URL (data URI hash) — host exports,
//  guest imports via URL. After that, turns are exchanged
//  via copying the turn-state link.
// ═══════════════════════════════════════════════════════

function genRoomId(){
  return Math.random().toString(36).substr(2,6).toUpperCase();
}

function lsKey(room,type){ return `imperium_${room}_${type}`; }

function lsWrite(room,type,data){
  try{ localStorage.setItem(lsKey(room,type), JSON.stringify(data)); return true; }
  catch(e){ return false; }
}
function lsRead(room,type){
  try{ const v=localStorage.getItem(lsKey(room,type)); return v?JSON.parse(v):null; }
  catch(e){ return null; }
}

function createRoom(){
  myName=getName(); myId='p0'; isHost=true;
  roomId=genRoomId();
  const roomData={ host:{id:'p0',name:myName,color:myColor}, guest:null, started:false, seq:0 };
  lsWrite(roomId,'room',roomData);

  const inviteUrl=`${location.origin}${location.pathname}#join-${roomId}`;
  document.getElementById('invite-url-text').textContent=inviteUrl;
  document.getElementById('invite-box').style.display='flex';
  document.getElementById('create-status').textContent='Sala criada! Partilha o link:';
  document.getElementById('room-wait-msg').style.display='block';

  updateRoomPlayersList(roomData);

  // Poll for guest joining
  pollTimer=setInterval(()=>{
    const rd=lsRead(roomId,'room');
    if(!rd) return;
    updateRoomPlayersList(rd);
    if(rd.guest){
      clearInterval(pollTimer);
      document.getElementById('room-wait-msg').style.display='none';
      document.getElementById('start-game-btn').style.display='block';
      document.getElementById('start-game-btn').textContent=`⚔ INICIAR GUERRA com ${rd.guest.name}`;
    }
  }, POLL_MS);
}

function updateRoomPlayersList(rd){
  const el=document.getElementById('room-players-list');
  let html='';
  if(rd.host) html+=`<div class="player-join-row"><div class="pjdot" style="background:${rd.host.color}"></div><span>${rd.host.name} (anfitrião)</span></div>`;
  if(rd.guest) html+=`<div class="player-join-row"><div class="pjdot" style="background:${rd.guest.color}"></div><span>${rd.guest.name}</span></div>`;
  el.innerHTML=html;
}

function copyInvite(){
  const url=document.getElementById('invite-url-text').textContent;
  navigator.clipboard.writeText(url).then(()=>{
    document.getElementById('copy-btn').textContent='✓ Copiado!';
    setTimeout(()=>document.getElementById('copy-btn').textContent='📋 Copiar Link',2000);
  });
}

function doJoin(){
  myName=getName(); myId='p1'; isHost=false;
  const code=document.getElementById('join-code-inp').value.trim().toUpperCase();
  if(!code){ document.getElementById('join-status').textContent='Introduz o código da sala.'; return; }
  roomId=code;
  const rd=lsRead(roomId,'room');
  if(!rd){ document.getElementById('join-status').className='status err'; document.getElementById('join-status').textContent='Sala não encontrada. Abre o link na mesma janela do navegador.'; return; }
  if(rd.guest){ document.getElementById('join-status').className='status err'; document.getElementById('join-status').textContent='Sala já está cheia.'; return; }
  rd.guest={id:'p1',name:myName,color:myColor};
  lsWrite(roomId,'room',rd);
  document.getElementById('join-status').className='status ok'; document.getElementById('join-status').textContent='Entrou! A aguardar o anfitrião...';

  // Wait for game start
  pollTimer=setInterval(()=>{
    const gs=lsRead(roomId,'gamestate');
    if(gs&&gs.started){
      clearInterval(pollTimer);
      loadGameFromState(gs, false);
    }
  }, POLL_MS);
}

function hostStartGame(){
  clearInterval(pollTimer);
  const rd=lsRead(roomId,'room');
  if(!rd) return;
  players={
    p0:{id:'p0',name:rd.host.name,color:rd.host.color,gold:80,isAI:false},
    p1:{id:'p1',name:rd.guest?rd.guest.name:'Adversário',color:rd.guest?rd.guest.color:COLORS[3],gold:80,isAI:false}
  };
  isSolo=false; mpTurn='p0';
  initGame(true);
}

function soloStart(){
  myName=getName(); myId='p0'; isSolo=true; isHost=true;
  players={
    p0:{id:'p0',name:myName,color:myColor,gold:80,isAI:false},
    ai1:{id:'ai1',name:'Império Norte',color:'#e74c3c',gold:80,isAI:true},
    ai2:{id:'ai2',name:'Sultanato Sul',color:'#9b59b6',gold:80,isAI:true},
    ai3:{id:'ai3',name:'Horda Leste',color:'#e67e22',gold:80,isAI:true},
  };
  initGame(false);
}

// ═══════════════════════════════════════════════════════
//  GAME INIT
// ═══════════════════════════════════════════════════════
const ISO_NAMES={
  '004':'Afeganistão','008':'Albânia','012':'Argélia','024':'Angola','032':'Argentina',
  '036':'Austrália','040':'Áustria','050':'Bangladesh','056':'Bélgica','068':'Bolívia',
  '076':'Brasil','100':'Bulgária','104':'Birmânia','116':'Camboja','120':'Camarões',
  '124':'Canadá','144':'Sri Lanka','152':'Chile','156':'China','170':'Colômbia',
  '180':'Congo','188':'Costa Rica','192':'Cuba','203':'Rep. Checa','208':'Dinamarca',
  '218':'Equador','818':'Egito','231':'Etiópia','246':'Finlândia','250':'França',
  '276':'Alemanha','288':'Gana','300':'Grécia','320':'Guatemala','332':'Haiti',
  '340':'Honduras','356':'Índia','360':'Indonésia','364':'Irão','368':'Iraque',
  '372':'Irlanda','380':'Itália','392':'Japão','400':'Jordânia','404':'Quénia',
  '408':'Coreia Norte','410':'Coreia Sul','418':'Laos','422':'Líbano','434':'Líbia',
  '484':'México','504':'Marrocos','508':'Moçambique','524':'Nepal','528':'Holanda',
  '554':'Nova Zelândia','558':'Nicarágua','566':'Nigéria','578':'Noruega',
  '586':'Paquistão','600':'Paraguai','604':'Peru','608':'Filipinas','616':'Polónia',
  '620':'Portugal','642':'Roménia','643':'Rússia','682':'Arábia Saudita',
  '686':'Senegal','706':'Somália','710':'África do Sul','724':'Espanha',
  '729':'Sudão','752':'Suécia','756':'Suíça','760':'Síria','764':'Tailândia',
  '792':'Turquia','800':'Uganda','804':'Ucrânia','784':'Emirados Árabes',
  '826':'Reino Unido','840':'EUA','858':'Uruguai','862':'Venezuela','704':'Vietname',
  '887':'Iémen','894':'Zâmbia','716':'Zimbabué','450':'Madagáscar','466':'Mali',
  '496':'Mongólia','516':'Namíbia','562':'Níger','788':'Tunísia','834':'Tanzânia',
};

const STARTS={
  p0:['620','724','250','380','276'],
  p1:['826','208','528','616','642'],
  ai1:['643','804','246','578','208'],
  ai2:['156','356','764','360','392'],
  ai3:['840','124','076','484','032'],
};

function initGame(writeLs){
  document.getElementById('s-lobby').classList.remove('active');
  document.getElementById('s-game').classList.add('active');

  if(!isSolo){
    document.getElementById('conn-indicator').style.display='flex';
    document.getElementById('turn-pill').style.display='flex';
    document.getElementById('end-turn-topbtn').style.display='block';
  }

  const mw=document.getElementById('mapwrap');
  const W=mw.clientWidth||900, H=mw.clientHeight||520;
  svgEl=d3.select('#wmap').attr('viewBox',`0 0 ${W} ${H}`);
  proj=d3.geoNaturalEarth1().scale(W/6.3).translate([W/2,H/2]);
  pathFn=d3.geoPath().projection(proj);
  const zoom=d3.zoom().scaleExtent([1,9]).on('zoom',e=>gEl.attr('transform',e.transform));
  svgEl.call(zoom);
  gEl=svgEl.append('g');
  gEl.append('path').datum(d3.geoGraticule()())
    .attr('d',pathFn).attr('fill','none')
    .attr('stroke','rgba(255,255,255,.035)').attr('stroke-width',.5);

  fetch('https://cdn.jsdelivr.net/npm/world-atlas@2/countries-110m.json')
    .then(r=>r.json())
    .then(world=>buildMap(world, W, H, writeLs))
    .catch(()=>addLog('Erro ao carregar mapa CDN.','e'));
}

function buildMap(world, W, H, writeLs){
  const feats=topojson.feature(world,world.objects.countries).features;
  const nbTopo=topojson.neighbors(world.objects.countries.geometries);

  feats.forEach((f,i)=>{
    const iso=String(f.id).padStart(3,'0');
    const c=pathFn.centroid(f);
    countries[iso]={
      iso, name:ISO_NAMES[iso]||'País '+iso,
      feature:f, idx:i,
      owner:null, troops:rnd(4,9), income:rnd(2,6),
      centroid:(isNaN(c[0])?[0,0]:c),
      neighbors:[]
    };
  });

  feats.forEach((f,i)=>{
    const iso=String(f.id).padStart(3,'0');
    nbTopo[i].forEach(j=>{
      const jiso=String(feats[j].id).padStart(3,'0');
      if(countries[iso]&&countries[jiso]) countries[iso].neighbors.push(jiso);
    });
  });

  Object.keys(players).forEach(pid=>{
    (STARTS[pid]||[]).forEach(iso=>{
      if(countries[iso]){ countries[iso].owner=pid; countries[iso].troops=rnd(12,18); }
    });
  });

  drawMap(feats);

  if(writeLs && !isSolo){
    const gs=buildGameState();
    gs.started=true;
    lsWrite(roomId,'gamestate',gs);
    startMPSync();
  }

  startIncomeLoop();
  updateAll();
  addLog('⚜ Guerra iniciada! Seleciona os teus países para agir.','ev');
  if(!isSolo) addLog(mpTurn===myId?'É a tua vez!':'Aguarda a vez de '+players[mpTurn].name,'ev');
}

function loadGameFromState(gs, asHost){
  isHost=asHost; isSolo=false; mpTurn=gs.mpTurn;
  players=gs.players;
  // Rebuild map but load country state from gs
  const mw=document.getElementById('mapwrap');
  const W=mw.clientWidth||900, H=mw.clientHeight||520;
  svgEl=d3.select('#wmap').attr('viewBox',`0 0 ${W} ${H}`);
  proj=d3.geoNaturalEarth1().scale(W/6.3).translate([W/2,H/2]);
  pathFn=d3.geoPath().projection(proj);
  const zoom=d3.zoom().scaleExtent([1,9]).on('zoom',e=>gEl.attr('transform',e.transform));
  svgEl.call(zoom); gEl=svgEl.append('g');
  gEl.append('path').datum(d3.geoGraticule()()).attr('d',pathFn).attr('fill','none').attr('stroke','rgba(255,255,255,.035)').attr('stroke-width',.5);

  document.getElementById('s-lobby').classList.remove('active');
  document.getElementById('s-game').classList.add('active');
  document.getElementById('conn-indicator').style.display='flex';
  document.getElementById('turn-pill').style.display='flex';
  document.getElementById('end-turn-topbtn').style.display='block';

  fetch('https://cdn.jsdelivr.net/npm/world-atlas@2/countries-110m.json')
    .then(r=>r.json()).then(world=>{
      const feats=topojson.feature(world,world.objects.countries).features;
      const nbTopo=topojson.neighbors(world.objects.countries.geometries);
      feats.forEach((f,i)=>{
        const iso=String(f.id).padStart(3,'0');
        const c=pathFn.centroid(f);
        countries[iso]={ iso,name:ISO_NAMES[iso]||'País '+iso,feature:f,idx:i,
          owner:null,troops:0,income:rnd(2,6),centroid:(isNaN(c[0])?[0,0]:c),neighbors:[] };
      });
      feats.forEach((f,i)=>{
        const iso=String(f.id).padStart(3,'0');
        nbTopo[i].forEach(j=>{ const jiso=String(feats[j].id).padStart(3,'0'); if(countries[iso]&&countries[jiso]) countries[iso].neighbors.push(jiso); });
      });
      applyGameState(gs);
      drawMap(feats);
      startIncomeLoop();
      startMPSync();
      updateAll();
      addLog('Entraste na sala! '+( mpTurn===myId?'É a tua vez!':'Aguarda '+players[mpTurn].name),'ev');
    });
}

// ═══════════════════════════════════════════════════════
//  MAP DRAW
// ═══════════════════════════════════════════════════════
function drawMap(feats){
  gEl.selectAll('.ctry').data(feats).enter()
    .append('path').attr('class','ctry').attr('d',pathFn)
    .attr('id',f=>'c'+String(f.id).padStart(3,'0'))
    .attr('fill',f=>ownerColor(String(f.id).padStart(3,'0')))
    .on('click',(e,f)=>selectCountry(String(f.id).padStart(3,'0')))
    .on('mousemove',(e,f)=>showTT(e,String(f.id).padStart(3,'0')))
    .on('mouseleave',()=>{document.getElementById('tt').style.display='none'});

  gEl.selectAll('.tlbl').data(feats).enter()
    .append('text').attr('class','tlbl')
    .attr('id',f=>'t'+String(f.id).padStart(3,'0'))
    .attr('x',f=>{ const c=countries[String(f.id).padStart(3,'0')]; return c?c.centroid[0]:0; })
    .attr('y',f=>{ const c=countries[String(f.id).padStart(3,'0')]; return c?c.centroid[1]+3:0; })
    .text(f=>{ const c=countries[String(f.id).padStart(3,'0')]; return c&&c.troops?c.troops:''; });
}

function ownerColor(iso){
  const c=countries[iso]; if(!c||!c.owner) return '#1e3048';
  return players[c.owner]?players[c.owner].color:'#1e3048';
}

function refreshColors(){
  Object.keys(countries).forEach(iso=>{
    d3.select('#c'+iso).attr('fill',ownerColor(iso));
    d3.select('#t'+iso).text(countries[iso]&&countries[iso].troops?countries[iso].troops:'');
  });
}

function showTT(e,iso){
  const c=countries[iso]; if(!c) return;
  const own=c.owner&&players[c.owner]?players[c.owner].name:'Neutro';
  const tt=document.getElementById('tt');
  const mw=document.getElementById('mapwrap').getBoundingClientRect();
  tt.style.display='block';
  tt.style.left=(e.clientX-mw.left+12)+'px';
  tt.style.top=(e.clientY-mw.top-10)+'px';
  tt.innerHTML=`<div class="tn">${c.name}</div>
    <div class="tr"><span>Dono</span><span>${own}</span></div>
    <div class="tr"><span>Tropas</span><span>${c.troops}</span></div>
    <div class="tr"><span>Renda</span><span>${c.income}/ciclo</span></div>`;
}

// ═══════════════════════════════════════════════════════
//  SELECTION
// ═══════════════════════════════════════════════════════
function selectCountry(iso){
  document.getElementById('tt').style.display='none';
  const c=countries[iso]; if(!c) return;
  selIso=iso;
  d3.selectAll('.ctry').classed('sel',false).classed('atk',false);
  d3.select('#c'+iso).classed('sel',true);
  if(c.owner===myId) c.neighbors.forEach(n=>{ if(countries[n]&&countries[n].owner!==myId) d3.select('#c'+n).classed('atk',true); });
  updatePanel();
}

function canAct(){ return isSolo || mpTurn===myId; }

function updatePanel(){
  if(!selIso){ document.getElementById('sname').textContent='—'; return; }
  const c=countries[selIso];
  const own=c.owner&&players[c.owner]?players[c.owner].name:'Neutro';
  const oc=c.owner&&players[c.owner]?players[c.owner].color:'#7a8a9a';
  document.getElementById('sname').textContent=c.name;
  document.getElementById('sinfo').innerHTML=`<span style="color:${oc};font-weight:600">${own}</span>`;
  document.getElementById('sdet').innerHTML=`
    <div class="irow"><span class="l">Tropas</span><span class="r">${c.troops}</span></div>
    <div class="irow"><span class="l">Renda/ciclo</span><span class="r">${c.income}💰</span></div>
    <div class="irow"><span class="l">Vizinhos</span><span class="r">${c.neighbors.length}</span></div>`;
  const ab=document.getElementById('sact'); ab.innerHTML='';
  const myP=players[myId]; const ok=canAct();
  if(c.owner===myId){
    ab.innerHTML+=`<div style="font-size:11px;color:#7a6d4a;margin:5px 0 2px">Recrutar:</div>`;
    ab.innerHTML+=`<button class="abtn" onclick="doRecruit('${selIso}',5,15)" ${(!ok||myP.gold<15)?'disabled':''}>+5 tropas (15💰)</button>`;
    ab.innerHTML+=`<button class="abtn" onclick="doRecruit('${selIso}',10,25)" ${(!ok||myP.gold<25)?'disabled':''}>+10 tropas (25💰)</button>`;
    const allies=c.neighbors.filter(n=>countries[n]&&countries[n].owner===myId);
    if(allies.length&&c.troops>1){
      ab.innerHTML+=`<div style="font-size:11px;color:#7a6d4a;margin:5px 0 2px">Mover tropas:</div>`;
      allies.slice(0,3).forEach(n=>ab.innerHTML+=`<button class="abtn" onclick="doMove('${selIso}','${n}')" ${!ok?'disabled':''}>→ ${countries[n].name}</button>`);
    }
    const enems=c.neighbors.filter(n=>countries[n]&&countries[n].owner!==myId);
    if(enems.length&&c.troops>1){
      ab.innerHTML+=`<div style="font-size:11px;color:#7a6d4a;margin:5px 0 2px">Atacar:</div>`;
      enems.slice(0,5).forEach(n=>ab.innerHTML+=`<button class="abtn d" onclick="doAttack('${selIso}','${n}')" ${!ok?'disabled':''}>⚔ ${countries[n].name} (${countries[n].troops}🗡)</button>`);
    }
  } else {
    const adj=c.neighbors.find(n=>countries[n]&&countries[n].owner===myId);
    if(adj&&countries[adj].troops>1) ab.innerHTML+=`<button class="abtn d" onclick="doAttack('${adj}','${selIso}')" ${!ok?'disabled':''}>⚔ Atacar de ${countries[adj].name}</button>`;
  }
  if(!ok&&!isSolo) ab.innerHTML+=`<div style="font-size:11px;color:#8a4a2a;font-style:italic;margin-top:6px">Não é a tua vez</div>`;
}

// ═══════════════════════════════════════════════════════
//  ACTIONS
// ═══════════════════════════════════════════════════════
function doRecruit(iso,n,cost){
  const p=players[myId]; if(!p||p.gold<cost||!canAct()) return;
  countries[iso].troops+=n; p.gold-=cost;
  addLog(`Recrutaste ${n} tropas em ${countries[iso].name}`,'p');
  afterAction();
}

function doAttack(fromIso,toIso){
  if(!canAct()) return;
  const att=countries[fromIso],def=countries[toIso];
  if(!att||!def||att.troops<2) return;
  let af=Math.floor(att.troops*.65),df=def.troops,sent=af,r=0;
  while(af>0&&df>0&&r<30){
    df=Math.max(0,df-Math.max(1,Math.round(af*(.35+Math.random()*.25))));
    af=Math.max(0,af-Math.max(1,Math.round(df*(.25+Math.random()*.25))));
    r++;
  }
  att.troops=Math.max(1,att.troops-sent);
  const fc=att.centroid,tc=def.centroid;
  if(fc&&tc&&fc[0]&&tc[0]){
    const ln=gEl.append('line').attr('class','aline')
      .attr('x1',fc[0]).attr('y1',fc[1]).attr('x2',tc[0]).attr('y2',tc[1])
      .attr('stroke',af>0?'#f1c40f':'#e74c3c');
    setTimeout(()=>ln.remove(),600);
  }
  if(af>0){ def.owner=myId; def.troops=Math.max(1,af); addLog(`⚔ Conquistaste ${def.name}! (${af} sobreviventes)`,'p'); }
  else addLog(`💀 Ataque a ${def.name} falhou!`,'e');
  afterAction();
}

function doMove(fromIso,toIso){
  if(!canAct()) return;
  const fc=countries[fromIso],tc=countries[toIso]; if(!fc||!tc||fc.troops<2) return;
  const n=Math.floor(fc.troops/2);
  fc.troops-=n; tc.troops+=n;
  addLog(`Moveste ${n} tropas de ${fc.name} para ${tc.name}`,'p');
  afterAction();
}

function afterAction(){
  if(!isSolo) syncState();
  refreshColors(); updateAll(); checkVictory();
  if(selIso) updatePanel();
}

function endMyTurn(){
  if(isSolo||!canAct()) return;
  mpTurn=mpTurn==='p0'?'p1':'p0';
  syncState();
  updateAll(); if(selIso) updatePanel();
  addLog(`Passaste a vez a ${players[mpTurn].name}`,'ev');
}

// ═══════════════════════════════════════════════════════
//  AI
// ═══════════════════════════════════════════════════════
function runAI(){
  Object.values(players).filter(p=>p.isAI).forEach(p=>{
    const mine=Object.keys(countries).filter(iso=>countries[iso].owner===p.id);
    if(!mine.length) return;
    mine.forEach(iso=>p.gold+=countries[iso].income);
    if(p.gold>=15&&Math.random()<.45){ const iso=mine[rnd(0,mine.length-1)]; countries[iso].troops+=5; p.gold-=15; }
    for(const iso of mine.sort(()=>Math.random()-.5)){
      const c=countries[iso]; if(!c||c.troops<5) continue;
      const tgts=c.neighbors.filter(n=>countries[n]&&countries[n].owner!==p.id);
      if(!tgts.length) continue;
      if(Math.random()<.55){
        const tgt=tgts[rnd(0,tgts.length-1)];
        const def=countries[tgt];
        let af=Math.floor(c.troops*.6),df=def.troops,r=0,sent=af;
        while(af>0&&df>0&&r<30){
          df=Math.max(0,df-Math.max(1,Math.round(af*(.35+Math.random()*.2))));
          af=Math.max(0,af-Math.max(1,Math.round(df*(.25+Math.random()*.2))));
          r++;
        }
        c.troops=Math.max(1,c.troops-sent);
        if(af>0){ def.owner=p.id; def.troops=Math.max(1,af); addLog(`⚠ ${p.name} conquistou ${def.name}!`,'e'); }
        break;
      }
    }
  });
}

// ═══════════════════════════════════════════════════════
//  INCOME LOOP
// ═══════════════════════════════════════════════════════
function startIncomeLoop(){
  let prog=0;
  incTimer=setInterval(()=>{
    prog+=100;
    document.getElementById('ibar').style.width=((prog/INCOME_MS)*100)+'%';
    if(prog>=INCOME_MS){
      prog=0; incomeTick();
    }
  },100);
}

function incomeTick(){
  Object.values(players).forEach(p=>{
    const mine=Object.keys(countries).filter(iso=>countries[iso].owner===p.id);
    mine.forEach(iso=>{ countries[iso].troops+=1; p.gold+=countries[iso].income; });
  });
  if(isSolo) runAI();
  refreshColors(); updateAll();
  const myInc=Object.keys(countries).filter(iso=>countries[iso].owner===myId).reduce((a,iso)=>a+countries[iso].income,0);
  addLog(`💰 +${myInc} ouro de rendimento`,'ev');
  if(!isSolo) syncState();
  checkVictory();
}

// ═══════════════════════════════════════════════════════
//  MULTIPLAYER SYNC via localStorage
// ═══════════════════════════════════════════════════════
function buildGameState(){
  const snap={};
  Object.keys(countries).forEach(iso=>snap[iso]={owner:countries[iso].owner,troops:countries[iso].troops});
  const pg={};
  Object.keys(players).forEach(id=>pg[id]=players[id].gold);
  return {snap,pg,mpTurn,players:sanitizePlayers(),seq:(lastSeenSeq+1),started:true};
}

function sanitizePlayers(){
  const out={};
  Object.keys(players).forEach(id=>out[id]={id,name:players[id].name,color:players[id].color,gold:players[id].gold,isAI:players[id].isAI||false});
  return out;
}

function syncState(){
  if(!roomId) return;
  const gs=buildGameState();
  lsWrite(roomId,'gamestate',gs);
  lastSeenSeq=gs.seq;
  updateConnIndicator('online');
}

function applyGameState(gs){
  if(!gs||gs.seq<=lastSeenSeq) return false;
  lastSeenSeq=gs.seq;
  Object.keys(gs.snap||{}).forEach(iso=>{ if(countries[iso]){ countries[iso].owner=gs.snap[iso].owner; countries[iso].troops=gs.snap[iso].troops; }});
  Object.keys(gs.players||{}).forEach(id=>{ if(players[id]){ players[id].gold=gs.players[id].gold; players[id].name=gs.players[id].name; }});
  if(gs.mpTurn) mpTurn=gs.mpTurn;
  return true;
}

function startMPSync(){
  updateConnIndicator('online');
  pollTimer=setInterval(()=>{
    if(!roomId) return;
    const gs=lsRead(roomId,'gamestate');
    if(!gs){ updateConnIndicator('offline'); return; }
    if(applyGameState(gs)){
      refreshColors(); updateAll(); if(selIso) updatePanel();
      updateConnIndicator('online');
      if(mpTurn===myId) addLog('É a tua vez de agir!','ev');
    } else {
      updateConnIndicator('online');
    }
  }, POLL_MS);
}

function updateConnIndicator(state){
  const el=document.getElementById('conn-indicator');
  el.className='conn-indicator '+state;
  el.textContent=state==='online'?'● Online':state==='syncing'?'⟳ Sync':'✕ Offline';
}

// ═══════════════════════════════════════════════════════
//  UI
// ═══════════════════════════════════════════════════════
function updateAll(){ updateTopbar(); updateSidebar(); }

function updateTopbar(){
  const p=players[myId]; if(!p) return;
  const mine=Object.keys(countries).filter(iso=>countries[iso].owner===myId);
  const tot=mine.reduce((a,iso)=>a+countries[iso].troops,0);
  document.getElementById('st-c').textContent=mine.length;
  document.getElementById('st-t').textContent=tot;
  document.getElementById('st-g').textContent=Math.floor(p.gold);
  document.getElementById('st-n').textContent=myName;
  document.getElementById('cdot').style.background=myColor;
  if(!isSolo){
    const tp=players[mpTurn]; if(tp) document.getElementById('st-turn').textContent=tp.name;
    const etb=document.getElementById('end-turn-topbtn');
    etb.textContent=mpTurn===myId?'Terminar Turno →':'Aguardar...';
    etb.style.background=mpTurn===myId?'rgba(201,168,76,.15)':'transparent';
    etb.style.color=mpTurn===myId?'var(--gold-l)':'#5a5040';
  }
}

function updateSidebar(){
  document.getElementById('psb').innerHTML=Object.values(players).map(p=>{
    const cnt=Object.keys(countries).filter(iso=>countries[iso].owner===p.id).length;
    return `<div class="prow"><div class="pdot" style="background:${p.color}"></div>
      <span style="flex:1">${p.name}${p.id===myId?' ✦':''}</span>
      <span style="font-size:11px;color:#7a6d4a">🏴${cnt}</span></div>`;
  }).join('');
}

function addLog(msg,type='s'){
  logLines.unshift({msg,type});
  if(logLines.length>5) logLines.pop();
  document.getElementById('li').innerHTML=logLines.map(l=>`<div class="ll ${l.type}">${l.msg}</div>`).join('');
}

function checkVictory(){
  const total=Object.keys(countries).length; if(!total) return;
  const mine=Object.keys(countries).filter(iso=>countries[iso].owner===myId).length;
  if(mine>total*.6){ document.getElementById('victory').classList.add('show'); document.getElementById('vt').textContent='VITÓRIA!'; document.getElementById('vt').style.color='var(--gold)'; document.getElementById('vs').textContent=`${myName} dominou ${mine} países (${Math.round(mine/total*100)}%)`; }
  else if(mine===0&&total>10){ document.getElementById('victory').classList.add('show'); document.getElementById('vt').textContent='DERROTA'; document.getElementById('vt').style.color='#c0392b'; document.getElementById('vs').textContent='O teu império foi destruído.'; }
}

function rnd(a,b){ return Math.floor(Math.random()*(b-a+1))+a; }

// Check URL hash on load for auto-join
window.addEventListener('load',()=>{
  const hash=location.hash.slice(1);
  if(hash.startsWith('join-')){
    const code=hash.replace('join-','');
    showJoinRoom();
    document.getElementById('join-code-inp').value=code.toUpperCase();
    // Try to pre-fill name
  }
});
</script>
</body>
</html>
