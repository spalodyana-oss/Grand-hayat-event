<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>World Wellness Weekend | Grand Hyatt Abu Dhabi</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Chosen Palette: Serene Earth -->
    <!-- Application Structure Plan: The application is designed as a single-page, top-down narrative to guide the user from initial interest to registration. It starts with a hero section containing the event's value proposition and a primary call-to-action (CTA). The core of the app is an interactive schedule viewer, allowing users to toggle between Day 1 and Day 2. This prevents overwhelming the user with a long list and allows them to focus on the day they are interested in. A visually engaging vertical timeline replaces the static bullet points from the source document for better scannability. Following the schedule, key highlights and benefits are presented in a card layout to reinforce the event's value. The page concludes with information about the global initiative and a final CTA. This structure was chosen to create a seamless and persuasive user journey, making the schedule easy to explore and encouraging registration. -->
    <!-- Visualization & Content Choices: The primary content is a schedule. Goal: Organize & Inform. Presentation: A custom-styled vertical timeline built with HTML and Tailwind CSS. Interaction: Buttons to toggle visibility between Day 1 and Day 2 schedules via vanilla JavaScript. Justification: A static list is less engaging. An interactive timeline is a more intuitive and visually appealing way to present chronological events, improving user experience and clarity. No quantitative data was present, so no charts were necessary. Icons (Unicode) are used to add visual cues to different event types. This approach avoids external libraries for a fast, lightweight experience. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .active-day-btn {
            background-color: #86A397 !important;
            color: #FFFFFF !important;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
        }
        .timeline-item::before {
            content: '';
            position: absolute;
            left: -31px;
            top: 10px;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background-color: #F0EBE3;
            border: 4px solid #86A397;
        }
        .timeline-container {
            border-left: 2px solid #86A397;
        }
    </style>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
</head>
<body class="bg-[#F5F3EF] text-[#3D405B]">

    <div class="container mx-auto px-4 sm:px-6 lg:px-8">

        <header class="text-center py-12 md:py-20">
            <h1 class="text-4xl md:text-6xl font-bold text-[#4A5C55] tracking-tight">World Wellness Weekend</h1>
            <p class="mt-4 max-w-3xl mx-auto text-lg md:text-xl text-[#5C6181]">
                Grand Hyatt Abu Dhabi, in collaboration with LODYana Spa and Fitness First, invites you to a transformative two-day experience designed to energize your body and uplift your mind. Embrace movement, mindfulness, and meaningful connection.
            </p>
            <a href="https://forms.gle/p5HxeKsb3Edm2sbv9" target="_blank" class="mt-8 inline-block bg-[#86A397] text-white font-bold py-3 px-8 rounded-full text-lg hover:bg-[#708f81] transition-colors duration-300 shadow-lg">
                Register Here
            </a>
        </header>

        <main class="bg-white/70 rounded-3xl shadow-lg p-6 md:p-10 mb-16 backdrop-blur-sm">
            <div class="text-center mb-8">
                <h2 class="text-3xl font-bold text-[#4A5C55]">Event Schedule</h2>
                <p class="text-md text-[#5C6181] mt-2">Select a day to view the detailed schedule of activities.</p>
                <div class="mt-6 inline-flex rounded-full bg-[#F0EBE3] p-1 space-x-1">
                    <button id="day1-btn" class="day-btn active-day-btn w-32 px-4 py-2 rounded-full font-semibold transition-colors duration-300">Day 1 <span class="hidden sm:inline-block">| Sep 20</span></button>
                    <button id="day2-btn" class="day-btn w-32 px-4 py-2 rounded-full font-semibold transition-colors duration-300">Day 2 <span class="hidden sm:inline-block">| Sep 21</span></button>
                </div>
            </div>

            <div id="day1-schedule" class="schedule-content">
                <p class="text-center text-lg text-[#5C6181] mb-8 italic max-w-2xl mx-auto">From a serene yoga session facing the palaces to an energetic Zumba class and mindful meditation, embark on a transformative day of wellness.</p>
                <div class="timeline-container relative pl-10 sm:pl-12 md:pl-16">
                    <div class="space-y-8">
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">7:00 – 7:30 AM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Guest Arrival & Registration</h3>
                            <p class="text-md text-[#5C6181]">📍 P3 Level</p>
                        </div>
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">7:30 - 8:30 AM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Palace View Yoga</h3>
                            <p class="text-md text-[#5C6181]">📍 P3 Level</p>
                        </div>
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">8:30 - 9:30 AM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Body Analysis & Wellness Break</h3>
                            <p class="text-md text-[#5C6181]">with Healthy Refreshments</p>
                            <p class="text-md text-[#5C6181]">📍 P3 Level</p>
                        </div>
                         <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">10:00 AM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Sound Healing Spiritual Meditation</h3>
                            <p class="text-md text-[#5C6181]">📍 P1 Level</p>
                        </div>
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">12:00 - 1:00 PM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Discover Gemology’s Diamond Facial</h3>
                            <p class="text-md text-[#5C6181]">by Lum’a Spa</p>
                            <p class="text-md text-[#5C6181]">📍 P3 Level</p>
                        </div>
                         <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">1:00 - 2:00 PM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Wellness Break</h3>
                            <p class="text-md text-[#5C6181]">with Healthy Refreshments & Snacks</p>
                            <p class="text-md text-[#5C6181]">📍 P3 Level</p>
                        </div>
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">2:00 - 3:00 PM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Zumba Class</h3>
                            <p class="text-md text-[#5C6181]">by Fitness First</p>
                            <p class="text-md text-[#5C6181]">📍 P1 Level</p>
                        </div>
                    </div>
                </div>
            </div>

            <div id="day2-schedule" class="schedule-content" style="display: none;">
                <p class="text-center text-lg text-[#5C6181] mb-8 italic max-w-2xl mx-auto">From an uplifting Pilates class to an insightful session about the art of breathing, continue your transformative day of wellness.</p>
                 <div class="timeline-container relative pl-10 sm:pl-12 md:pl-16">
                    <div class="space-y-8">
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">7:00 – 7:30 AM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Guest Arrival & Registration</h3>
                            <p class="text-md text-[#5C6181]">📍 P3 Level</p>
                        </div>
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">7:30 - 8:30 AM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Palace View Yoga</h3>
                            <p class="text-md text-[#5C6181]">📍 P3 Level</p>
                        </div>
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">8:30 - 9:30 AM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Wellness Break</h3>
                            <p class="text-md text-[#5C6181]">with Healthy Refreshments</p>
                            <p class="text-md text-[#5C6181]">📍 P3 Level</p>
                        </div>
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">10:00 - 11:00 AM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Pilates Session</h3>
                             <p class="text-md text-[#5C6181]">by Fitness First</p>
                            <p class="text-md text-[#5C6181]">📍 P1 Level</p>
                        </div>
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">11:00 - 11:30 AM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Body Analysis & Wellness Break</h3>
                             <p class="text-md text-[#5C6181]">with Healthy Refreshments</p>
                            <p class="text-md text-[#5C6181]">📍 P3 Level</p>
                        </div>
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">11:30 - 1:00 PM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Healing Breathing Meditation Session</h3>
                            <p class="text-md text-[#5C6181]">📍 P1 Level</p>
                        </div>
                        <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">1:00 - 2:00 PM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Wellness Break</h3>
                            <p class="text-md text-[#5C6181]">with Healthy Refreshments & Snacks</p>
                            <p class="text-md text-[#5C6181]">📍 P3 Level</p>
                        </div>
                         <div class="timeline-item relative">
                            <p class="text-sm font-semibold text-[#86A397]">2:00 - 4:00 PM</p>
                            <h3 class="text-xl font-bold text-[#4A5C55] mt-1">Uncover LODYana Spa’s Slimming Secrets</h3>
                            <p class="text-md text-[#5C6181]">📍 Lum’a Spa</p>
                        </div>
                    </div>
                </div>
            </div>
        </main>

        <section class="mb-16">
            <div class="grid md:grid-cols-2 gap-8 text-center">
                <div class="bg-white/70 rounded-3xl p-8 shadow-lg">
                    <h3 class="text-2xl font-bold text-[#4A5C55]">Complimentary Access</h3>
                    <p class="mt-2 text-[#5C6181]">All classes are complimentary. By attending, you also get to enjoy access to Grand Hyatt Abu Dhabi’s sauna and pool facilities (subject to availability).</p>
                </div>
                <div class="bg-white/70 rounded-3xl p-8 shadow-lg">
                    <h3 class="text-2xl font-bold text-[#4A5C55]">A Global Celebration</h3>
                    <p class="mt-2 text-[#5C6181]">Join over 10,000 venues worldwide in celebrating wellness and inspiring a lasting commitment to a healthy lifestyle in a vibrant, nurturing setting.</p>
                </div>
            </div>
        </section>

        <footer class="text-center py-10 border-t-2 border-[#EAE6DD] mb-16">
            <p class="max-w-4xl mx-auto text-[#5C6181]">World Wellness Weekend is an International Non-Profit Association, launched in 2017 to support the United Nations’ objective of “Good Health and Wellbeing for All” and the Global Wellness Institute’s Wellness Moonshot, a world free of preventable diseases.</p>
             <div class="mt-8 flex flex-col items-center">
                <h3 class="text-xl font-bold text-[#4A5C55] mb-4">Our Partners</h3>
                <div class="flex flex-wrap justify-center items-center gap-8">
                    <a href="https://www.lodyanaspa.ae/" target="_blank" title="LODYana Healing and Wellness Center" class="flex flex-col items-center group">
                        <img src="https://lodyana.spa.com/Lodyana%20logo.jpg" alt="LODYana Spa" class="w-16 h-16 transition-transform duration-300 group-hover:scale-110 shadow-md">
                        <p class="mt-2 text-sm text-[#5C6181] font-semibold">LODYana Spa</p>
                    </a>
                    <a href="https://www.hyatt.com/grand-hyatt/en-US/auhgh-grand-hyatt-abu-dhabi-hotel-and-residences-emirates-pearl?gclsrc=aw.ds&&src=bbm_sem_bbm_search_google_eame_rooms_brand_catchall_UAE_Abu%20Dhabi_Grand%20Hyatt_AUHGH_Grand%20Hyatt%20Abu%20Dhabi%20Hotel%20%26%20Residences%20Emirates%20Pearl_grand%20hyatt%20abu%20dhabi&mckv=s-dc_pcrid_773459610702_mtid_5297kx13790&gad_source=1&gad_campaignid=22010265295&gbraid=0AAAAAookwJjGiSTGtAZs-tkRbM43lj093&gclid=CjwKCAjwiY_GBhBEEiwAFaghvvPqJjHh0i_AGZRFcF8gj3F24X8EKCLGEn8xDfA65NTKUe55gI5tSBoCAKsQAvD_BwE" target="_blank" title="Grand Hyatt Abu Dhabi" class="flex flex-col items-center group">
                        <img src="https://grandhyattabudhabi.com/GHAUH%20Logo%20_En%20(Transparent).png" alt="Grand Hyatt" class="w-16 h-16 transition-transform duration-300 group-hover:scale-110 shadow-md">
                        <p class="mt-2 text-sm text-[#5C6181] font-semibold">Grand Hyatt</p>
                    </a>
                    <a href="https://uae.fitnessfirstme.com/" target="_blank" title="Fitness First" class="flex flex-col items-center group">
                        <img src="https://fitnessfirst.com/fitness-first-1612073155290.jpg" alt="Fitness First" class="w-16 h-16 transition-transform duration-300 group-hover:scale-110 shadow-md">
                        <p class="mt-2 text-sm text-[#5C6181] font-semibold">Fitness First</p>
                    </a>
                </div>
            </div>
             <a href="https://forms.gle/p5HxeKsb3Edm2sbv9" target="_blank" class="mt-8 inline-block bg-[#86A397] text-white font-bold py-3 px-8 rounded-full text-lg hover:bg-[#708f81] transition-colors duration-300 shadow-lg">
                Secure Your Spot
            </a>
            <div class="mt-16 bg-white/70 rounded-3xl shadow-lg p-6 md:p-10 text-center">
                <h3 class="text-2xl font-bold text-[#4A5C55] mb-4">Event Location</h3>
                <a href="https://maps.app.goo.gl/Gq6yF46j9EzCVjCo6" target="_blank" class="flex flex-col items-center hover:text-[#86A397] transition-colors duration-300">
                    <span class="text-4xl text-gray-700">📍</span>
                    <p class="mt-2 text-lg font-semibold underline">Grand Hyatt Abu Dhabi Hotel & Residences Emirates Pearl</p>
                    <p class="text-sm text-[#5C6181]">West Corniche, Abu Dhabi, United Arab Emirates</p>
                </a>
            </div>
        </footer>

    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const day1Btn = document.getElementById('day1-btn');
            const day2Btn = document.getElementById('day2-btn');
            const day1Schedule = document.getElementById('day1-schedule');
            const day2Schedule = document.getElementById('day2-schedule');
            const allDayBtns = document.querySelectorAll('.day-btn');

            function showSchedule(day) {
                day1Schedule.style.display = 'none';
                day2Schedule.style.display = 'none';
                allDayBtns.forEach(btn => btn.classList.remove('active-day-btn'));

                if (day === 1) {
                    day1Schedule.style.display = 'block';
                    day1Btn.classList.add('active-day-btn');
                } else if (day === 2) {
                    day2Schedule.style.display = 'block';
                    day2Btn.classList.add('active-day-btn');
                }
            }
            
            day1Btn.addEventListener('click', () => showSchedule(1));
            day2Btn.addEventListener('click', () => showSchedule(2));

            showSchedule(1);
        });
    </script>
</body>
</html>
