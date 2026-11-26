# THAMBI
Fav akka birthday wish
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TO MY FAVOURITE AKKA 🎀</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Canvas Confetti -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        cream: '#FFF9F0',
                        blush: '#F8DDE8',
                        babyBlue: '#DDECF8',
                        lavender: '#E8E0F5',
                        peach: '#F9D8C6',
                        cherry: '#C94B4B',
                        warmBrown: '#67504A',
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        cursive: ['Dancing Script', 'cursive', 'serif'],
                    }
                }
            }
        }
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600;700&family=Inter:wght@400;500;600;700;800&display=swap');
        
        body {
            background-color: #FFF9F0;
            color: #67504A;
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
        }

        .font-handwriting {
            font-family: 'Dancing Script', cursive;
        }

        /* Smooth page transition container */
        .page-step {
            display: none;
            opacity: 0;
            transform: translateY(15px) scale(0.98);
            transition: opacity 0.6s cubic-bezier(0.22, 1, 0.36, 1), transform 0.6s cubic-bezier(0.22, 1, 0.36, 1);
        }
        .page-step.active {
            display: block;
            opacity: 1;
            transform: translateY(0) scale(1);
        }

        /* Floating Animation */
        @keyframes float {
            0% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(2deg); }
            100% { transform: translateY(0px) rotate(0deg); }
        }
        .animate-float {
            animation: float 4s ease-in-out infinite;
        }

        /* Background Rising Particles */
        @keyframes riseAndFade {
            0% { transform: translateY(100vh) scale(0.6) rotate(0deg); opacity: 0; }
            20% { opacity: 0.7; }
            80% { opacity: 0.7; }
            100% { transform: translateY(-10vh) scale(1.1) rotate(25deg); opacity: 0; }
        }
        .bg-particle {
            position: fixed;
            bottom: -50px;
            pointer-events: none;
            z-index: 1;
            animation: riseAndFade linear infinite;
        }

        /* Shake animation for wrong password */
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            20%, 60% { transform: translateX(-8px); }
            40%, 80% { transform: translateX(8px); }
        }
        .animate-shake {
            animation: shake 0.4s ease-in-out;
        }

        /* Shooting Star Animation */
        @keyframes shootingStar {
            0% { transform: translate(-100px, -100px) rotate(35deg) scale(0); opacity: 1; }
            70% { opacity: 1; }
            100% { transform: translate(500px, 300px) rotate(35deg) scale(1.2); opacity: 0; }
        }
        .shooting-star {
            position: absolute;
            width: 80px;
            height: 2px;
            background: linear-gradient(90deg, #FFF9F0, transparent);
            border-radius: 999px;
            box-shadow: 0 0 10px #F9D8C6;
            animation: shootingStar 1.2s ease-out forwards;
            pointer-events: none;
        }
        .page-step.active {
            display: block;
            opacity: 1;
        }

        /* Floating Animation */
        @keyframes float {
            0% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(2deg); }
            100% { transform: translateY(0px) rotate(0deg); }
        }
        .animate-float {
            animation: float 4s ease-in-out infinite;
        }

        @keyframes pulse-slow {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        .animate-pulse-slow {
            animation: pulse-slow 3s ease-in-out infinite;
        }

        /* Polaroid scrapbook rotation effects */
        .polaroid {
            background: white;
            padding: 12px 12px 24px 12px;
            box-shadow: 0 10px 25px -5px rgba(103, 80, 74, 0.15), 0 8px 10px -6px rgba(103, 80, 74, 0.1);
            transition: all 0.3s ease;
        }
        .polaroid:hover {
            transform: scale(1.03) rotate(0deg) !important;
            z-index: 20;
            box-shadow: 0 20px 30px -10px rgba(103, 80, 74, 0.25);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #FFF9F0;
        }
        ::-webkit-scrollbar-thumb {
            background: #F8DDE8;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #C94B4B;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between selection:bg-blush selection:text-cherry relative overflow-x-hidden">

    <!-- Ambient Floating Background Particles Container -->
    <div id="ambientParticles" class="fixed inset-0 pointer-events-none overflow-hidden z-0"></div>

    <!-- Custom Background Audio Element (Upload 'song.mp3' to your GitHub repo!) -->
    <audio id="customBgmAudio" loop preload="auto">
        <source src="song.mp3" type="audio/mpeg">
    </audio>

    <!-- Global Music & Audio Toggle -->
    <div class="fixed top-4 right-4 z-50 flex items-center gap-2">
        <label title="Test your own MP3 song right now" class="bg-white/80 backdrop-blur-md border border-cherry/20 px-2.5 py-2 rounded-full shadow-md hover:shadow-lg transition text-xs font-semibold flex items-center gap-1 text-warmBrown hover:text-cherry cursor-pointer">
            <i class="fa-solid fa-upload text-cherry"></i>
            <span class="hidden sm:inline">Change Song</span>
            <input type="file" accept="audio/*" class="hidden" onchange="loadCustomAudio(event)">
        </label>
        <button id="bgMusicBtn" onclick="toggleBGM()" class="bg-white/80 backdrop-blur-md border border-cherry/20 px-3 py-2 rounded-full shadow-md hover:shadow-lg transition text-xs font-semibold flex items-center gap-2 text-warmBrown hover:text-cherry cursor-pointer">
            <i class="fa-solid fa-music text-cherry"></i> <span id="bgMusicText">Play Song 🎵</span>
        </button>
    </div>

    <!-- Header bar -->
    <header class="w-full py-4 px-6 text-center border-b border-peach/30 bg-white/40 backdrop-blur-sm fixed top-0 left-0 right-0 z-40 flex justify-between items-center">
        <div class="flex items-center gap-2">
            <span class="text-xl">🎀</span>
            <h1 class="font-bold text-cherry text-sm sm:text-base tracking-wide uppercase">TO MY FAVOURITE AKKA 🎀</h1>
        </div>
        <div class="text-xs text-warmBrown/70 font-medium hidden sm:block">
            Step <span id="currentPageNum">1</span> of 10
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="w-full max-w-4xl mx-auto px-4 pt-24 pb-16 flex-grow flex items-center justify-center relative z-10">

        <!-- ==================== PAGE 1: PASSWORD GATE & THE GIFT SHE DIDN'T EXPECT ==================== -->
        <section id="page1" class="page-step active w-full text-center">
            
            <!-- STEP 1A: SECRET PASSWORD LOCK SCREEN -->
            <div id="passwordGateCard" class="bg-white/80 backdrop-blur-md rounded-3xl p-6 sm:p-10 border-2 border-blush shadow-2xl max-w-md mx-auto transition-all duration-500">
                <div class="w-20 h-20 mx-auto mb-4 bg-blush/60 rounded-full flex items-center justify-center text-4xl shadow-inner animate-float">
                    🔐
                </div>
                <span class="inline-block bg-lavender text-warmBrown text-xs font-bold px-3 py-1 rounded-full mb-2 uppercase tracking-wider">VIP Akka Access Only 🎀</span>
                <h2 class="text-2xl font-extrabold text-cherry mb-2">STOP RIGHT THERE, AKKAAA! 🛑😂</h2>
                <p class="text-xs sm:text-sm text-warmBrown/80 mb-5 leading-relaxed">
                    Idhu un thambi create panna secret universe! Entry venumna secret password podu paapom! 👀✨
                </p>

                <div class="bg-cream p-4 rounded-2xl border border-peach mb-5">
                    <p class="text-xs font-semibold text-warmBrown mb-2">💡 Hint: Un favourite person yaaru? (Type <span class="text-cherry font-extrabold">THAMBI</span> or <span class="text-cherry font-extrabold">AKKA</span>)</p>
                    <input type="text" id="secretPasswordInput" placeholder="Enter secret password..." 
                        onkeypress="if(event.key === 'Enter') checkSecretPassword()"
                        class="w-full text-center font-bold uppercase tracking-widest text-sm py-3 px-4 rounded-xl border-2 border-blush focus:border-cherry focus:outline-none bg-white text-warmBrown transition">
                </div>

                <p id="passwordErrorMsg" class="hidden text-xs font-bold text-cherry mb-4">
                    ❌ AYYO THAPPU AKKAAA! 😂 Hint-a olunga paaru di!
                </p>

                <button onclick="checkSecretPassword()" class="w-full bg-cherry hover:bg-red-600 text-white font-bold py-3.5 px-6 rounded-2xl shadow-lg hover:shadow-cherry/30 hover:scale-105 transition duration-200 text-sm flex items-center justify-center gap-2 cursor-pointer">
                    <span>UNLOCK MY BIRTHDAY UNIVERSE 🔓✨</span>
                </button>
            </div>

            <!-- STEP 1B: WELCOME GIFT SCREEN (Revealed after password) -->
            <div id="page1WelcomeCard" class="hidden bg-white/75 backdrop-blur-md rounded-3xl p-6 sm:p-10 border border-blush shadow-xl max-w-xl mx-auto transition-all duration-500">
                <!-- Cute SVG Mascot -->
                <div class="relative w-36 h-36 mx-auto mb-6 animate-float">
                    <svg viewBox="0 0 200 200" class="w-full h-full">
                        <!-- Cloud background -->
                        <path d="M40 120 C20 120 10 100 25 85 C15 65 35 45 55 55 C70 35 100 35 115 55 C135 45 155 65 145 85 C160 100 150 120 130 120 Z" fill="#DDECF8" opacity="0.7"/>
                        <!-- Bear Mascot -->
                        <circle cx="100" cy="90" r="45" fill="#67504A"/>
                        <circle cx="70" cy="55" r="16" fill="#67504A"/>
                        <circle cx="130" cy="55" r="16" fill="#67504A"/>
                        <circle cx="70" cy="55" r="9" fill="#F8DDE8"/>
                        <circle cx="130" cy="55" r="9" fill="#F8DDE8"/>
                        <!-- Face -->
                        <ellipse cx="100" cy="98" rx="18" ry="14" fill="#FFF9F0"/>
                        <circle cx="88" cy="85" r="5" fill="#222"/>
                        <circle cx="112" cy="85" r="5" fill="#222"/>
                        <ellipse cx="100" cy="94" rx="6" ry="4" fill="#67504A"/>
                        <!-- Cheeks -->
                        <circle cx="78" cy="92" r="6" fill="#F8DDE8" opacity="0.8"/>
                        <circle cx="122" cy="92" r="6" fill="#F8DDE8" opacity="0.8"/>
                        <!-- Ribbon Gift Box -->
                        <rect x="75" y="115" width="50" height="40" rx="6" fill="#C94B4B"/>
                        <rect x="95" y="115" width="10" height="40" fill="#F8DDE8"/>
                        <rect x="75" y="130" width="50" height="10" fill="#F8DDE8"/>
                        <!-- Bow -->
                        <path d="M90 115 C80 100 95 100 100 115 C105 100 120 100 110 115 Z" fill="#F8DDE8"/>
                    </svg>
                </div>

                <span class="inline-block bg-blush/60 text-cherry text-xs font-bold px-3 py-1 rounded-full mb-3 uppercase tracking-wider">Surprise Alert!</span>
                <h2 class="text-2xl sm:text-3xl font-extrabold text-cherry mb-2">OI AKKAAA! ORU GIFT IRUKKU DI! 👀🎀</h2>
                <p class="text-xs sm:text-sm text-warmBrown/70 font-medium mb-6">Your Thambi has a little surprise for you...</p>

                <div class="bg-cream/80 p-4 sm:p-5 rounded-2xl border border-peach/50 text-left text-sm text-warmBrown leading-relaxed mb-6 space-y-3">
                    <p>Heyyy, en favourite akka! ❤️</p>
                    <p>Un thambi unakkaga oru chinna surprise ready pannirukken!</p>
                    <p>Aana direct-ah gift kudukka maaten di. Konjam suspense, konjam comedy, konjam emotional torture irukkum! 😂</p>
                    <p class="font-semibold text-cherry">Last varaikkum paaru akka... Unakkaga oru special surprise waiting!</p>
                    <p>Seri sollu... En gift-a accept panriya?</p>
                </div>

                <div id="p1Buttons" class="flex flex-col sm:flex-row gap-3 justify-center">
                    <button onclick="p1Accept()" class="bg-cherry hover:bg-red-600 text-white font-bold py-3 px-6 rounded-2xl shadow-lg hover:shadow-cherry/30 hover:scale-105 transition duration-200 flex items-center justify-center gap-2 text-sm">
                        <span>YESSS, UN THAMBI! ❤️</span>
                    </button>
                    <button onclick="p1Reject()" class="bg-gray-100 hover:bg-gray-200 text-warmBrown font-bold py-3 px-6 rounded-2xl border border-warmBrown/20 transition duration-200 text-sm">
                        <span>NOOO, VENAM! 😂</span>
                    </button>
                </div>

                <!-- Hidden Rejected Modal / Warning inside page -->
                <div id="p1RejectMsg" class="hidden mt-6 p-4 bg-blush/80 rounded-2xl border border-cherry/30 text-center animate-bounce">
                    <p class="font-extrabold text-cherry text-base mb-1">ENNADIII AKKAAA?! 😭😂</p>
                    <p class="text-xs text-warmBrown mb-3">Un birthday-ku ivlo effort pottu website create pannirukken! Poi YES press pannu akka! Un thambi paavam! 🤣❤️</p>
                    <button onclick="p1Reset()" class="bg-warmBrown text-white font-bold text-xs py-2 px-4 rounded-xl hover:bg-warmBrown/80 transition">
                        TRY AGAIN, AKKA 😂
                    </button>
                </div>
            </div>
        </section>

        <!-- ==================== PAGE 2: A SECRET FROM YOUR THAMBI ==================== -->
        <section id="page2" class="page-step w-full text-center">
            <div class="bg-white/70 backdrop-blur-md rounded-3xl p-6 sm:p-10 border border-lavender shadow-xl max-w-xl mx-auto relative overflow-hidden">
                <!-- Decorative Elements -->
                <div class="absolute -top-6 -right-6 w-24 h-24 bg-lavender/40 rounded-full blur-xl"></div>
                <div class="absolute -bottom-6 -left-6 w-24 h-24 bg-blush/40 rounded-full blur-xl"></div>

                <!-- Cute Envelope Lock SVG -->
                <div class="w-32 h-32 mx-auto mb-4 relative">
                    <svg viewBox="0 0 200 200" class="w-full h-full">
                        <!-- Envelope -->
                        <rect x="30" y="60" width="140" height="90" rx="10" fill="#E8E0F5" stroke="#67504A" stroke-width="4"/>
                        <path d="M30 60 L100 115 L170 60" fill="none" stroke="#67504A" stroke-width="4"/>
                        <!-- Heart Stamp -->
                        <circle cx="145" cy="85" r="12" fill="#F8DDE8"/>
                        <path d="M145 88 C141 83 138 88 145 93 C152 88 149 83 145 88 Z" fill="#C94B4B"/>
                        <!-- Lock Pad -->
                        <circle cx="100" cy="115" r="22" fill="#F9D8C6" stroke="#67504A" stroke-width="3"/>
                        <path d="M94 105 A8 8 0 0 1 106 105 V110 H94 Z" fill="none" stroke="#67504A" stroke-width="3"/>
                        <circle cx="100" cy="116" r="3" fill="#67504A"/>
                    </svg>
                </div>

                <h2 class="text-2xl sm:text-3xl font-extrabold text-warmBrown mb-2">AKKA... UNAKKU ORU SECRET SOLLAVA? 💌</h2>
                <div class="w-16 h-1 bg-lavender mx-auto rounded-full mb-6"></div>

                <div class="bg-cream/90 p-5 rounded-2xl border border-lavender text-left text-sm text-warmBrown leading-relaxed mb-6 space-y-3">
                    <p>Theriyuma akka...</p>
                    <p>Namma rendu perum blood-la related illa.</p>
                    <p>Aana life unexpected-ah namma rendu perayum connect panniduchu.</p>
                    <p>Sila relationships namakku birth-aagumbodhe kidaikkum...</p>
                    <p>Sila relationships life namakku unexpected-ah gift pannum.</p>
                    <p class="font-bold text-cherry text-base">Nee enakku appadi kidaicha oru beautiful gift akka. 🫂❤️</p>
                    <p class="text-xs text-warmBrown/70 italic">Un thambi kitta innum neraya surprises irukku. Aana ovvonna open pannithaan paakanum! Hehe. 🤭</p>
                </div>

                <button id="unlockBtn" onclick="p2UnlockSecret()" class="bg-warmBrown hover:bg-warmBrown/90 text-white font-bold py-3 px-6 rounded-2xl shadow-lg hover:scale-105 transition duration-200 flex items-center justify-center gap-2 mx-auto text-sm">
                    <i class="fa-solid fa-key text-peach"></i>
                    <span>UNLOCK THE SECRET 🔐</span>
                </button>

                <div id="p2RevealedSecret" class="hidden mt-6 p-4 bg-lavender/60 border border-warmBrown/20 rounded-2xl text-warmBrown font-bold text-sm animate-pulse">
                    ✨ SECRET UNLOCKED: AKKA IS EXTRA SPECIAL. ❤️
                </div>
            </div>
        </section>

        <!-- ==================== PAGE 3: THREE GIFTS, THREE SECRETS ==================== -->
        <section id="page3" class="page-step w-full text-center">
            <div class="bg-white/70 backdrop-blur-md rounded-3xl p-6 sm:p-10 border border-peach shadow-xl max-w-2xl mx-auto">
                <h2 class="text-2xl sm:text-3xl font-extrabold text-cherry mb-2">CHOOSE YOUR LITTLE SURPRISE, AKKAAA! 🎀</h2>
                <p class="text-xs sm:text-sm text-warmBrown/70 font-medium mb-6">Each gift-kullayum oru different secret irukku. 👀</p>

                <!-- 3 Interactive Boxes -->
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-8">
                    <!-- Gift 1 -->
                    <div onclick="openGift(1)" id="giftCard1" class="cursor-pointer bg-cream border-2 border-blush hover:border-cherry p-5 rounded-2xl transition-all duration-300 hover:shadow-lg flex flex-col items-center">
                        <div class="w-16 h-16 mb-3 text-3xl flex items-center justify-center bg-blush rounded-2xl animate-float">
                            🎁
                        </div>
                        <h3 class="font-bold text-cherry text-sm mb-1">Gift 1</h3>
                        <p class="text-xs text-warmBrown/70">The Funny One 😂</p>
                    </div>

                    <!-- Gift 2 -->
                    <div onclick="openGift(2)" id="giftCard2" class="cursor-pointer bg-cream border-2 border-babyBlue hover:border-cherry p-5 rounded-2xl transition-all duration-300 hover:shadow-lg flex flex-col items-center">
                        <div class="w-16 h-16 mb-3 text-3xl flex items-center justify-center bg-babyBlue rounded-2xl animate-float" style="animation-delay: 0.5s;">
                            🎀
                        </div>
                        <h3 class="font-bold text-cherry text-sm mb-1">Gift 2</h3>
                        <p class="text-xs text-warmBrown/70">The Caring One 🫂</p>
                    </div>

                    <!-- Gift 3 -->
                    <div onclick="openGift(3)" id="giftCard3" class="cursor-pointer bg-cream border-2 border-lavender hover:border-cherry p-5 rounded-2xl transition-all duration-300 hover:shadow-lg flex flex-col items-center">
                        <div class="w-16 h-16 mb-3 text-3xl flex items-center justify-center bg-lavender rounded-2xl animate-float" style="animation-delay: 1s;">
                            💌
                        </div>
                        <h3 class="font-bold text-cherry text-sm mb-1">Gift 3</h3>
                        <p class="text-xs text-warmBrown/70">The Heartfelt One 💌</p>
                    </div>
                </div>

                <!-- Revealed Box Content Modal/Display area -->
                <div id="giftModal" class="hidden bg-cream p-5 rounded-2xl border border-cherry/30 text-left text-sm text-warmBrown mb-6 shadow-inner animate-fade-in">
                    <p id="giftModalText" class="font-medium leading-relaxed"></p>
                </div>

                <div id="p3CompletedMsg" class="hidden mb-6 text-cherry font-extrabold text-sm tracking-wide">
                    🎉 THREE SECRETS UNLOCKED! 🔓🎀
                </div>

                <button id="p3NextBtn" onclick="goToPage(4)" class="hidden bg-cherry hover:bg-red-600 text-white font-bold py-3 px-8 rounded-2xl shadow-lg hover:scale-105 transition duration-200 mx-auto text-sm">
                    NEXT SURPRISE, THAMBI! 👀
                </button>
            </div>
        </section>

        <!-- ==================== PAGE 4: OUR LITTLE MEMORY UNIVERSE ==================== -->
        <section id="page4" class="page-step w-full text-center">
            <div class="bg-white/80 backdrop-blur-md rounded-3xl p-6 sm:p-8 border border-blush shadow-xl max-w-3xl mx-auto">
                <span class="inline-block bg-peach/50 text-warmBrown text-xs font-bold px-3 py-1 rounded-full mb-2">Akka's Special Gallery 📸</span>
                <h2 class="text-2xl sm:text-3xl font-extrabold text-cherry mb-2">THE JOURNEY OF MY FAVOURITE AKKA ❤️</h2>
                <p class="text-xs sm:text-sm text-warmBrown/80 max-w-lg mx-auto mb-6">
                    Namma rendu perum serndhu edutha photos illana enna? Un chinna vayasu cuteness-la irundhu ippo varaikkum un azhagana moments ellam enakku romba special di! 🫂📸
                </p>

                <!-- Editable Polaroid Photo Grid -->
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 mb-8 text-left">
                    
                    <!-- Photo 1 -->
                    <div class="polaroid transform -rotate-2 rounded-lg">
                        <div class="relative group bg-gray-100 rounded overflow-hidden aspect-square mb-3">
                            <img id="img1" src="https://placehold.co/400x400/F8DDE8/67504A?text=Cute+Small+Age+Akka+👶" alt="Small Age Akka" class="w-full h-full object-cover">
                            <label class="absolute inset-0 bg-black/40 text-white opacity-0 group-hover:opacity-100 flex items-center justify-center text-xs font-bold cursor-pointer transition">
                                <i class="fa-solid fa-camera mr-1"></i> Add Childhood Photo
                                <input type="file" accept="image/*" class="hidden" onchange="loadPhoto(event, 'img1')">
                            </label>
                        </div>
                        <input id="cap1" type="text" value="CHINNA VAYASU CUTIE 👶🎀" class="w-full text-center text-xs font-bold text-warmBrown font-handwriting bg-transparent border-b border-dashed border-warmBrown/30 focus:outline-none">
                    </div>

                    <!-- Photo 2 -->
                    <div class="polaroid transform rotate-2 rounded-lg">
                        <div class="relative group bg-gray-100 rounded overflow-hidden aspect-square mb-3">
                            <img id="img2" src="https://placehold.co/400x400/DDECF8/67504A?text=That+Million+Dollar+Smile+✨" alt="Akka Smile" class="w-full h-full object-cover">
                            <label class="absolute inset-0 bg-black/40 text-white opacity-0 group-hover:opacity-100 flex items-center justify-center text-xs font-bold cursor-pointer transition">
                                <i class="fa-solid fa-camera mr-1"></i> Add Smile Photo
                                <input type="file" accept="image/*" class="hidden" onchange="loadPhoto(event, 'img2')">
                            </label>
                        </div>
                        <input id="cap2" type="text" value="UN AZHAGANA SMILE 😍✨" class="w-full text-center text-xs font-bold text-warmBrown font-handwriting bg-transparent border-b border-dashed border-warmBrown/30 focus:outline-none">
                    </div>

                    <!-- Photo 3 -->
                    <div class="polaroid transform -rotate-1 rounded-lg">
                        <div class="relative group bg-gray-100 rounded overflow-hidden aspect-square mb-3">
                            <img id="img3" src="https://placehold.co/400x400/E8E0F5/67504A?text=Pure+Beauty+Queen+👑" alt="Akka Beauty" class="w-full h-full object-cover">
                            <label class="absolute inset-0 bg-black/40 text-white opacity-0 group-hover:opacity-100 flex items-center justify-center text-xs font-bold cursor-pointer transition">
                                <i class="fa-solid fa-camera mr-1"></i> Add Portrait Photo
                                <input type="file" accept="image/*" class="hidden" onchange="loadPhoto(event, 'img3')">
                            </label>
                        </div>
                        <input id="cap3" type="text" value="MY GORGEOUS AKKA 👑❤️" class="w-full text-center text-xs font-bold text-warmBrown font-handwriting bg-transparent border-b border-dashed border-warmBrown/30 focus:outline-none">
                    </div>

                    <!-- Photo 4 -->
                    <div class="polaroid transform rotate-3 rounded-lg">
                        <div class="relative group bg-gray-100 rounded overflow-hidden aspect-square mb-3">
                            <img id="img4" src="https://placehold.co/400x400/F9D8C6/67504A?text=Traditional+/+Ethnic+Look+🌸" alt="Traditional Look" class="w-full h-full object-cover">
                            <label class="absolute inset-0 bg-black/40 text-white opacity-0 group-hover:opacity-100 flex items-center justify-center text-xs font-bold cursor-pointer transition">
                                <i class="fa-solid fa-camera mr-1"></i> Add Ethnic Photo
                                <input type="file" accept="image/*" class="hidden" onchange="loadPhoto(event, 'img4')">
                            </label>
                        </div>
                        <input id="cap4" type="text" value="ENNA AKKA, SEMMA LOOK! 🌸🔥" class="w-full text-center text-xs font-bold text-warmBrown font-handwriting bg-transparent border-b border-dashed border-warmBrown/30 focus:outline-none">
                    </div>

                    <!-- Photo 5 -->
                    <div class="polaroid transform -rotate-2 rounded-lg">
                        <div class="relative group bg-gray-100 rounded overflow-hidden aspect-square mb-3">
                            <img id="img5" src="https://placehold.co/400x400/FFF9F0/67504A?text=Goofy+%26+Candid+Moment+😂" alt="Candid Moment" class="w-full h-full object-cover">
                            <label class="absolute inset-0 bg-black/40 text-white opacity-0 group-hover:opacity-100 flex items-center justify-center text-xs font-bold cursor-pointer transition">
                                <i class="fa-solid fa-camera mr-1"></i> Add Candid Photo
                                <input type="file" accept="image/*" class="hidden" onchange="loadPhoto(event, 'img5')">
                            </label>
                        </div>
                        <input id="cap5" type="text" value="UN PAITHIYAKARA VIBE 😂💗" class="w-full text-center text-xs font-bold text-warmBrown font-handwriting bg-transparent border-b border-dashed border-warmBrown/30 focus:outline-none">
                    </div>

                    <!-- Photo 6 -->
                    <div class="polaroid transform rotate-1 rounded-lg">
                        <div class="relative group bg-gray-100 rounded overflow-hidden aspect-square mb-3">
                            <img id="img6" src="https://placehold.co/400x400/F8DDE8/67504A?text=Thambi's+Favourite+Pic+💖" alt="Favourite Pic" class="w-full h-full object-cover">
                            <label class="absolute inset-0 bg-black/40 text-white opacity-0 group-hover:opacity-100 flex items-center justify-center text-xs font-bold cursor-pointer transition">
                                <i class="fa-solid fa-camera mr-1"></i> Add Favourite Photo
                                <input type="file" accept="image/*" class="hidden" onchange="loadPhoto(event, 'img6')">
                            </label>
                        </div>
                        <input id="cap6" type="text" value="MY FAVOURITE AKKA ALWAYS 🫂✨" class="w-full text-center text-xs font-bold text-warmBrown font-handwriting bg-transparent border-b border-dashed border-warmBrown/30 focus:outline-none">
                    </div>

                </div>

                <p class="text-xs text-warmBrown/60 mb-6 italic">💡 Tip: Tap any photo frame above to upload Akka's small age photo, cute selfies, or best portraits!</p>

                <button onclick="goToPage(5)" class="bg-cherry hover:bg-red-600 text-white font-bold py-3 px-8 rounded-2xl shadow-lg hover:scale-105 transition duration-200 text-sm">
                    AKKA, INNUM NERAYA IRUKKU! 💗
                </button>
            </div>
        </section>

        <!-- ==================== PAGE 5: SIX REASONS YOU ARE MY FAVOURITE AKKA ==================== -->
        <section id="page5" class="page-step w-full text-center">
            <div class="bg-white/80 backdrop-blur-md rounded-3xl p-6 sm:p-10 border border-peach shadow-xl max-w-2xl mx-auto">
                <h2 class="text-2xl sm:text-3xl font-extrabold text-cherry mb-2">WHY YOU'RE MY FAVOURITE AKKA! 🥹❤️</h2>
                <p class="text-xs sm:text-sm text-warmBrown/70 font-medium mb-8">Each flower-kullayum oru chinna message irukku. Tap to bloom 🌷</p>

                <div class="grid grid-cols-2 sm:grid-cols-3 gap-4 mb-8">
                    <!-- Flower 1 -->
                    <div onclick="openFlower(1)" id="flower1" class="bg-cream border border-peach rounded-2xl p-4 cursor-pointer hover:border-cherry hover:shadow-md transition">
                        <div class="text-4xl mb-2 animate-bounce" style="animation-duration: 3s;">🌷</div>
                        <span class="text-xs font-bold text-cherry block">YOUR SMILE</span>
                    </div>

                    <!-- Flower 2 -->
                    <div onclick="openFlower(2)" id="flower2" class="bg-cream border border-peach rounded-2xl p-4 cursor-pointer hover:border-cherry hover:shadow-md transition">
                        <div class="text-4xl mb-2 animate-bounce" style="animation-duration: 2.5s;">🌸</div>
                        <span class="text-xs font-bold text-cherry block">PERSONALITY</span>
                    </div>

                    <!-- Flower 3 -->
                    <div onclick="openFlower(3)" id="flower3" class="bg-cream border border-peach rounded-2xl p-4 cursor-pointer hover:border-cherry hover:shadow-md transition">
                        <div class="text-4xl mb-2 animate-bounce" style="animation-duration: 3.2s;">🌺</div>
                        <span class="text-xs font-bold text-cherry block">YOUR DREAMS</span>
                    </div>

                    <!-- Flower 4 -->
                    <div onclick="openFlower(4)" id="flower4" class="bg-cream border border-peach rounded-2xl p-4 cursor-pointer hover:border-cherry hover:shadow-md transition">
                        <div class="text-4xl mb-2 animate-bounce" style="animation-duration: 2.8s;">🌻</div>
                        <span class="text-xs font-bold text-cherry block">YOUR HEART</span>
                    </div>

                    <!-- Flower 5 -->
                    <div onclick="openFlower(5)" id="flower5" class="bg-cream border border-peach rounded-2xl p-4 cursor-pointer hover:border-cherry hover:shadow-md transition">
                        <div class="text-4xl mb-2 animate-bounce" style="animation-duration: 3.5s;">🌹</div>
                        <span class="text-xs font-bold text-cherry block">OUR BOND</span>
                    </div>

                    <!-- Flower 6 -->
                    <div onclick="openFlower(6)" id="flower6" class="bg-cream border border-peach rounded-2xl p-4 cursor-pointer hover:border-cherry hover:shadow-md transition">
                        <div class="text-4xl mb-2 animate-bounce" style="animation-duration: 2.3s;">💐</div>
                        <span class="text-xs font-bold text-cherry block">SIMPLY YOU</span>
                    </div>
                </div>

                <!-- Flower Content Display -->
                <div id="flowerMsgBox" class="hidden bg-blush/40 p-5 rounded-2xl border border-cherry/30 text-sm text-warmBrown font-medium mb-6 animate-fade-in">
                    <p id="flowerMsgText"></p>
                </div>

                <div id="p5ConfirmedMsg" class="hidden mb-6 text-cherry font-extrabold text-sm tracking-wide">
                    OFFICIALLY CONFIRMED: EN THAMBI-KKU NEE FAVOURITE AKKAAA! 😂❤️
                </div>

                <button id="p5NextBtn" onclick="goToPage(6)" class="hidden bg-warmBrown hover:bg-warmBrown/90 text-white font-bold py-3 px-8 rounded-2xl shadow-lg hover:scale-105 transition duration-200 text-sm">
                    OKAY, NEXT PAGE-KKU POLAAM! 🎮
                </button>
            </div>
        </section>

        <!-- ==================== PAGE 6: AKKA VS THAMBI: THE SIBLING TEST ==================== -->
        <section id="page6" class="page-step w-full text-center">
            <div class="bg-white/80 backdrop-blur-md rounded-3xl p-6 sm:p-10 border border-babyBlue shadow-xl max-w-xl mx-auto">
                <span class="inline-block bg-babyBlue text-warmBrown text-xs font-bold px-3 py-1 rounded-full mb-3 uppercase tracking-wider">Mini Sibling Quiz 🎮</span>
                <h2 class="text-2xl sm:text-3xl font-extrabold text-cherry mb-4">AKKA VS THAMBI — YARU ROMBA LOOSU? 🤣</h2>

                <!-- Question Step Container -->
                <div id="quizContainer" class="bg-cream p-6 rounded-2xl border border-babyBlue mb-6 text-left">
                    <p id="quizQuestion" class="font-bold text-warmBrown text-base mb-4 text-center"></p>

                    <div id="quizOptions" class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                        <!-- Options injected via JS -->
                    </div>

                    <div id="quizFeedback" class="hidden mt-4 p-3 bg-blush/60 rounded-xl text-cherry font-bold text-xs text-center">
                    </div>
                </div>

                <button id="p6NextBtn" onclick="goToPage(7)" class="hidden bg-cherry hover:bg-red-600 text-white font-bold py-3 px-8 rounded-2xl shadow-lg hover:scale-105 transition duration-200 text-sm">
                    SERIOUS-AANA ORU CHINNA WISH IRUKKU... 🌙
                </button>
            </div>
        </section>

        <!-- ==================== PAGE 7: A WISH FROM YOUR THAMBI ==================== -->
        <section id="page7" class="page-step w-full text-center">
            <div id="page7SkyCard" class="bg-gradient-to-b from-warmBrown to-gray-900 text-cream rounded-3xl p-6 sm:p-10 shadow-2xl max-w-xl mx-auto relative overflow-hidden">
                <!-- Stars effect background -->
                <div class="absolute inset-0 opacity-40 pointer-events-none">
                    <div class="absolute top-4 left-10 text-yellow-200 text-xs animate-ping" style="animation-duration: 3s;">✨</div>
                    <div class="absolute top-20 right-12 text-yellow-200 text-base animate-pulse">⭐</div>
                    <div class="absolute bottom-16 left-16 text-yellow-200 text-sm animate-ping" style="animation-duration: 4s;">✨</div>
                </div>

                <div class="text-4xl mb-3">🌙</div>
                <h2 class="text-2xl sm:text-3xl font-extrabold text-peach mb-4">AKKA, UNAKKAGA ORU CHINNA WISH... ✨</h2>

                <div class="bg-white/10 backdrop-blur-md p-5 rounded-2xl border border-white/10 text-left text-xs sm:text-sm leading-relaxed mb-6 space-y-3 font-light">
                    <p>Akka...</p>
                    <p>Un life-la neraya beautiful things nadakkanum.</p>
                    <p>Nee nenacha dreams ellam achieve pannanum.</p>
                    <p>Unakku nalla opportunities kidaikkanum.</p>
                    <p>Unna respect panra, un happiness-a genuinely care panra people un life-la irukkanum.</p>
                    <p>Kashtamaana days vandhaalum, adha face panna strength kidaikkanum.</p>
                    <p class="font-semibold text-peach text-sm">Nee happy-ah irukkanum nu ellarum expect panraanga nu mattum illa... UNAKKUM HAPPY-A IRUKKA FULL RIGHT IRUKKU. ❤️</p>
                    <p>Un feelings important. Un dreams important. Un happiness important.</p>
                    <p class="italic">Idhellam un birthday-ku un thambi manasara wish panra wishes, akka. 🫂</p>
                <button onclick="p7MakeWish()" class="bg-peach hover:bg-peach/80 text-warmBrown font-bold py-3 px-6 rounded-2xl shadow-lg transition duration-200 flex items-center justify-center gap-2 mx-auto text-xs sm:text-sm mb-4 cursor-pointer">
                    <span>MAKE A WISH WITH A STAR ⭐</span>
                </button>

                <div id="p7StarWishMsg" class="hidden text-xs text-yellow-200 font-bold mb-6 animate-pulse">
                    ✨ UN WISH UNIVERSE-KKU SEND AAGIDUCHU! ✨<br>Ippo birthday celebration time! 🎂
                </div>

                <div id="p7NextBtnContainer" class="hidden">
                    <button onclick="goToPage(8)" class="bg-cherry hover:bg-red-600 text-white font-bold py-3 px-8 rounded-2xl shadow-lg hover:scale-105 transition duration-200 text-sm cursor-pointer">
                        LET'S CELEBRATE, AKKAAA! 🎉
                    </button>
                </div>
            </div>
        </section>

        <!-- ==================== PAGE 8: BIRTHDAY CELEBRATION ==================== -->
        <section id="page8" class="page-step w-full text-center">
            <div class="bg-white/80 backdrop-blur-md rounded-3xl p-6 sm:p-10 border border-blush shadow-xl max-w-2xl mx-auto">
                <span class="inline-block bg-blush text-cherry text-xs font-bold px-3 py-1 rounded-full mb-2">Grand Celebration 🥳</span>
                <h2 class="text-2xl sm:text-3xl font-extrabold text-cherry mb-2">HAPPIEST BIRTHDAY TO MY FAVOURITE AKKAAA! 🎂🎀</h2>
                
                <div class="bg-cream/90 p-5 rounded-2xl border border-peach/50 text-left text-xs sm:text-sm text-warmBrown leading-relaxed mb-6 space-y-2">
                    <p class="font-bold text-cherry text-base">FINALLYYYY, UN SPECIAL DAY VANDHURUCHU! 🥳❤️</p>
                    <p>Happy birthday, akkaaa!</p>
                    <p>Un life full-ah happiness irukkanum. Nee nenacha dreams ellam achieve pannanum.</p>
                    <p>Un thambi side-la irundhu oru big birthday hug! 🫂❤️</p>
                    <p class="font-semibold">Seri akka... candles blow pannalama?</p>
                </div>

                <!-- Interactive SVG Cake -->
                <div class="relative w-48 h-48 mx-auto mb-6">
                    <svg viewBox="0 0 200 200" class="w-full h-full">
                        <!-- Cake Stand -->
                        <ellipse cx="100" cy="170" rx="80" ry="15" fill="#E8E0F5"/>
                        <!-- Cake Base -->
                        <rect x="40" y="110" width="120" height="50" rx="8" fill="#F9D8C6"/>
                        <path d="M40 120 Q 60 130 80 120 Q 100 130 120 120 Q 140 130 160 120 L 160 110 L 40 110 Z" fill="#F8DDE8"/>
                        <!-- Top Layer -->
                        <rect x="55" y="75" width="90" height="40" rx="6" fill="#FFF9F0"/>
                        <path d="M55 85 Q 70 95 85 85 Q 100 95 115 85 Q 130 95 145 85 L 145 75 L 55 75 Z" fill="#C94B4B"/>
                        <!-- Candles -->
                        <!-- Candle 1 -->
                        <rect x="70" y="50" width="6" height="25" fill="#DDECF8"/>
                        <path id="flame1" d="M73 40 C68 46 78 46 73 50 Z" fill="#FFC107" class="animate-pulse"/>
                        <!-- Candle 2 (Center) -->
                        <rect x="97" y="45" width="6" height="30" fill="#F8DDE8"/>
                        <path id="flame2" d="M100 35 C95 41 105 41 100 45 Z" fill="#FFC107" class="animate-pulse"/>
                        <!-- Candle 3 -->
                        <rect x="124" y="50" width="6" height="25" fill="#DDECF8"/>
                        <path id="flame3" d="M127 40 C122 46 132 46 127 50 Z" fill="#FFC107" class="animate-pulse"/>
                    </svg>
                </div>

                <button id="blowBtn" onclick="p8BlowCandles()" class="bg-cherry hover:bg-red-600 text-white font-bold py-3 px-8 rounded-2xl shadow-lg hover:scale-105 transition duration-200 text-sm mb-4">
                    BLOW THE CANDLES! 🕯️
                </button>

                <div id="p8BdayWishMsg" class="hidden text-cherry font-extrabold text-base mb-6 animate-bounce">
                    MAKE A WISH, BIRTHDAY GIRL! ❤️🎂
                </div>

                <div id="p8FinalLetterPrompt" class="hidden bg-peach/40 p-4 rounded-2xl border border-cherry/20 text-center mb-6">
                    <p class="font-bold text-cherry text-sm mb-1">WAITTT, AKKAAA... 👀</p>
                    <p class="text-xs text-warmBrown mb-3">BIRTHDAY GIFT INNUM MUDIYALA! UN THAMBI-KITTA ORU LAST LETTER IRUKKU... 💌</p>
                    <button onclick="goToPage(9)" class="bg-warmBrown hover:bg-warmBrown/90 text-white font-bold py-3 px-8 rounded-2xl shadow-lg hover:scale-105 transition duration-200 text-sm">
                        OPEN YOUR FINAL LETTER ❤️
                    </button>
                </div>
            </div>
        </section>

        <!-- ==================== PAGE 9: EMOTIONAL LETTER FROM THAMBI ==================== -->
        <section id="page9" class="page-step w-full text-center">
            <div class="bg-white/90 backdrop-blur-md rounded-3xl p-6 sm:p-10 border border-peach shadow-2xl max-w-2xl mx-auto">
                <span class="inline-block bg-blush text-cherry text-xs font-bold px-3 py-1 rounded-full mb-2">Straight From Heart 💌</span>
                <h2 class="text-2xl sm:text-3xl font-extrabold text-warmBrown mb-4">EN FAVOURITE AKKAKKU, UN THAMBI EZHUDHURA LETTER... 🥹❤️</h2>

                <!-- Closed Envelope state -->
                <div id="p9ClosedEnvelope" class="my-8">
                    <div class="w-32 h-32 mx-auto mb-4 bg-blush/60 rounded-3xl flex items-center justify-center text-5xl shadow-inner border border-cherry/20 animate-float">
                        ✉️
                    </div>
                    <button onclick="p9OpenLetter()" class="bg-cherry hover:bg-red-600 text-white font-bold py-3 px-8 rounded-2xl shadow-lg hover:scale-105 transition duration-200 text-sm">
                        OPEN MY LETTER 💌
                    </button>
                </div>

                <!-- Open Letter view -->
                <div id="p9OpenedLetter" class="hidden text-left bg-cream p-6 sm:p-8 rounded-2xl border border-peach shadow-inner my-6 text-xs sm:text-sm text-warmBrown leading-relaxed space-y-4 max-h-[450px] overflow-y-auto">
                    <p class="font-bold text-cherry text-base">Hey en favourite akka... ❤️</p>
                    <p class="font-bold text-cherry">First of all, HAPPIEST BIRTHDAY DI! 🥹🎂</p>
                    
                    <p>Unakku theriyuma akka... Namma blood siblings illa nu sonnaalum, enakku nee oru real akka dhaan.</p>
                    <p>Namma rendu perum ore family-la born aagala. Aana life namma rendu perayum connect panniduchu. Andha bond enakku romba special.</p>
                    <p>Sila relationships namakku birth-aagumbodhe kidaikkum... Sila relationships namma life-la unexpected-ah vandhu, family maadhiri special aagidum. Nee enakku appadi kidaicha oru akka. 🫂❤️</p>
                    
                    <p>Naan perfect thambi-ah iruppen nu solla maaten. Sila neram unna kalaaippen, silly-ah pesuven, unna irritate pannalaam... 😂 Aana adhellam oru pakkam irundhaalum, nee enakku special nu mattum eppovume change aagadhu.</p>
                    
                    <p>Unakku kashtam varumbodhu, nee thaniya ellathayum handle pannanum nu feel pannadha. Unakku support panna mudinja varaikkum naan try pannuven. Un happiness-a celebrate panna, un success-ku happy-a irukka, un dreams-a encourage panna oru thambi-ah irukkanum nu aasai.</p>
                    
                    <p>Namma future-la busy aagalaam. Life change aagalaam. Neraya pudhu memories create pannalaam. Aana indha bond namma rendu perukkum special-ah irukkanum nu naan genuinely wish panren.</p>
                    
                    <div class="p-3 bg-blush/40 border-l-4 border-cherry text-cherry font-extrabold text-sm my-4 rounded-r-xl">
                        BLOOD RELATION ILLANA ENNA? NEE EN AKKAA DHAAN! ❤️🫂
                    </div>
                    
                    <p>Unna kalaaikka oru thambi... Un kooda sirikka oru thambi... Unakku support panna try pannura oru thambi... Un birthday-ku ivlo scene podra oru thambi! 😂🎀 Andha thambi naan dhaan akka!</p>

                    <p>Un life full-ah happiness irukkanum. Un dreams ellam konjam konjama reality aaganum. Unakku pudicha life-a nee build pannanum. Nee happy-ah irukkanum, healthy-ah irukkanum, and unakku nee evlo special nu eppovum theriyanum.</p>

                    <p>Thank you en life-la vandhadhukku. Thank you enakku oru akka maadhiri aanaadhukku. Thank you indha bond-a special aakkuradhukku.</p>

                    <p class="font-bold text-cherry text-base mt-4">Happy birthday, en chella akka! ❤️<br>LOVE YOU SO MUCH, AKKA! 🫂🎀</p>
                    <p class="font-handwriting text-xl text-warmBrown font-bold text-right">— UN THAMBI, ALWAYS. ❤️</p>
                </div>

                <div id="p9Footer" class="hidden">
                    <p class="text-xs font-bold text-warmBrown/70 uppercase tracking-widest mb-6">NOT BY BLOOD, BUT BONDED LIKE SIBLINGS. ❤️</p>
                    <button onclick="goToPage(10)" class="bg-cherry hover:bg-red-600 text-white font-bold py-3 px-8 rounded-2xl shadow-lg hover:scale-105 transition duration-200 text-sm">
                        AKKA... UNAKKU INNUM ORU LAST SURPRISE IRUKKU! 👀🎬
                    </button>
                </div>
            </div>
        </section>

        <!-- ==================== PAGE 10: PERSONAL BIRTHDAY VIDEO & FINAL SURPRISE ==================== -->
        <section id="page10" class="page-step w-full text-center">
            <div class="bg-gradient-to-b from-peach/30 via-cream to-blush/30 backdrop-blur-md rounded-3xl p-6 sm:p-10 border border-cherry/30 shadow-2xl max-w-2xl mx-auto relative overflow-hidden">
                <!-- Film Strip Decoration -->
                <div class="w-full bg-warmBrown text-white text-xs py-1 px-4 mb-6 flex justify-between rounded-lg font-mono">
                    <span>🎬 THAMBI_PRODUCTIONS</span>
                    <span>AKKA_SPECIAL_V1.MP4</span>
                </div>

                <h2 class="text-2xl sm:text-3xl font-extrabold text-cherry mb-2">AKKAAA... THIS LAST GIFT IS JUST FOR YOU. 🥹🎬</h2>
                <p class="text-xs sm:text-sm text-warmBrown/80 font-medium mb-4">Words-la solla mudiyadha sila feelings... indha chinna video-la irukku. ❤️</p>

                <div class="bg-white/80 p-5 rounded-2xl border border-peach text-left text-xs sm:text-sm text-warmBrown leading-relaxed mb-6">
                    <p class="mb-2">Indha varaikkum nee en website-la neraya surprises paathutta...</p>
                    <p class="mb-2">Aana last-a oru surprise irukku. Idha un thambi unakkaga special-ah vechurukken.</p>
                    <p class="font-bold text-cherry text-center text-base">Ready-ah, akka? 💌</p>
                </div>

                <!-- Video Reveal Gift Box -->
                <div id="p10VideoBox" class="my-6">
                    <div class="w-28 h-28 mx-auto mb-4 bg-cherry text-white rounded-3xl flex items-center justify-center text-4xl shadow-xl animate-bounce">
                        🎁
                    </div>
                    <button onclick="p10RevealVideo()" class="bg-cherry hover:bg-red-600 text-white font-bold py-3 px-8 rounded-2xl shadow-lg hover:scale-105 transition duration-200 text-sm">
                        OPEN YOUR FINAL GIFT 🎁
                    </button>
                </div>

                <!-- Embedded Video Container (Revealed on click) -->
                <div id="p10VideoContainer" class="hidden my-6">
                    <div class="relative w-full rounded-2xl overflow-hidden shadow-2xl border-4 border-white bg-black aspect-video mb-4">
                        <!-- Customizable Video HTML5 Tag with Fallback UI -->
                        <video id="akkaBdayVideo" controls class="w-full h-full object-cover">
                            <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
                            Your browser does not support HTML video.
                        </video>
                    </div>

                    <div class="bg-cream p-4 rounded-xl border border-peach text-xs text-warmBrown mb-4 text-left">
                        <p class="font-bold text-cherry mb-1">💡 Note for Thambi:</p>
                        <p class="mb-2">You can replace the video source URL inside the HTML code (`#akkaBdayVideo source`) with your actual Google Drive video link or custom MP4 video file!</p>
                        <label class="inline-block bg-warmBrown text-white text-xs px-3 py-1.5 rounded-lg cursor-pointer font-bold">
                            <i class="fa-solid fa-upload mr-1"></i> Upload Video File Now
                            <input type="file" accept="video/*" class="hidden" onchange="loadCustomVideo(event)">
                        </label>
                    </div>
                </div>

                <!-- Final Heartfelt Footer -->
                <div class="mt-8 pt-6 border-t border-warmBrown/20">
                    <p class="font-handwriting text-2xl text-cherry font-bold mb-1">From your little Thambi, with a big heart. ❤️</p>
                    <p class="text-xs text-warmBrown/70 font-semibold">"Not siblings by blood, but connected by a bond that feels like family."</p>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer navigation bar -->
    <footer class="w-full py-4 px-6 border-t border-peach/30 bg-white/40 backdrop-blur-sm text-center text-xs text-warmBrown/60">
        <p>Created with ❤️ by Thambi for his favourite Akka • 2026</p>
    </footer>

    <!-- JavaScript Logic -->
    <script>
        // ================= CONFIGURE PASSWORD HERE =================
        // You can change or add any secret passwords here (case-insensitive)
        const VALID_PASSWORDS = ["THAMBI", "AKKA", "MYTHAMBI", "BESTAKKA", "1234"];

        // Spawn gentle floating hearts & stars across the screen
        function initAmbientParticles() {
            const container = document.getElementById('ambientParticles');
            const symbols = ['🎀', '✨', '❤️', '🌸', '⭐', '💌'];
            for (let i = 0; i < 16; i++) {
                const el = document.createElement('div');
                el.className = 'bg-particle text-sm sm:text-base opacity-60';
                el.innerText = symbols[i % symbols.length];
                el.style.left = `${Math.random() * 95}%`;
                el.style.animationDuration = `${9 + Math.random() * 10}s`;
                el.style.animationDelay = `${Math.random() * 8}s`;
                container.appendChild(el);
            }
        }
        window.addEventListener('DOMContentLoaded', initAmbientParticles);

        // Password Validation Logic
        function checkSecretPassword() {
            const input = document.getElementById('secretPasswordInput');
            const errorMsg = document.getElementById('passwordErrorMsg');
            const gateCard = document.getElementById('passwordGateCard');
            const welcomeCard = document.getElementById('page1WelcomeCard');
            const entered = input.value.trim().toUpperCase();

            if (VALID_PASSWORDS.includes(entered)) {
                errorMsg.classList.add('hidden');
                confetti({ particleCount: 70, spread: 75, origin: { y: 0.6 } });
                gateCard.classList.add('hidden');
                welcomeCard.classList.remove('hidden');
                welcomeCard.style.animation = 'float 4s ease-in-out infinite';
            } else {
                errorMsg.classList.remove('hidden');
                gateCard.classList.remove('animate-shake');
                void gateCard.offsetWidth; // trigger reflow to restart shake animation
                gateCard.classList.add('animate-shake');
            }
        }

        // State tracking
        let currentPage = 1;
        let openedGiftsCount = 0;
        let openedFlowersCount = 0;
        let currentQuizIndex = 0;
        let isBgmPlaying = false;

        // Quiz Data for Page 6
        // Password Validation Logic
        function checkSecretPassword() {
            const input = document.getElementById('secretPasswordInput');
            const errorMsg = document.getElementById('passwordErrorMsg');
            const gateCard = document.getElementById('passwordGateCard');
            const welcomeCard = document.getElementById('page1WelcomeCard');
            const entered = input.value.trim().toUpperCase();

            if (VALID_PASSWORDS.includes(entered)) {
                errorMsg.classList.add('hidden');
                confetti({ particleCount: 70, spread: 75, origin: { y: 0.6 } });
                gateCard.classList.add('hidden');
                welcomeCard.classList.remove('hidden');
                welcomeCard.style.animation = 'float 4s ease-in-out infinite';

                // Auto-start your custom song when she unlocks the universe!
                const audio = document.getElementById('customBgmAudio');
                if (audio && !isBgmPlaying) {
                    audio.play().then(() => {
                        isBgmPlaying = true;
                        document.getElementById('bgMusicText').innerText = "Pause Song ⏸️";
                    }).catch(() => {
                        // Browser requires manual click if song.mp3 isn't uploaded yet
                    });
                }
            } else {
                errorMsg.classList.remove('hidden');
                gateCard.classList.remove('animate-shake');
                void gateCard.offsetWidth; // trigger reflow to restart shake animation
                gateCard.classList.add('animate-shake');
            }
        }

        // Page Switcher Helper
        function goToPage(pageNum) {
            document.querySelectorAll('.page-step').forEach(p => p.classList.remove('active'));
            const target = document.getElementById(`page${pageNum}`);
            if (target) {
                target.classList.add('active');
                currentPage = pageNum;
                document.getElementById('currentPageNum').innerText = pageNum;
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }

            // Page specific initializations
            if (pageNum === 6) {
                loadQuizStep(0);
            }
        }

        // PAGE 1 LOGIC
        function p1Accept() {
            confetti({ particleCount: 50, spread: 60, origin: { y: 0.6 } });
            goToPage(2);
        }
        function p1Reject() {
            document.getElementById('p1RejectMsg').classList.remove('hidden');
        }
        function p1Reset() {
            document.getElementById('p1RejectMsg').classList.add('hidden');
        }

        // PAGE 2 LOGIC
        function p2UnlockSecret() {
            document.getElementById('p2RevealedSecret').classList.remove('hidden');
            setTimeout(() => {
                goToPage(3);
            }, 1800);
        }

        // PAGE 3 LOGIC
        const giftMessages = {
            1: "Akka, unna kalaaikkaradhu enakku romba pudikkum! 😂\nNee enna thittinaalum, naan thirumba kalaaippen.\nUnna konjam irritate pannradhu en thambi duty maadhiri aagiduchu! 🤣❤️",
            2: "Akka, nee kashtama irukkumbodhu ellathayum thaniya handle pannanum nu avasiyam illa.\nMudinja varaikkum unakku support-ah irukka naan try pannuven.\nUn happiness enakku important di. ❤️",
            3: "Namma blood siblings illa naalum, nee enakku oru real akka maadhiri special.\nEn life-la nee occupy panra place romba precious.\nAndha bond enakku eppovume special dhaan. 🥹❤️"
        };
        const openedGifts = new Set();

        function openGift(id) {
            const modal = document.getElementById('giftModal');
            const text = document.getElementById('giftModalText');
            modal.classList.remove('hidden');
            text.innerText = giftMessages[id];

            document.getElementById(`giftCard${id}`).classList.add('bg-blush/50', 'border-cherry');
            openedGifts.add(id);

            if (openedGifts.size === 3) {
                document.getElementById('p3CompletedMsg').classList.remove('hidden');
                document.getElementById('p3NextBtn').classList.remove('hidden');
                confetti({ particleCount: 40, spread: 50 });
            }
        }

        // PAGE 4 PHOTO LOADER
        function loadPhoto(event, imgId) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById(imgId).src = e.target.result;
                }
                reader.readAsDataURL(file);
            }
        }

        // PAGE 5 FLOWER LOGIC
        const flowerMsgs = {
            1: "Un smile eppovum ippadiye irukkanum akka! Nee happy-ah irukkuradhu romba mukkiyam.",
            2: "Nee unmaiya nee-ya irukkuradhu dhaan un special quality.",
            3: "Un dreams ellam achieve pannanum nu un thambi manasara wish panraan.",
            4: "Unakku nee evlo special nu sila neram theriyama irukkalaam. Aana un value romba mukkiyam.",
            5: "Namma blood relation illa naalum, namma bond enakku romba precious.",
            6: "Enna reason-um thevai illa akka... nee enakku favourite akka dhaan!"
        };
        const openedFlowers = new Set();

        function openFlower(id) {
            const box = document.getElementById('flowerMsgBox');
            const txt = document.getElementById('flowerMsgText');
            box.classList.remove('hidden');
            txt.innerText = flowerMsgs[id];

            openedFlowers.add(id);
            document.getElementById(`flower${id}`).classList.add('bg-blush', 'border-cherry');

            if (openedFlowers.size === 6) {
                document.getElementById('p5ConfirmedMsg').classList.remove('hidden');
                document.getElementById('p5NextBtn').classList.remove('hidden');
                confetti({ particleCount: 50, spread: 70 });
            }
        }

        // PAGE 6 QUIZ LOGIC
        function loadQuizStep(index) {
            currentQuizIndex = index;
            const item = quizData[index];
            document.getElementById('quizQuestion').innerText = `Q${index+1}: ${item.q}`;
            document.getElementById('quizFeedback').classList.add('hidden');

            const optsDiv = document.getElementById('quizOptions');
            optsDiv.innerHTML = '';
            item.opts.forEach(opt => {
                const btn = document.createElement('button');
                btn.className = "bg-white hover:bg-blush border border-babyBlue text-warmBrown font-bold py-3 px-4 rounded-xl text-xs transition duration-200";
                btn.innerText = opt;
                btn.onclick = () => answerQuiz(item.ans);
                optsDiv.appendChild(btn);
            });
        }

        function answerQuiz(feedbackText) {
            const fb = document.getElementById('quizFeedback');
            fb.innerText = feedbackText;
            fb.classList.remove('hidden');

            setTimeout(() => {
                if (currentQuizIndex < quizData.length - 1) {
                    loadQuizStep(currentQuizIndex + 1);
                } else {
                    document.getElementById('quizContainer').classList.add('opacity-80');
                    document.getElementById('p6NextBtn').classList.remove('hidden');
                }
            }, 1500);
        }

        // PAGE 7 STAR WISH
        function p7MakeWish() {
            // Spawn shooting stars inside Page 7 night sky
            const skyCard = document.getElementById('page7SkyCard');
            if (skyCard) {
                for (let i = 0; i < 4; i++) {
                    setTimeout(() => {
                        const star = document.createElement('div');
                        star.className = 'shooting-star';
                        star.style.top = `${10 + Math.random() * 40}%`;
                        star.style.left = `${Math.random() * 40}%`;
                        skyCard.appendChild(star);
                        setTimeout(() => star.remove(), 1300);
                    }, i * 250);
                }
            }

            try {
                if (typeof confetti === 'function') {
                    confetti({ particleCount: 40, spread: 100, origin: { y: 0.5 } });
                }
            } catch(e) {
                console.log("Confetti trigger skipped", e);
            }
            const wishMsg = document.getElementById('p7StarWishMsg');
            const nextContainer = document.getElementById('p7NextBtnContainer');
            
            if (wishMsg) wishMsg.classList.remove('hidden');
            if (nextContainer) nextContainer.classList.remove('hidden');
        }

        // PAGE 8 CANDLE BLOWING
        function p8BlowCandles() {
            document.getElementById('flame1').setAttribute('fill', 'transparent');
            document.getElementById('flame2').setAttribute('fill', 'transparent');
            document.getElementById('flame3').setAttribute('fill', 'transparent');

            confetti({
                particleCount: 100,
                spread: 70,
                origin: { y: 0.6 }
            });

            document.getElementById('p8BdayWishMsg').classList.remove('hidden');
            document.getElementById('blowBtn').classList.add('hidden');
            
            setTimeout(() => {
                document.getElementById('p8FinalLetterPrompt').classList.remove('hidden');
            }, 1000);
        }

        // PAGE 9 LETTER REVEAL
        function p9OpenLetter() {
            document.getElementById('p9ClosedEnvelope').classList.add('hidden');
            document.getElementById('p9OpenedLetter').classList.remove('hidden');
            document.getElementById('p9Footer').classList.remove('hidden');
            confetti({ particleCount: 40, spread: 60 });
        }

        // PAGE 10 VIDEO REVEAL
        function p10RevealVideo() {
            document.getElementById('p10VideoBox').classList.add('hidden');
            document.getElementById('p10VideoContainer').classList.remove('hidden');
            confetti({ particleCount: 120, spread: 90, origin: { y: 0.5 } });
        }

        function loadCustomVideo(event) {
            const file = event.target.files[0];
            if (file) {
                const videoNode = document.getElementById('akkaBdayVideo');
                const fileURL = URL.createObjectURL(file);
                videoNode.src = fileURL;
                videoNode.play();
            }
        }

        // Custom MP3 Song Player & Uploader
        function loadCustomAudio(event) {
            const file = event.target.files[0];
            if (file) {
                const audioNode = document.getElementById('customBgmAudio');
                audioNode.src = URL.createObjectURL(file);
                audioNode.play().then(() => {
                    isBgmPlaying = true;
                    document.getElementById('bgMusicText').innerText = "Pause Song ⏸️";
                });
            }
        }

        function toggleBGM() {
            const audioNode = document.getElementById('customBgmAudio');
            const btnText = document.getElementById('bgMusicText');

            if (isBgmPlaying) {
                audioNode.pause();
                isBgmPlaying = false;
                btnText.innerText = "Play Song 🎵";
            } else {
                audioNode.play().then(() => {
                    isBgmPlaying = true;
                    btnText.innerText = "Pause Song ⏸️";
                }).catch(() => {
                    alert("Upload 'song.mp3' to your GitHub repo or tap the upload icon next to Play Song to pick an MP3 file! 🎵");
                });
            }
        }
    </script>
</body>
</html>

```
