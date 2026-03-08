<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>MIMIII’S INDUSTRIES™ | PRIVATE ACCESS</title>
<script src="https://cdn.tailwindcss.com"></script>
<link href="https://fonts.googleapis.com/css2?family=Bodoni+Moda:ital,wght@0,400;0,900;1,400&family=Montserrat:wght@200;400;700&display=swap" rel="stylesheet">
<style>
:root {
--pink-accent: #ff007f;
--chrome: linear-gradient(180deg, #ffffff 0%, #ff69b4 50%, #707070 100%);
--deep-dark: #0a0005;
}
body {
margin: 0;
background-color: #000;
font-family: 'Montserrat', sans-serif;
color: #fff;
overflow: hidden;
user-select: none;
}
.background-wrap {
position: fixed;
top: 0;
left: 0;
width: 100%;
height: 100%;
z-index: -2;
background: var(--deep-dark);
}
.leopard-layer {
position: absolute;
width: 100%;
height: 100%;
background-image: url('https://www.transparenttextures.com/patterns/leopard.png');
background-color: #33001a;
opacity: 0.8;
filter: invert(1) sepia(1) saturate(25) hue-rotate(285deg) brightness(0.7);
z-index: -1;
}
.satin-glow {
position: absolute;
width: 100%;
height: 100%;
background: radial-gradient(circle at center, rgba(255, 0, 127, 0.4) 0%, transparent 85%);
}
.bill-particle {
position: absolute;
pointer-events: none;
z-index: 10;
animation: fall-bill linear infinite;
width: 70px;
height: 35px;
background: linear-gradient(135deg, #2e7d32, #1b5e20);
border: 1px solid #43a047;
border-radius: 2px;
display: flex;
align-items: center;
justify-content: center;
font-size: 10px;
font-weight: bold;
color: #a5d6a7;
box-shadow: 0 4px 12px rgba(0,0,0,0.6);
}
.bill-particle::after {
content: "100$";
letter-spacing: 1px;
}
@keyframes fall-bill {
0% { transform: translateY(-100px) rotateX(0deg) rotateY(0deg) rotateZ(0deg); opacity: 0; }
10% { opacity: 1; }
90% { opacity: 1; }
100% { transform: translateY(110vh) rotateX(1080deg) rotateY(360deg) rotateZ(180deg); opacity: 0; }
}
#login-screen {
position: fixed;
inset: 0;
z-index: 1000;
background: black;
display: flex;
justify-content: center;
align-items: center;
transition: opacity 1s ease-in-out;
}
.login-card {
padding: 3.5rem;
border: 2px solid var(--pink-accent);
background: rgba(15, 0, 8, 0.95);
backdrop-filter: blur(25px);
text-align: center;
box-shadow: 0 0 70px rgba(255, 0, 127, 0.6);
width: 90%;
max-width: 480px;
}
.input-baddie {
background: rgba(255, 255, 255, 0.05);
border: 1px solid rgba(255, 0, 127, 0.5);
color: white;
padding: 1.2rem;
width: 100%;
margin-bottom: 2rem;
text-align: center;
letter-spacing: 0.8rem;
font-size: 1.4rem;
outline: none;
transition: 0.3s;
}
.input-baddie:focus {
border-color: var(--pink-accent);
box-shadow: 0 0 25px rgba(255, 0, 127, 0.7);
}
.slide {
height: 100vh;
width: 100vw;
position: absolute;
top: 0;
left: 0;
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
opacity: 0;
visibility: hidden;
transition: opacity 0.8s ease, transform 0.8s ease;
transform: scale(1.1);
padding: 2rem;
}
.slide.active {
opacity: 1;
visibility: visible;
transform: scale(1);
}
.luxury-text {
font-family: 'Bodoni Moda', serif;
text-transform: uppercase;
letter-spacing: 0.5rem;
}
.chrome-text {
background: var(--chrome);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
font-weight: 900;
}
.auth-badge {
background: #fff;
color: #000;
padding: 1rem 3rem;
font-size: 0.9rem;
text-transform: uppercase;
letter-spacing: 0.5rem;
font-weight: 900;
box-shadow: 0 0 30px #fff, 0 0 60px #ff007f;
margin-bottom: 4rem;
display: inline-block;
border-radius: 2px;
animation: pulse-neon 1.5s infinite ease-in-out;
}
@keyframes pulse-neon {
0%, 100% { transform: scale(1); box-shadow: 0 0 20px #fff, 0 0 40px #ff007f; }
50% { transform: scale(1.05); box-shadow: 0 0 40px #fff, 0 0 80px #ff007f; }
}
.baddie-card {
background: rgba(0, 0, 0, 0.9);
backdrop-filter: blur(25px);
border: 1px solid rgba(255, 0, 127, 0.5);
padding: 3.5rem;
max-width: 950px;
width: 100%;
box-shadow: 0 0 50px rgba(255, 0, 127, 0.3);
}
.avatar-box {
width: 260px;
height: 360px;
border: 2px solid var(--pink-accent);
position: relative;
background: url('https://images.unsplash.com/photo-1524250502761-1ac6f2e30d43?auto=format&fit=crop&q=80&w=400');
background-size: cover;
background-position: center;
box-shadow: 0 0 35px rgba(255, 0, 127, 0.5);
}
.nav-controls {
position: fixed;
bottom: 3rem;
width: 100%;
display: flex;
justify-content: space-between;
padding: 0 10%;
z-index: 100;
}
.btn-nav {
background: rgba(15, 0, 8, 0.8);
border: 2px solid var(--pink-accent);
color: #fff;
padding: 0.8rem 2rem;
font-size: 0.8rem;
text-transform: uppercase;
letter-spacing: 0.3rem;
cursor: pointer;
transition: 0.4s;
font-weight: bold;
}
.btn-nav:hover {
background: var(--pink-accent);
color: #000;
box-shadow: 0 0 30px var(--pink-accent);
}
#shutdown-overlay {
position: fixed;
inset: 0;
background: black;
z-index: 2000;
display: none;
justify-content: center;
align-items: center;
flex-direction: column;
}
.poop-jewel {
font-size: 5rem;
filter: drop-shadow(0 0 25px #ff007f);
animation: float-poop 2s infinite ease-in-out;
}
@keyframes float-poop {
0%, 100% { transform: translateY(0) rotate(0deg); }
50% { transform: translateY(-30px) rotate(5deg); }
}
.glitch {
animation: glitch 0.2s infinite;
}
@keyframes glitch {
0% { transform: translate(0); }
25% { transform: translate(-4px, 4px); }
50% { transform: translate(4px, -4px); }
100% { transform: translate(0); }
}
</style>
</head>
<body>
<div id="login-screen">
<div class="login-card">
<h2 class="luxury-text text-3xl mb-8 chrome-text">MIMIII’S INDUSTRIES™</h2>
<p class="text-[0.7rem] uppercase tracking-[0.4rem] opacity-50 mb-12 font-bold">ACCÈS PRIVÉ v5.1</p>
<div id="boot-section">
<div id="boot-loader" class="text-pink-600 text-xs mb-10 italic font-bold">Connexion aux serveurs...</div>
<button onclick="showPasswordStep()" id="login-btn" class="hidden border-2 border-pink-600 px-10 py-5 text-[0.9rem] uppercase tracking-widest hover:bg-pink-600 transition duration-700 w-full font-black">ACCÉDER À LA SESSION</button>
</div>
<div id="password-section" class="hidden">
<p class="text-[0.6rem] uppercase tracking-[0.3rem] text-pink-400 mb-6 font-bold">MOT DE PASSE REQUIS</p>
<input type="password" id="pass-input" class="input-baddie" placeholder="••••••" maxlength="6">
<button onclick="verifyPassword()" class="border-2 border-white/40 px-10 py-5 text-[0.9rem] uppercase tracking-widest hover:bg-white hover:text-black transition duration-500 w-full font-black">DÉVERROUILLER</button>
<p id="error-msg" class="text-[0.6rem] text-red-600 mt-6 opacity-0 uppercase font-black">ACCÈS REFUSÉ. CODE INCORRECT.</p>
</div>
</div>
</div>
<div id="shutdown-overlay">
<div class="glitch luxury-text text-4xl text-pink-600">SHUTDOWN</div>
<p class="mt-8 text-[0.8rem] uppercase tracking-[0.5rem] opacity-50 italic">Déconnexion de Mimiii's Industries...</p>
</div>
<div class="background-wrap">
<div class="leopard-layer"></div>
<div class="satin-glow"></div>
<div id="money-container"></div>
</div>
<section class="slide active" id="slide-1">
<div class="text-center">
<div class="auth-badge">Authentification Réussie</div>
<h1 class="luxury-text text-7xl md:text-9xl chrome-text mb-8 leading-tight">PRIVATE<br>MANUEL</h1>
<div class="mt-20 h-1 w-60 bg-white/30 mx-auto shadow-[0_0_20px_white] rounded-full"></div>
</div>
</section>
<section class="slide" id="slide-2">
<div class="baddie-card">
<h2 class="luxury-text text-4xl mb-20 text-center text-pink-600 border-b border-pink-900 pb-8">Spécifications</h2>
<div class="grid grid-cols-1 md:grid-cols-3 gap-20 text-center">
<div class="space-y-8">
<div class="text-7xl chrome-text">08</div>
<p class="text-[0.8rem] uppercase tracking-widest opacity-60 font-bold">Objets de luxe</p>
</div>
<div class="space-y-8">
<div class="text-7xl chrome-text">01</div>
<p class="text-[0.8rem] uppercase tracking-widest opacity-60 font-bold">Mission d'élite</p>
</div>
<div class="space-y-8">
<div class="text-7xl chrome-text">+500</div>
<p class="text-[0.8rem] uppercase tracking-widest opacity-60 font-bold">Points d'Aura</p>
</div>
</div>
</div>
</section>
<section class="slide" id="slide-3">
<div class="flex flex-col md:flex-row items-center gap-20 max-w-7xl w-full">
<div class="avatar-box shadow-[0_0_50px_rgba(255,0,127,0.6)]">
<div class="absolute bottom-6 left-6 bg-black/95 px-6 py-4 text-[0.8rem] uppercase tracking-widest border border-pink-600 font-bold">1m57 | Cheveux Marron Bouclés</div>
</div>
<div class="flex-grow space-y-12">
<div class="flex items-center gap-10">
<h2 class="luxury-text text-8xl chrome-text">MIMIII</h2>
<div class="flex gap-5">
<img src="https://flagcdn.com/w80/ma.png" class="w-14 shadow-2xl border border-white/20" alt="Maroc">
<img src="https://flagcdn.com/w80/dz.png" class="w-14 shadow-2xl border border-white/20" alt="Algérie">
</div>
</div>
<div class="space-y-6">
<div class="bg-white/5 p-10 border-r-8 border-pink-600 text-right backdrop-blur-xl">
<p class="text-[0.7rem] uppercase opacity-40 mb-4 tracking-[0.3rem]">Spécialité</p>
<p class="text-3xl italic font-black">Colis absurdes mais affectueux</p>
</div>
<div class="bg-white/5 p-10 border-r-8 border-pink-600 text-right backdrop-blur-xl">
<p class="text-[0.7rem] uppercase opacity-40 mb-4 tracking-[0.3rem]">Compétences</p>
<p class="text-3xl font-black">Humour douteux & chaos</p>
</div>
<div class="bg-white/5 p-10 border-r-8 border-pink-600 text-right flex items-center justify-end gap-12 backdrop-blur-xl">
<div>
<p class="text-[0.7rem] uppercase opacity-40 mb-4 tracking-[0.3rem]">Le précieux bonus</p>
<p class="text-3xl font-black">Culotte remplie de caca (miam)</p>
</div>
<div class="poop-jewel">💩✨</div>
</div>
</div>
</div>
</div>
</section>
<section class="slide" id="slide-4">
<h2 class="luxury-text text-5xl mb-24 underline decoration-pink-600 decoration-[12px] underline-offset-[15px]">Protocole</h2>
<div class="grid grid-cols-1 md:grid-cols-2 gap-12 w-full max-w-4xl">
<div class="p-12 border-2 border-white/10 bg-black/70 hover:border-pink-600 transition duration-700 group cursor-default">
<span class="text-pink-600 font-black text-2xl block mb-8 group-hover:scale-125 transition-transform">01</span>
<span class="text-2xl uppercase tracking-[0.4rem] font-bold">Ouvrir avec mépris</span>
</div>
<div class="p-12 border-2 border-white/10 bg-black/70 hover:border-pink-600 transition duration-700 group cursor-default">
<span class="text-pink-600 font-black text-2xl block mb-8 group-hover:scale-125 transition-transform">02</span>
<span class="text-2xl uppercase tracking-[0.4rem] font-bold">Analyser la menace</span>
</div>
<div class="p-12 border-2 border-white/10 bg-black/70 hover:border-pink-600 transition duration-700 group cursor-default">
<span class="text-pink-600 font-black text-2xl block mb-8 group-hover:scale-125 transition-transform">03</span>
<span class="text-2xl uppercase tracking-[0.4rem] font-bold">Ignorer les haters</span>
</div>
<div class="p-12 border-2 border-white/10 bg-black/70 hover:border-pink-600 transition duration-700 group cursor-default">
<span class="text-pink-600 font-black text-2xl block mb-8 group-hover:scale-125 transition-transform">04</span>
<span class="text-2xl uppercase tracking-[0.4rem] font-bold">Régner sur l'industrie</span>
</div>
</div>
</section>
<section class="slide" id="slide-6">
<div class="w-full max-w-3xl text-center">
<p class="luxury-text text-3xl mb-20 tracking-[2rem] opacity-70 italic font-bold">Aura Sync</p>
<div class="h-3 w-full bg-white/10 relative mb-12 rounded-full overflow-hidden">
<div id="aura-bar" class="h-full bg-pink-600 w-0 shadow-[0_0_50px_#ff007f] rounded-full"></div>
</div>
<div id="aura-perc" class="text-9xl chrome-text italic font-black">+0%</div>
</div>
</section>
<section class="slide" id="slide-7">
<div class="text-center">
<h2 class="luxury-text text-[12vw] chrome-text mb-16">BYE.</h2>
<button onclick="logout()" class="border-4 border-pink-600 px-24 py-6 text-lg uppercase tracking-[1rem] hover:bg-pink-600 hover:text-black transition duration-700 font-black shadow-[0_0_30px_rgba(255,0,127,0.5)]">LOGOUT</button>
</div>
</section>
<div class="nav-controls">
<button class="btn-nav" onclick="changeSlide(-1)">PRÉCÉDENT</button>
<button class="btn-nav" onclick="changeSlide(1)">SUIVANT</button>
</div>
<div class="fixed top-12 left-12 flex items-center gap-8">
<div class="w-4 h-4 rounded-full bg-pink-600 animate-pulse shadow-[0_0_25px_#ff007f]"></div>
<span class="text-[0.8rem] uppercase tracking-[0.3rem] opacity-70 font-black italic">CONNEXION: SÉCURISÉE</span>
</div>
<script>
let currentSlide=0;
const slides=document.querySelectorAll('.slide');
window.onload=()=>{
const loader=document.getElementById('boot-loader');
const messages=["Scan du réseau Mimiii's Industry...","Injection des textures léopard...","Chargement du bonus culotte...","IDENTIFICATION REQUISE."];
let i=0;
const interval=setInterval(()=>{
loader.innerText=messages[i];
i++;
if(i===messages.length){
clearInterval(interval);
document.getElementById('login-btn').classList.remove('hidden')
}
},800);
createMoney()
};
function showPasswordStep(){
document.getElementById('boot-section').classList.add('hidden');
document.getElementById('password-section').classList.remove('hidden');
document.getElementById('pass-input').focus()
}
function verifyPassword(){
const input=document.getElementById('pass-input').value;
const error=document.getElementById('error-msg');
if(input.toUpperCase()==="H3RP3S"){
startSession()
}else{
error.classList.remove('opacity-0');
error.classList.add('glitch');
setTimeout(()=>{
error.classList.add('opacity-0');
error.classList.remove('glitch');
document.getElementById('pass-input').value=""
},2000)
}
}
function startSession(){
document.getElementById('login-screen').style.opacity='0';
setTimeout(()=>{
document.getElementById('login-screen').style.display='none'
},1200)
}
function logout(){
document.getElementById('shutdown-overlay').style.display='flex';
setTimeout(()=>{
location.reload()
},3500)
}
function changeSlide(dir){
slides[currentSlide].classList.remove('active');
currentSlide=(currentSlide+dir+slides.length)%slides.length;
slides[currentSlide].classList.add('active');
if(currentSlide===4){
setTimeout(()=>{
const bar=document.getElementById('aura-bar');
bar.style.width='100%';
bar.style.transition='width 4s cubic-bezier(0.1, 1, 0.1, 1)';
let p=0;
let iv=setInterval(()=>{
p+=43;
if(p>1500){
document.getElementById('aura-perc').innerText='+1500%';
clearInterval(iv)
}else{
document.getElementById('aura-perc').innerText=`+${p}%`
}
},50)
},500)
}
}
function createMoney(){
const container=document.getElementById('money-container');
const totalBills=55;
for(let i=0;i<totalBills;i++){
const bill=document.createElement('div');
bill.className='bill-particle';
bill.style.left=Math.random()*100+'vw';
bill.style.animationDelay=Math.random()*15+'s';
const duration=Math.random()*4+4;
bill.style.animationDuration=duration+'s';
if(Math.random()>0.8){
bill.style.background='linear-gradient(135deg, #ad1457, #880e4f)';
bill.style.borderColor='#ff007f';
bill.style.color='#ff80ab'
}
container.appendChild(bill)
}
}
document.getElementById('pass-input')?.addEventListener('keypress',(e)=>{
if(e.key==='Enter')verifyPassword()
});
document.addEventListener('keydown',(e)=>{
if(document.getElementById('login-screen').style.display==='none'){
if(e.key==="ArrowRight")changeSlide(1);
if(e.key==="ArrowLeft")changeSlide(-1)
}
});
</script>
</body>
</html>
