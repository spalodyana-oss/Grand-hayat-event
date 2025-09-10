<!-- Chosen Palette: Serene Sand -->
<!-- Application Structure Plan: The SPA is designed with a user-centric, interactive timeline. The primary interaction is a toggle to switch between Day 1 and Day 2, preventing a long scroll and allowing users to focus. A secondary, nested interaction allows users to toggle between the two mid-day session options ("Fitness" vs. "Spa"). This structure was chosen because it mirrors the key decisions a user needs to make (which day to attend, which session to choose) and presents the dense schedule in a digestible, explorable format. Key highlights and gifts are summarized in a separate section for quick reference. -->
<!-- Visualization & Content Choices: Report Info: 2-Day Schedule -> Goal: Organize/Compare -> Viz/Method: Interactive HTML/CSS Vertical Timeline -> Interaction: JS-powered buttons to toggle visibility of Day 1/Day 2 content and nested toggles for Session Options A/B. Justification: A timeline is the most intuitive way to present a schedule. The interactivity makes it dynamic and prevents overwhelming the user. | Report Info: Key details (capacity, gifts) -> Goal: Inform/Entice -> Viz/Method: Styled HTML cards with Unicode icons. Justification: Creates visually distinct, scannable summaries of important value propositions. | No charts are needed as the data is purely textual and structural. -->
<!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wellness & Beauty Retreat | Interactive Schedule</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #FDFBF8;
            color: #4A4A4A;
        }
        .active-day {
            background-color: #C5A880 !important;
            color: #FFFFFF !important;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
        }
        .active-option {
            background-color: #EAE2D9 !important;
            color: #8C6A42 !important;
            border-color: #C5A880 !important;
        }
        .timeline-item {
            position: relative;
            padding-bottom: 2.5rem;
            padding-left: 2.5rem; 
        }
        .timeline-item:last-child {
            padding-bottom: 0;
        }
        .timeline-item::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0.25rem;
            height: 100%;
            width: 2px;
            background-color: #EAE2D9;
        }
        .timeline-item:last-child::before {
            height: 0;
        }
        .timeline-marker {
            position: absolute;
            left: -0.5rem;
            top: 0.25rem;
            width: 1.25rem;
            height: 1.25rem;
            border-radius: 9999px;
            background-color: #FDFBF8;
            border: 3px solid #C5A880;
            z-index: 10;
        }
    </style>
</head>
<body class="antialiased">

    <div class="container mx-auto px-4 py-8 md:py-12">

        <!-- Header -->
        <header class="text-center mb-10 md:mb-16">
            <h1 class="text-3xl md:text-5xl font-bold text-[#8C6A42] mb-2">Two-Day Wellness & Beauty Retreat</h1>
            <p class="text-lg md:text-xl text-gray-500">Grand Hyatt x LODYana Spa x Fitness First</p>
        </header>

        <!-- Introduction Section -->
        <section class="max-w-4xl mx-auto text-center mb-12">
             <h2 class="text-2xl font-bold text-gray-700 mb-4">An Exclusive Journey to Inner & Outer Radiance</h2>
            <p class="text-gray-600 leading-relaxed mb-6">
                Welcome to an immersive two-day experience designed to harmonize your mind, body, and spirit. Held at the luxurious Grand Hyatt Abu Dhabi, this retreat is an exclusive collaboration bringing you the best in wellness, fitness, and beauty. Explore the schedule below to discover your path to transformation. Each day is limited to 50 guests to ensure an intimate and personalized journey.
            </p>
        </section>


        <!-- Interactive Schedule Section -->
        <section class="max-w-5xl mx-auto">
            <!-- Day Selector -->
            <div class="flex justify-center items-center mb-10 space-x-2 md:space-x-4 bg-gray-100 p-2 rounded-full shadow-inner">
                <button id="day1-btn" class="w-full md:w-auto text-sm md:text-base font-semibold py-3 px-6 rounded-full transition-all duration-300 ease-in-out active-day">Day 1: Sept 20th</button>
                <button id="day2-btn" class="w-full md:w-auto text-sm md:text-base font-semibold text-gray-600 py-3 px-6 rounded-full transition-all duration-300 ease-in-out">Day 2: Sept 21st</button>
            </div>

            <!-- Schedule Content -->
            <div id="schedule-content">
                <!-- Day 1 Schedule -->
                <div id="day1-content">
                    <h3 class="text-center text-2xl font-bold text-[#8C6A42] mb-8">Schedule for Day 1: Fitness & Spiritual Harmony</h3>
                    <div class="max-w-3xl mx-auto">
                        <!-- Timeline -->
                        <div>
                            <!-- Morning Flow -->
                            <div class="timeline-item">
                                <div class="timeline-marker"></div>
                                <p class="font-bold text-sm text-[#C5A880]">7:00 AM - 9:30 AM</p>
                                <h4 class="font-semibold text-lg text-gray-800 mt-1">Morning Flow: Activate & Elevate</h4>
                                <ul class="list-disc list-inside text-gray-600 mt-2 space-y-1">
                                    <li><span class="font-semibold">7:00 AM:</span> Beginner's yoga session in the serene garden.</li>
                                    <li><span class="font-semibold">8:30 AM:</span> Welcome drinks, registration, and tour of the Spa & Gym facilities on Level P3.</li>
                                </ul>
                            </div>
                            
                            <!-- Mid-Day Session -->
                            <div class="timeline-item">
                                <div class="timeline-marker"></div>
                                <p class="font-bold text-sm text-[#C5A880]">10:00 AM - 2:00 PM</p>
                                <h4 class="font-semibold text-lg text-gray-800 mt-1">Mid-Day Session: Choice & Transformation</h4>
                                <p class="text-gray-600 mt-2 mb-4">Select an option below to view the detailed schedule for your chosen experience.</p>
                                <!-- Option Selector -->
                                <div class="flex space-x-2 rounded-lg bg-gray-50 p-1 mb-4">
                                    <button id="day1-option-a-btn" class="w-full text-center p-3 rounded-md text-sm font-medium border-2 border-transparent transition-all duration-300 active-option">🏃‍♀️ Fitness & Rejuvenation</button>
                                    <button id="day1-option-b-btn" class="w-full text-center p-3 rounded-md text-sm font-medium border-2 border-transparent text-gray-500 transition-all duration-300">💆‍♀️ Spa & Education</button>
                                </div>
                                <!-- Option A Content -->
                                <div id="day1-option-a-content" class="bg-white p-4 rounded-lg border border-gray-200">
                                    <ul class="space-y-2 text-gray-700">
                                        <li><span class="font-semibold">10:00 AM:</span> Fitness First Class (Choose Zumba or Pilates) in the Mouza Meeting Room (P1).</li>
                                        <li><span class="font-semibold">11:00 AM:</span> Healthy snacks & Body Analysis at the Luma terrace (P3).</li>
                                        <li><span class="font-semibold">12:00 PM:</span> Meditation presentation & a transformative Sound Healing spiritual session.</li>
                                    </ul>
                                </div>
                                <!-- Option B Content -->
                                <div id="day1-option-b-content" class="bg-white p-4 rounded-lg border border-gray-200 hidden">
                                    <ul class="space-y-2 text-gray-700">
                                        <li><span class="font-semibold">10:00 AM:</span> Meditation presentation & a deeply restorative Sound Healing spiritual session.</li>
                                        <li><span class="font-semibold">12:00 PM:</span> Exclusive spa lines and home care educational session with Hidropeptide.</li>
                                    </ul>
                                </div>
                            </div>
                            
                            <!-- Afternoon -->
                            <div class="timeline-item">
                                <div class="timeline-marker"></div>
                                <p class="font-bold text-sm text-[#C5A880]">AFTER 2:00 PM</p>
                                <h4 class="font-semibold text-lg text-gray-800 mt-1">Afternoon: Relaxation & Reward</h4>
                                <p class="text-gray-600 mt-2">Guests are invited to stay and enjoy the Grand Hyatt's luxurious facilities, including the sauna, hammam, steam room, and swimming pool until the evening.</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Day 2 Schedule -->
                <div id="day2-content" class="hidden">
                    <h3 class="text-center text-2xl font-bold text-[#8C6A42] mb-8">Schedule for Day 2: Mindfulness & Inner Peace</h3>
                    <div class="max-w-3xl mx-auto">
                        <!-- Timeline -->
                        <div>
                            <!-- Morning Flow -->
                            <div class="timeline-item">
                                <div class="timeline-marker"></div>
                                <p class="font-bold text-sm text-[#C5A880]">7:00 AM - 9:30 AM</p>
                                <h4 class="font-semibold text-lg text-gray-800 mt-1">Morning Flow: Activate & Elevate</h4>
                                <ul class="list-disc list-inside text-gray-600 mt-2 space-y-1">
                                    <li><span class="font-semibold">7:00 AM:</span> Beginner's yoga session in the serene garden.</li>
                                    <li><span class="font-semibold">8:30 AM:</span> Welcome drinks, registration, and tour of the Spa & Gym facilities on Level P3.</li>
                                </ul>
                            </div>
                            
                             <!-- Mid-Day Session -->
                            <div class="timeline-item">
                                <div class="timeline-marker"></div>
                                <p class="font-bold text-sm text-[#C5A880]">10:00 AM - 2:00 PM</p>
                                <h4 class="font-semibold text-lg text-gray-800 mt-1">Mid-Day Session: Choice & Transformation</h4>
                                <p class="text-gray-600 mt-2 mb-4">Select an option below to view the detailed schedule for your chosen experience.</p>
                                <!-- Option Selector -->
                                <div class="flex space-x-2 rounded-lg bg-gray-50 p-1 mb-4">
                                    <button id="day2-option-a-btn" class="w-full text-center p-3 rounded-md text-sm font-medium border-2 border-transparent transition-all duration-300 active-option">🏃‍♀️ Fitness & Rejuvenation</button>
                                    <button id="day2-option-b-btn" class="w-full text-center p-3 rounded-md text-sm font-medium border-2 border-transparent text-gray-500 transition-all duration-300">💆‍♀️ Spa & Education</button>
                                </div>
                                <!-- Option A Content -->
                                <div id="day2-option-a-content" class="bg-white p-4 rounded-lg border border-gray-200">
                                    <ul class="space-y-2 text-gray-700">
                                        <li><span class="font-semibold">10:00 AM:</span> Fitness First Class (Choose Zumba or Pilates) in the Mouza Meeting Room (P1).</li>
                                        <li><span class="font-semibold">11:00 AM:</span> Healthy snacks & Body Analysis at the Luma terrace (P3).</li>
                                        <li><span class="font-semibold">12:00 PM:</span> Meditation presentation & a deeply restorative Breathing meditation session.</li>
                                    </ul>
                                </div>
                                <!-- Option B Content -->
                                <div id="day2-option-b-content" class="bg-white p-4 rounded-lg border border-gray-200 hidden">
                                    <ul class="space-y-2 text-gray-700">
                                        <li><span class="font-semibold">10:00 AM:</span> Meditation presentation & a deeply restorative Breathing meditation session.</li>
                                        <li><span class="font-semibold">12:00 PM:</span> Exclusive spa lines and home care educational session with Hidropeptide.</li>
                                    </ul>
                                </div>
                            </div>
                            
                            <!-- Afternoon -->
                            <div class="timeline-item">
                                <div class="timeline-marker"></div>
                                <p class="font-bold text-sm text-[#C5A880]">AFTER 2:00 PM</p>
                                <h4 class="font-semibold text-lg text-gray-800 mt-1">Afternoon: Relaxation & Reward</h4>
                                <p class="text-gray-600 mt-2">Guests are invited to stay and enjoy the Grand Hyatt's luxurious facilities, including the sauna, hammam, steam room, and swimming pool until the evening.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Gifts & Highlights Section -->
        <section class="mt-16 md:mt-24">
            <div class="max-w-4xl mx-auto text-center">
                <h2 class="text-2xl font-bold text-gray-700 mb-4">Exclusive Gifts for Every Guest</h2>
                <p class="text-gray-600 leading-relaxed mb-8">
                    As a token of our appreciation, every participant will receive a curated package of gifts to continue their wellness journey.
                </p>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 text-left">
                    <div class="bg-white rounded-xl p-6 shadow-lg hover:shadow-xl transition-shadow duration-300">
                        <span class="text-4xl">🏋️</span>
                        <h4 class="font-bold text-lg text-gray-800 mt-3 mb-2">Fitness First Day Pass</h4>
                        <p class="text-gray-600">Enjoy a complimentary one-day gym pass to experience Fitness First's state-of-the-art facilities.</p>
                    </div>
                    <div class="bg-white rounded-xl p-6 shadow-lg hover:shadow-xl transition-shadow duration-300">
                        <span class="text-4xl">✨</span>
                        <h4 class="font-bold text-lg text-gray-800 mt-3 mb-2">LODYana Spa Certificate</h4>
                        <p class="text-gray-600">A deposit certificate to be used towards a future luxurious spa treatment of your choice.</p>
                    </div>
                     <div class="bg-white rounded-xl p-6 shadow-lg hover:shadow-xl transition-shadow duration-300">
                        <span class="text-4xl">🍽️</span>
                        <h4 class="font-bold text-lg text-gray-800 mt-3 mb-2">Poolside Lunch Voucher</h4>
                        <p class="text-gray-600">A complimentary F&B certificate to enjoy a delicious lunch by the Grand Hyatt pool on the day of the event.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
         <footer class="text-center mt-16 md:mt-24 pt-8 border-t border-gray-200">
            <h3 class="text-xl font-semibold text-gray-800">Ready to Transform?</h3>
            <p class="text-gray-600 mt-2 mb-6">Spaces are limited. Register now to secure your place at this exclusive wellness retreat.</p>
            <a href="#" class="bg-[#8C6A42] text-white font-bold py-3 px-8 rounded-full hover:bg-[#7a5c3a] transition-colors duration-300 shadow-lg">
                Register Now
            </a>
            <p class="text-sm text-gray-400 mt-8">&copy; 2025 LODYana Spa. All Rights Reserved.</p>
        </footer>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const day1Btn = document.getElementById('day1-btn');
            const day2Btn = document.getElementById('day2-btn');
            const day1Content = document.getElementById('day1-content');
            const day2Content = document.getElementById('day2-content');

            day1Btn.addEventListener('click', () => {
                day1Content.classList.remove('hidden');
                day2Content.classList.add('hidden');
                day1Btn.classList.add('active-day');
                day2Btn.classList.remove('active-day');
            });

            day2Btn.addEventListener('click', () => {
                day2Content.classList.remove('hidden');
                day1Content.classList.add('hidden');
                day2Btn.classList.add('active-day');
                day1Btn.classList.remove('active-day');
            });

            function setupOptionToggle(dayPrefix) {
                const optionABtn = document.getElementById(`${dayPrefix}-option-a-btn`);
                const optionBBtn = document.getElementById(`${dayPrefix}-option-b-btn`);
                const optionAContent = document.getElementById(`${dayPrefix}-option-a-content`);
                const optionBContent = document.getElementById(`${dayPrefix}-option-b-content`);
                
                if(optionABtn && optionBBtn && optionAContent && optionBContent){
                    optionABtn.addEventListener('click', () => {
                        optionAContent.classList.remove('hidden');
                        optionBContent.classList.add('hidden');
                        optionABtn.classList.add('active-option');
                        optionBBtn.classList.remove('active-option');
                    });

                    optionBBtn.addEventListener('click', () => {
                        optionBContent.classList.remove('hidden');
                        optionAContent.classList.add('hidden');
                        optionBBtn.classList.add('active-option');
                        optionABtn.classList.remove('active-option');
                    });
                }
            }

            setupOptionToggle('day1');
            setupOptionToggle('day2');
        });
    </script>

</body>
</html>
