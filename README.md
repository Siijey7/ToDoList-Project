<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BSCS 2 B Status Celebration</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'background-dark': '#1e293b', 
                        'celebration-coral': '#FF7F50', 
                        'celebration-gold': '#FFD700',   
                        'text-light': '#f8fafc', 
                        'text-dark-card': '#334155' 
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    keyframes: {
                        pulseNeon: {
                            '0%, 100%': { transform: 'scale(1)', filter: 'drop-shadow(0 0 10px rgba(255, 127, 80, 0.7))' },
                            '50%': { transform: 'scale(1.05)', filter: 'drop-shadow(0 0 20px rgba(255, 127, 80, 1))' },
                        },
                    },
                    animation: {
                        pulseNeon: 'pulseNeon 2s ease-in-out infinite',
                    }
                }
            }
        }
    </script>
    <style>
        .card-container {
            perspective: 1000px;
        }

        .card {
            width: 100%;
            height: 100%;
            transform-style: preserve-3d;
            transition: transform 1.2s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        .card-face {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            border-radius: 1.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 2rem;
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.4), 0 10px 10px -5px rgba(0, 0, 0, 0.2);
            border: 3px solid rgba(255, 255, 255, 0.15);
        }

        .card-back {
            transform: rotateY(180deg);
        }

        .card-container:target .card {
            transform: rotateY(180deg);
        }

        .card-container:not(:target) .reveal-button {
            animation: pulseNeon 2s ease-in-out infinite; 
        }

        .reset-link {
             text-decoration: none;
        }

        .message-scroll-area::-webkit-scrollbar {
            width: 8px;
        }
        .message-scroll-area::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
        }
        .message-scroll-area::-webkit-scrollbar-thumb {
            background-color: rgba(255, 255, 255, 0.3);
            border-radius: 10px;
            border: 2px solid rgba(255, 255, 255, 0.1);
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
</head>
<body class="bg-background-dark min-h-screen flex items-center justify-center font-sans p-4">

    <audio id="celebration-sound" src="https://assets.mixkit.co/sfx/preview/mixkit-happy-birthday-song-3037.mp3" preload="auto"></audio>

    <main class="w-full max-w-2xl text-center"> 
        <h1 class="text-4xl sm:text-5xl font-extrabold mb-8 text-white tracking-tight">
            **BSCS 2 B** <span class="text-celebration-gold">Status Celebration!</span>
        </h1>

        <div id="surprise-container" class="card-container w-full h-[550px] sm:h-[600px]"> 
            <div class="card">

                <div class="card-face bg-gradient-to-br from-gray-700 to-gray-800 border-celebration-gold">
                    <div class="space-y-8 p-4">
                        
                        <svg class="mx-auto w-32 h-32 text-celebration-gold" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                             <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                             <path d="M11 19c-3.1 0-5.6-2.5-5.6-5.6S7.9 7.8 11 7.8s5.6 2.5 5.6 5.6-2.5 5.6-5.6 5.6z" fill="#FFD700" stroke="none"/>
                             <path d="M12 11h.01M12 15h.01M10 13h4M12 3v3m-4 4L7 9m10 1l1-1m-4 10v-3m-3 0h6a2 2 0 002-2V7a2 2 0 00-2-2h-3l-2-2-2 2H7a2 2 0 00-2 2v10a2 2 0 002 2h6z" stroke="#FF7F50"/>
                        </svg>

                        <p class="text-gray-300 text-xl font-semibold">
                            Hello, Sir Gio Albert Montano! This is a special birthday card from the students of BSCS 2 B. Click below to receive your birthday message!
                        </p>

                        <a onclick="playCelebrationSound()" href="#surprise-container" id="revealButton" class="reveal-button inline-block px-8 py-3 bg-celebration-coral text-background-dark font-bold rounded-full shadow-lg hover:shadow-celebration-coral transition duration-300 ease-in-out transform hover:scale-105 border-2 border-celebration-coral">
                            <span class="text-lg">Open Birthday Card!</span>
                        </a>
                    </div>
                </div>

                <div class="card-face card-back bg-gradient-to-tl from-celebration-gold to-celebration-coral text-text-dark-card overflow-hidden">
                    <div class="flex flex-col items-center justify-start h-full p-4 sm:p-6 text-center space-y-4">
                        
                        <svg class="mx-auto w-32 h-32 text-celebration-coral mb-2" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <rect x="5" y="35" width="40" height="10" rx="3" fill="#FFD700"/>
                            <rect x="10" y="25" width="30" height="10" rx="3" fill="#FF7F50"/>
                            <rect x="15" y="15" width="20" height="10" rx="3" fill="#FFFFFF"/>
                            <path d="M15 15 C17 18, 19 18, 20 15 M25 15 C26 18, 28 18, 30 15 M35 15 C33 18, 31 18, 30 15" fill="#FF7F50"/>
                            <rect x="20" y="10" width="2" height="5" fill="#FFD700"/>
                            <rect x="28" y="10" width="2" height="5" fill="#FFD700"/>
                            <path d="M20 10 L21 7 L22 10 Z" fill="#FF7F50"/>
                            <path d="M28 10 L29 7 L30 10 Z" fill="#FF7F50"/>
                        </svg>

                        <img src="https://scontent.fceb6-1.fna.fbcdn.net/v/t39.30808-6/481140241_122223187364091148_4397234662320790934_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=a5f93a&_nc_eui2=AeEgYy8oMpU5-TKKZSbdHNWUEZiBd6j0vHYRmIF3qPS8djXi-QqX81R1jEIt_NpAIL5CgOnFw3hgrAWR01l_vyfO&_nc_ohc=a-h64Hus4egQ7kNvwEHuoDK&_nc_oc=Adkg2DK8ocQ23MWkRia4s6Mx0sHxdw0dk1o1_OT0PruN3VdovFGYBViVN7lyX5I4vS4&_nc_zt=23&_nc_ht=scontent.fceb6-1.fna&_nc_gid=xOBzQ4MFh66iCy7oy30P3w&oh=00_Afcx_Jg3AyQNSo3SIaYpZfXgn-KJ7qf67jjmj96DHAwJHQ&oe=68F3F3D5" alt="Instructor's Photo" class="w-32 h-32 sm:w-40 sm:h-40 rounded-full object-cover border-4 border-white shadow-lg mb-4">
                        <h2 class="text-4xl sm:text-5xl font-black tracking-tight leading-tight text-white">
                            HAPPY BIRTHDAY!
                        </h2>

                        <div class="message-scroll-area text-md sm:text-lg flex-grow overflow-y-auto w-full max-w-md px-2 py-3 bg-white/70 rounded-lg shadow-inner text-text-dark-card leading-relaxed">
                            <p class="mb-3">Dear Gio Albert Montano,</p>

                            <p class="mb-3">
                                Please accept our formal greetings for your birthday. We hope you have a very happy day.
                            </p>

                            <p class="mb-3">
                                We, your students, wish to thank you for your commitment to teaching. Your clear lessons on Data Structures and coding help us greatly in our studies. We also value the life lessons and good advice you share with us.
                            </p>

                            <p class="mb-3">
                                Your support makes our class a good place to learn. We appreciate your time and effort. We wish you success and happiness in the coming year.
                            </p>

                            <p class="mt-4 pt-4 text-sm font-bold border-t border-celebration-coral/50">
                                A Small Gift: A Pokémon-Themed Joke
                            </p>
                            <p class="text-sm italic">
                                You know, Professor Oak always warned trainers about the dangers of the tall grass, but he never mentioned the biggest threat to your Pokedex: the server running a simple **Data Structure** query. I was trying to find a truly rare Pokémon, like a shiny Snorlax, but the search crashed because the database was using a Bubble Sort instead of a Quick Sort. It was so slow, I think even a Magikarp could've outpaced that algorithm. Maybe that's why trainers are always yelling, 'Gotta catch 'em all!' It's not about collecting; it's about trying to **Catch The Exception** before the system bluescreens! We hope your birthday runs smoothly without any segmentation faults!
                            </p>

                            <p class="mt-4 text-sm italic">Sincerely,</p>
                            <p class="text-sm italic">Your Students</p>
                        </div>

                        <a href="#" class="reset-link inline-block text-background-dark bg-white/90 px-6 py-2 font-bold rounded-full shadow-md hover:bg-white transition duration-300 mt-4">
                            (Close Card)
                        </a>
                    </div>
                </div>

            </div>
        </div>

        <p class="mt-8 text-gray-500 text-sm">
            From: BSCS 2 B Students | Card Designer: BSCS 2B | Status: Status: Celebrating!
        </p>
    </main>

    <script>
        function playCelebrationSound() {
            const audio = document.getElementById('celebration-sound');
            if (audio) {
                audio.currentTime = 0; 
                audio.play().catch(error => {
                    console.warn("Audio playback failed (due to browser autoplay policy):", error);
                });
            }
        }
    </script>
</body>
</html>
