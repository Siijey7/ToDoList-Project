<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday Project!</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            'birthday-pink': '#FFB6C1',
            'birthday-blue': '#87CEFA',
            'birthday-gold': '#FFD700',
            'birthday-purple': '#C084FC',
            'birthday-white': '#FFF8F0',
          },
          fontFamily: {
            sans: ['Poppins', 'sans-serif'],
          },
          keyframes: {
            pulseNeon: {
              '0%, 100%': { transform: 'scale(1)', filter: 'drop-shadow(0 0 10px rgba(255, 182, 193, 0.7))' },
              '60%': { transform: 'scale(1.05)', filter: 'drop-shadow(0 0 20px rgba(255, 182, 193, 1))' },
            },
            confetti: {
              '0%': { transform: 'translateY(0) rotate(0)' },
              '100%': { transform: 'translateY(100vh) rotate(360deg)' }
            }
          },
          animation: {
            pulseNeon: 'pulseNeon 2s ease-in-out infinite',
            confetti: 'confetti 6s linear infinite',
          }
        }
      }
    }
  </script>

  <style>
    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: repeating-linear-gradient(
        45deg,
        rgba(255, 255, 255, 0.2) 0,
        rgba(255, 255, 255, 0.2) 1px,
        transparent 2px,
        transparent 4px
      );
      pointer-events: none;
      z-index: 0;
    }

    .card-container {
      perspective: 1000px;
      position: relative;
    }

    .card {
      width: 100%;
      height: 100%;
      transform-style: preserve-3d;
      transition: transform 1.2s cubic-bezier(0.68, -0.55, 0.265, 1.55);
      position: relative;
      z-index: 1;
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
      border: 3px solid rgba(255, 255, 255, 0.25);
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
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
    .message-scroll-area::-webkit-scrollbar-thumb {
      background-color: rgba(255, 182, 193, 0.5);
      border-radius: 10px;
    }
  </style>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700;900&display=swap" rel="stylesheet">
</head>

<body class="bg-gradient-to-br from-birthday-pink via-birthday-blue to-birthday-purple min-h-screen flex items-center justify-center font-sans p-4">

  <main class="w-full max-w-2xl text-center relative z-10">
    <h1 class="text-4xl sm:text-5xl font-extrabold mb-8 text-white drop-shadow-lg tracking-tight">
        🎂 Happy Birthday <span class="text-birthday-gold"></span>
    </h1>

    <div id="surprise-container" class="card-container w-full h-[550px] sm:h-[600px]">
      <div class="card">

        <!-- FRONT CARD -->
        <div class="card-face bg-gradient-to-br from-birthday-blue to-birthday-pink">
          <div class="space-y-8 p-4">
            <svg class="mx-auto w-32 h-32 text-birthday-gold" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v8m4-4H8" />
            </svg>

            <p class="text-white text-xl font-semibold">
              Click below to reveal the <span class="text-birthday-gold">Birthday Surprise</span> and message for your instructor!
            </p>

            <a href="#surprise-container" class="reveal-button inline-block px-8 py-3 bg-birthday-gold text-white font-bold rounded-full shadow-lg hover:scale-105 transition">
              🎁 View Birthday Message
            </a>
          </div>
        </div>

        <!-- BACK CARD -->
        <div class="card-face card-back bg-gradient-to-tl from-birthday-gold via-birthday-pink to-birthday-purple text-white overflow-hidden">
          <div class="flex flex-col items-center justify-start h-full p-4 sm:p-6 text-center space-y-4">

            <img src="https://scontent-mnl3-2.xx.fbcdn.net/v/t39.30808-6/508146696_122239603070091148_3901578049460948195_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=a5f93a&_nc_eui2=AeFaVt3liNrEeTQnsyqFcQU29XXitk5hBxz1deK2TmEHHE1ZibcZZbzj6d_U-NHdQ9LT_aJ7p_y6hcU6dI8gHsO6&_nc_ohc=3Jnugt5tjnwQ7kNvwHqvy_8&_nc_oc=AdlOlhTJHfb-sTIlYt3qzfvKzZm86_EyHgwtAteeHoQAhlA4Hw1iekmu1TwxjEPO1JE&_nc_zt=23&_nc_ht=scontent-mnl3-2.xx&_nc_gid=ryTDwnIp0GA-4_5y0K9JQw&oh=00_AffAsUUIjUHEODRfWcoFKzi8ueWtMoh9YEgJJiq79QhAtA&oe=68F50038"
              alt="Instructor" class="w-32 h-32 sm:w-40 sm:h-40 rounded-full border-4 border-white shadow-xl mb-4">

            <h2 class="text-4xl sm:text-5xl font-black leading-tight drop-shadow-lg">🎉 Happy Birthday Sir Gio! 🎉</h2>

            <div class="message-scroll-area bg-white/80 text-birthday-purple rounded-xl p-4 shadow-inner flex-grow overflow-y-auto max-w-md leading-relaxed">
              <p>Dear Sir Gio Albert Montano,</p>
              <p class="mt-3">We wish you the happiest birthday! 🎂 Thank you for your patience, dedication, and the inspiration you bring to every lesson.</p>
              <p class="mt-3">Your Data Structures lessons aren’t just about algorithms — they’re about logic, persistence, and heart. You make every concept come alive, and we appreciate you greatly.</p>
              <p class="mt-3 italic">May your day be filled with joy, laughter, and perfectly optimized code that runs in O(1) time!</p>
              <p class="mt-3">With warmest wishes,</p>
              <p class="italic">Your Grateful Students 💻</p>
            </div>

            <a href="#" class="reset-link inline-block text-birthday-purple bg-white px-6 py-2 font-bold rounded-full shadow-md hover:bg-birthday-gold hover:text-white transition duration-300 mt-4">
              🎈 Close Card
            </a>
          </div>
        </div>
      </div>
    </div>

    <p class="mt-8 text-gray-100 text-sm">From: <span class="font-bold">BSCS 2B</span> | Status: Celebrating 🎉</p>
  </main>
</body>
</html>
