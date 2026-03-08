<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MIMIII’S INDUSTRIES™ | SECURE LOGIN</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Bodoni+Moda:ital,wght@0,400;0,900;1,400&family=Montserrat:wght@200;400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --pink-accent: #ff007f;
            --chrome: linear-gradient(180deg, #ffffff 0%, #ff69b4 50%, #707070 100%);
        }
        body {
            margin: 0;
            background-color: #000;
            font-family: 'Montserrat', sans-serif;
            color: #fff;
            overflow: hidden;
        }
        /* Fond Léopard Rose Ultra-Bling */
        .background-wrap {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            z-index: -2;
            background: #000;
        }
        .leopard-layer {
            position: absolute;
            width: 100%; height: 100%;
            background-image: url('https://www.transparenttextures.com/patterns/leopard.png');
            background-color: #33001a;
            opacity: 0.6;
            filter: invert(1) sepia(1) saturate(20) hue-rotate(280deg) brightness(0.8);
            z-index: -1;
        }
        .satin-glow {
            position: absolute;
            width: 100%; height: 100%;
            background: radial-gradient(circle at center, rgba(255, 0, 127, 0.4) 0%, transparent 80%);
        }
        /* Pluie de Billets */
        .bill-particle {
            position: absolute;
            pointer-events: none;
            z-index: 10;
            animation: fall-bill linear infinite;
            width: 60px;
            height: 30px;
            background: #2d5a27;
            border: 1px solid #4a7c44;
            border-radius: 2px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 8px;
            color: #a5d6a7;
            box-shadow: 0 4px 6px rgba(0,0,0,0.3);
        }
        .bill-particle::after {
            content: '$';
            font-weight: bold;
        }
        @keyframes fall-bill {
            0% { transform: translateY(-50px) rotateX(0deg) rotateY(0deg); opacity: 1; }
            100% { transform: translateY(110vh) rotateX(720deg) rotateY(360deg); opacity: 0.7; }
        }
        /* Écrans de Login & Password */
        #login-screen {
            position: fixed;
            inset: 0;
            z-index: 1000;
            background: black;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            transition: opacity 1s ease-out;
        }
        .login-card {
            padding: 3rem;
            border: 1px solid var(--pink-accent);
            background: rgba(255, 0, 127, 0.05);
            backdrop-filter: blur(10px);
            text-align: center;
            box-shadow: 0 0 50px rgba(255, 0, 127, 0.3);
            width: 90%;
            max-width: 450px;
        }
        
        .input-baddie {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 0, 127, 0.5);
            color: white;
            padding: 1rem;
            width: 100%;
            margin-bottom: 1.5rem;
            text-align: center;
            letter-spacing: 0.5rem;
            outline: none;
            transition: all 0.3s;
        }
        .input-baddie:focus {
            border-color: var(--pink-accent);
            box-shadow: 0 0 15px rgba(255, 0, 127, 0.5);
            background: rgba(255, 255, 255, 0.1);
        }
        /* Slides */
        .slide {
            height: 100vh;
            width: 100vw;
            position: absolute;
            top: 0; left: 0;
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
            letter-spacing: 0.4rem;
        }
        .chrome-text {
            background: var(--chrome);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 900;
        }
        /* Badge pour messages importants */
        .auth-badge {
            background: var(--pink-accent);
            color: white;
            padding: 0.5rem 2rem;
            font-size: 0.7rem;
            text-transform: uppercase;
            letter-spacing: 0.5rem;
            font-weight: bold;
            box-shadow: 0 0 20px var(--pink-accent);
            margin-bottom: 2rem;
            display: inline-block;
        }
        .baddie-card {
            background: rgba(0, 0, 0, 0.75);
            backdrop-filter: blur(20px);
            border: 2px solid rgba(255, 0, 127, 0.5);
            border-radius: 0;
            padding: 3rem;
            max-width: 900px;
            width: 100%;
            box-shadow: 0 0 40px rgba(255, 0, 127, 0.2);
        }
        /* Avatar */
        .avatar-box {
            width: 250px;
            height: 350px;
            border: 1px solid var(--pink-accent);
            position: relative;
            background: url('https://images.unsplash.com/photo-1524250502761-1ac6f2e30d43?auto=format&fit=crop&q=80&w=400');
            background-size: cover;
            background-position: center;
            box-shadow: 0 0 20px rgba(255, 0, 127, 0.4);
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
            background: none;
            border-bottom: 2px solid var(--pink-accent);
            color: #fff;
            padding: 0.5rem 1rem;
            font-size: 0.7rem;
            text-transform: uppercase;
            letter-spacing: 0.3rem;
            cursor: pointer;
            transition: all 0.3s;
        }
        .btn-nav:hover {
            background: var(--pink-accent);
            color: #000;
        }

        /* Shutdown Animation */
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
            font-size: 4rem;
            filter: drop-shadow(0 0 20px #ff007f);
            animation: bounce 1.5s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0) scale(1); }
            50% { transform: translateY(-20px) scale(1.1); }
        }
        .glitch {
            animation: glitch 0.2s infinite;
        }
        @keyframes glitch {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }
    </style>
</head>
<body>
    <!-- Écran de Connexion -->
    <div id="login-screen">
        <div class="login-card" id="card-content">
            <h2 class="luxury-text text-xl mb-6">MIMIII’S INDUSTRIES™</h2>
            <p class="text-[0.6rem] uppercase tracking-widest opacity-50 mb-8">System: Secure Baddie Access v4.5</p>
            <!-- Étape 1 : Boot -->
            <div id="boot-section">
                <div id="boot-loader" class="text-pink-600 text-xs mb-8 italic">Initialisation du lien satellite...</div>
                <button onclick="showPasswordStep()" id="login-btn" class="hidden border border-pink-600 px-8 py-3 text-[0.7rem] uppercase tracking-widest hover:bg-pink-600 transition duration-500 w-full">
                    CONNECT TO SESSION
                </button>
            </div>
            <!-- Étape 2 : Password -->
            <div id="password-section" class="hidden">
                <p class="text-[0.5rem] uppercase tracking-widest text-pink-400 mb-4">Accès Restreint : Entrez le Code</p>
                <input type="password" id="pass-input" class="input-baddie" placeholder="••••••" maxlength="6">
                <button onclick="verifyPassword()" class="border border-white/20 px-8 py-3 text-[0.7rem] uppercase tracking-widest hover:bg-white hover:text-black transition duration-500 w-full">
                    VALIDER L'ACCÈS
                </button>
                <p id="error-msg" class="text-[0.5rem] text-red-500 mt-4 opacity-0 uppercase tracking-tighter">Accès Refusé. Identité non reconnue.</p>
            </div>
        </div>
    </div>
    <!-- Écran de Déconnexion -->
    <div id="shutdown-overlay">
        <div class="glitch luxury-text text-2xl text-pink-600">SYSTEM SHUTDOWN</div>
        <p class="mt-4 text-[0.6rem] uppercase tracking-widest opacity-40">Déconnexion de Mimiii's Industry...</p>
    </div>
    <div class="background-wrap">
        <div class="leopard-layer"></div>
        <div class="satin-glow"></div>
        <div id="money-rain"></div>
    </div>
    <!-- SLIDE 1 -->
    <section class="slide active" id="slide-1">
        <div class="text-center">
            <div class="auth-badge">Authentification Réussie</div>
            <h1 class="luxury-text text-6xl md:text-9xl chrome-text mb-4 leading-none">PRIVATE<br>MANUEL</h1>
            <div class="mt-12 h-1 w-32 bg-white/20 mx-auto"></div>
        </div>
    </section>
    <!-- SLIDE 2 -->
    <section class="slide" id="slide-2">
        <div class="baddie-card">
            <h2 class="luxury-text text-3xl mb-12 text-center text-pink-600">Spécifications</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-12 text-center">
                <div class="space-y-4">
                    <div class="text-5xl chrome-text">08</div>
                    <p class="text-[0.6rem] uppercase tracking-widest opacity-50">Artefacts de collection</p>
                </div>
                <div class="space-y-4">
                    <div class="text-5xl chrome-text">01</div>
                    <p class="text-[0.6rem] uppercase tracking-widest opacity-50">Mission de sabotage</p>
                </div>
                <div class="space-y-4">
                    <div class="text-5xl chrome-text">+500</div>
                    <p class="text-[0.6rem] uppercase tracking-widest opacity-50">Points d'Aura</p>
                </div>
            </div>
        </div>
    </section>
    <!-- SLIDE 3: LA CRÉATRICE (MIMIII) -->
    <section class="slide" id="slide-3">
        <div class="flex flex-col md:flex-row items-center gap-12 max-w-6xl">
            <div class="avatar-box group">
                <div class="absolute inset-0 bg-black/40 group-hover:bg-transparent transition duration-700"></div>
                <div class="absolute bottom-4 left-4 bg-black/80 px-4 py-2 text-[0.6rem] uppercase tracking-widest border border-pink-900">
                    1m57 | Cheveux Marron Bouclés
                </div>
            </div>
            <div class="space-y-8">
                <div class="flex items-center gap-6">
                    <h2 class="luxury-text text-7xl chrome-text">MIMIII</h2>
                    <div class="flex gap-4">
                        <img src="https://flagcdn.com/w80/ma.png" class="w-10 shadow-2xl" alt="Maroc">
                        <img src="https://flagcdn.com/w80/dz.png" class="w-10 shadow-2xl" alt="Algérie">
                    </div>
                </div>
                <div class="grid grid-cols-1 gap-4">
                    <div class="bg-white/5 p-6 border-r-2 border-pink-600 text-right">
                        <p class="text-[0.5rem] uppercase opacity-40 mb-2">Spécialité</p>
                        <p class="text-xl italic font-bold">Colis absurdes mais affectueux</p>
                    </div>
                    <div class="bg-white/5 p-6 border-r-2 border-pink-600 text-right">
                        <p class="text-[0.5rem] uppercase opacity-40 mb-2">Compétences</p>
                        <p class="text-xl">Humour douteux & chaos</p>
                    </div>
                    <div class="bg-white/5 p-6 border-r-2 border-pink-600 text-right flex items-center justify-end gap-6">
                        <div>
                            <p class="text-[0.5rem] uppercase opacity-40 mb-2">Le précieux bonus</p>
                            <p class="text-xl">Culotte remplie de caca (miam)</p>
                        </div>
                        <div class="poop-jewel">💩✨</div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <!-- SLIDE 4 -->
    <section class="slide" id="slide-4">
        <h2 class="luxury-text text-4xl mb-16 underline decoration-pink-600 decoration-4">Le Protocole</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 w-full max-w-2xl">
            <div class="p-8 border border-white/10 bg-black/40 hover:border-pink-600 transition">
                <span class="text-xs text-pink-600 block mb-4">01</span>
                <span class="text-lg uppercase tracking-widest">Ouvrir avec mépris</span>
            </div>
            <div class="p-8 border border-white/10 bg-black/40 hover:border-pink-600 transition">
                <span class="text-xs text-pink-600 block mb-4">02</span>
                <span class="text-lg uppercase tracking-widest">Analyser la menace</span>
            </div>
            <div class="p-8 border border-white/10 bg-black/40 hover:border-pink-600 transition">
                <span class="text-xs text-pink-600 block mb-4">03</span>
                <span class="text-lg uppercase tracking-widest">Ignorer les haters</span>
            </div>
            <div class="p-8 border border-white/10 bg-black/40 hover:border-pink-600 transition">
                <span class="text-xs text-pink-600 block mb-4">04</span>
                <span class="text-lg uppercase tracking-widest">Régner sur l'industrie</span>
            </div>
        </div>
    </section>
    <!-- SLIDE 6 (AURA) -->
    <section class="slide" id="slide-6">
        <div class="w-full max-w-xl text-center">
            <p class="luxury-text text-xl mb-12">Synchronisation de l'Aura</p>
            <div class="h-1 w-full bg-white/5 relative mb-8">
                <div id="aura-bar" class="h-full bg-pink-600 w-0 shadow-[0_0_20px_#ff007f]"></div>
            </div>
            <div id="aura-perc" class="text-7xl chrome-text italic">+0%</div>
        </div>
    </section>
    <!-- SLIDE 7 -->
    <section class="slide" id="slide-7">
        <div class="text-center">
            <h2 class="luxury-text text-8xl chrome-text mb-8">FIN</h2>
            <button onclick="logout()" class="border-2 border-pink-600 px-16 py-4 text-xs uppercase tracking-[0.5rem] hover:bg-pink-600 hover:text-black transition duration-500 font-bold">
                LOGOUT SESSION
            </button>
        </div>
    </section>
    <!-- PERMANENT UI -->
    <div class="nav-controls">
        <button class="btn-nav" onclick="changeSlide(-1)">Précédent</button>
        <button class="btn-nav" onclick="changeSlide(1)">Suivant</button>
    </div>
    <div class="fixed top-8 left-8 flex items-center gap-4">
        <div class="w-2 h-2 rounded-full bg-pink-600 animate-pulse"></div>
        <span class="text-[0.6rem] uppercase tracking-widest opacity-40 italic">Connexion: SÉCURISÉE</span>
    </div>
    <script>
        let currentSlide = 0;
        const slides = document.querySelectorAll('.slide');
        // Animation de boot au chargement
        window.onload = () => {
            const loader = document.getElementById('boot-loader');
            const messages = [
                "Établissement du lien sécurisé...",
                "Contournement des pare-feux haters...",
                "Chargement des textures léopard...",
                "Synchronisation de l'Aura Baddie...",
                "ACCÈS AUTORISÉ."
            ];
            let i = 0;
            const interval = setInterval(() => {
                loader.innerText = messages[i];
                i++;
                if(i === messages.length) {
                    clearInterval(interval);
                    document.getElementById('login-btn').classList.remove('hidden');
                }
            }, 500);
            createMoney();
        };
        function showPasswordStep() {
            document.getElementById('boot-section').classList.add('hidden');
            document.getElementById('password-section').classList.remove('hidden');
            document.getElementById('pass-input').focus();
        }
        function verifyPassword() {
            const input = document.getElementById('pass-input').value;
            const error = document.getElementById('error-msg'); 
            if (input === "H3RP3S") {
                startSession();
            } else {
                error.classList.remove('opacity-0');
                error.classList.add('glitch');
                setTimeout(() => {
                    error.classList.add('opacity-0');
                    error.classList.remove('glitch');
                }, 2000);
            }
        }
        function startSession() {
            document.getElementById('login-screen').style.opacity = '0';
            setTimeout(() => {
                document.getElementById('login-screen').style.display = 'none';
            }, 1000);
        }
        function logout() {
            document.getElementById('shutdown-overlay').style.display = 'flex';
            setTimeout(() => {
                location.reload();
            }, 3000);
        }
        function changeSlide(dir) {
            slides[currentSlide].classList.remove('active');
            currentSlide = (currentSlide + dir + slides.length) % slides.length;
            slides[currentSlide].classList.add('active');  
            if(currentSlide === 4) { // Aura Slide
                setTimeout(() => {
                    const bar = document.getElementById('aura-bar');
                    bar.style.width = '100%';
                    bar.style.transition = 'width 3s cubic-bezier(0.1, 1, 0.1, 1)';
                    let p = 0;
                    let iv = setInterval(() => {
                        p += 31;
                        if(p > 1500) {
                            document.getElementById('aura-perc').innerText = '+1500%';
                            clearInterval(iv);
                        } else {
                            document.getElementById('aura-perc').innerText = `+${p}%`;
                        }
                    }, 30);
                }, 400);
            }
        }
        function createMoney() {
            const container = document.getElementById('money-rain');
            for(let i=0; i<40; i++) {
                const bill = document.createElement('div');
                bill.className = 'bill-particle';
                // Variation de couleur des billets (vert sombre à rose baddie)
                const isSpecial = Math.random() > 0.8;
                if(isSpecial) {
                    bill.style.background = '#880e4f';
                    bill.style.borderColor = '#ff007f';
                    bill.style.color = '#ff80ab';
                }

                bill.style.left = Math.random() * 100 + 'vw';
                bill.style.top = '-' + (Math.random() * 20 + 5) + 'vh';
                
                // Randomize rotation and speed
                const duration = Math.random() * 4 + 3;
                bill.style.animationDuration = duration + 's';
                bill.style.animationDelay = Math.random() * 10 + 's';
                
                container.appendChild(bill);
            }
        }
        document.getElementById('pass-input')?.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') verifyPassword();
        });
        document.addEventListener('keydown', (e) => {
            if(e.key === "ArrowRight") changeSlide(1);
            if(e.key === "ArrowLeft") changeSlide(-1);
        });
    </script>
</body>
</html>
