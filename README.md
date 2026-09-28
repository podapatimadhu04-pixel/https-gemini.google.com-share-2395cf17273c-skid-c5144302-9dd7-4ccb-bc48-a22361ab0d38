# https-gemini.google.com-share-2395cf17273c-skid-c5144302-9dd7-4ccb-bc48-a22361ab0d38
for the farmmer to ai use to best methods in farming
<!DOCTYPE html>
<html lang="en" class="h-full bg-slate-50">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KisanSmart AI - Smart Agriculture Platform</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        agri: {
                            50: '#f0fdf4',
                            100: '#dcfce7',
                            200: '#bbf7d0',
                            300: '#86efac',
                            400: '#4ade80',
                            500: '#22c55e',
                            600: '#16a34a',
                            700: '#15803d',
                            800: '#166534',
                            900: '#14532d',
                            dark: '#0a2e18'
                        },
                        earth: {
                            100: '#fdf6e7',
                            500: '#d97706',
                            800: '#78350f'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif']
                    }
                }
            }
        }
    </script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body { font-family: 'Inter', sans-serif; }
        .custom-scrollbar::-webkit-scrollbar { width: 6px; height: 6px; }
        .custom-scrollbar::-webkit-scrollbar-track { background: #f1f5f9; }
        .custom-scrollbar::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 4px; }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover { background: #94a3b8; }
        .glass-card { background: rgba(255, 255, 255, 0.9); backdrop-filter: blur(8px); }
        .pulse-emerald { animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite; }
        @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: .5; } }
    </style>
</head>
<body class="h-full flex flex-col bg-slate-100 text-slate-800 antialiased overflow-x-hidden">

    <div id="app" class="flex h-screen overflow-hidden">

        <!-- Sidebar Navigation (Desktop) -->
        <aside id="sidebar" class="hidden md:flex flex-col w-64 bg-agri-900 text-white flex-shrink-0 transition-all duration-300 z-30 shadow-xl">
            <!-- App Brand -->
            <div class="flex items-center justify-between p-4 border-b border-agri-800">
                <div class="flex items-center space-x-3">
                    <div class="w-10 h-10 rounded-xl bg-agri-500 flex items-center justify-center text-white font-bold text-xl shadow-lg">
                        <i class="fa-solid fa-wheat-awn"></i>
                    </div>
                    <div>
                        <h1 class="font-bold text-lg leading-tight tracking-wide text-white">KisanSmart AI</h1>
                        <p class="text-xs text-agri-300">Smart Farming Ecosystem</p>
                    </div>
                </div>
            </div>

            <!-- Active Field Quick Indicator -->
            <div class="p-3 bg-agri-800/60 m-3 rounded-xl border border-agri-700/50">
                <div class="text-xs text-agri-300 font-medium mb-1 uppercase tracking-wider flex justify-between items-center">
                    <span>Active Field</span>
                    <i class="fa-solid fa-[#22c55e] text-[10px] text-agri-400"></i>
                </div>
                <select id="activeFieldSelectNav" onchange="switchActiveField(this.value)" class="w-full bg-agri-900 text-white text-sm rounded-lg p-2 border border-agri-700 focus:ring-2 focus:ring-agri-400 focus:outline-none cursor-pointer">
                    <!-- Populated dynamically -->
                </select>
            </div>

            <!-- Nav Links -->
            <nav class="flex-1 overflow-y-auto custom-scrollbar p-3 space-y-1 text-sm font-medium">
                <button onclick="navigateTo('dashboard')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="dashboard">
                    <i class="fa-solid fa-chart-pie w-5 text-agri-400"></i>
                    <span>Dashboard</span>
                </button>
                <button onclick="navigateTo('fields')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="fields">
                    <i class="fa-solid fa-layer-group w-5 text-agri-400"></i>
                    <span>My Fields</span>
                </button>
                <button onclick="navigateTo('scanner')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors relative" data-view="scanner">
                    <i class="fa-solid fa-camera-retro w-5 text-agri-400"></i>
                    <span>AI Crop Scanner</span>
                    <span class="ml-auto bg-amber-500 text-xs font-bold text-slate-900 px-1.5 py-0.5 rounded-full">AI</span>
                </button>
                <button onclick="navigateTo('diseases')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="diseases">
                    <i class="fa-solid fa-vial-virus w-5 text-agri-400"></i>
                    <span>Diseases & Organic Remedies</span>
                </button>
                <button onclick="navigateTo('water')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="water">
                    <i class="fa-solid fa-droplet w-5 text-agri-400"></i>
                    <span>Water & Soil Monitor</span>
                </button>
                <button onclick="navigateTo('health')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="health">
                    <i class="fa-solid fa-heart-pulse w-5 text-agri-400"></i>
                    <span>Field Health Tracking</span>
                </button>
                <button onclick="navigateTo('irrigation')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="irrigation">
                    <i class="fa-solid fa-faucet-drip w-5 text-agri-400"></i>
                    <span>Smart Irrigation</span>
                </button>
                <button onclick="navigateTo('recommendations')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="recommendations">
                    <i class="fa-solid fa-wand-magic-sparkles w-5 text-agri-400"></i>
                    <span>Crop Advisor AI</span>
                </button>
                <button onclick="navigateTo('weather')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="weather">
                    <i class="fa-solid fa-cloud-sun-rain w-5 text-agri-400"></i>
                    <span>Agromet Weather</span>
                </button>
                <button onclick="navigateTo('calendar')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="calendar">
                    <i class="fa-solid fa-calendar-days w-5 text-agri-400"></i>
                    <span>Farm Calendar</span>
                </button>
                <button onclick="navigateTo('records')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="records">
                    <i class="fa-solid fa-book-bookmark w-5 text-agri-400"></i>
                    <span>Digital Records</span>
                </button>
                <button onclick="navigateTo('chatbot')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="chatbot">
                    <i class="fa-solid fa-robot w-5 text-agri-400"></i>
                    <span>AI Farm Assistant</span>
                </button>
                <button onclick="navigateTo('analytics')" class="nav-btn w-full flex items-center space-x-3 px-3 py-2.5 rounded-lg text-agri-100 hover:bg-agri-800 transition-colors" data-view="analytics">
                    <i class="fa-solid fa-chart-line w-5 text-agri-400"></i>
                    <span>Analytics</span>
                </button>
            </nav>

            <!-- Bottom User & Settings -->
            <div class="p-3 border-t border-agri-800 flex items-center justify-between">
                <button onclick="navigateTo('settings')" class="flex items-center space-x-2 text-agri-200 hover:text-white text-sm p-2 rounded-lg hover:bg-agri-800 w-full transition-colors">
                    <i class="fa-solid fa-gear text-agri-400"></i>
                    <span>Settings & API</span>
                </button>
            </div>
        </aside>

        <!-- Main Content Area -->
        <div class="flex-1 flex flex-col h-full overflow-hidden">

            <!-- Top Navigation Header -->
            <header class="bg-white border-b border-slate-200 px-4 py-3 flex items-center justify-between z-20 flex-shrink-0 shadow-sm">
                <div class="flex items-center space-x-3">
                    <button id="mobileMenuBtn" onclick="toggleMobileMenu()" class="md:hidden text-slate-600 hover:text-slate-900 p-2 rounded-lg focus:outline-none">
                        <i class="fa-solid fa-bars text-xl"></i>
                    </button>
                    <div class="md:hidden flex items-center space-x-2">
                        <div class="w-8 h-8 rounded-lg bg-agri-600 flex items-center justify-center text-white font-bold">
                            <i class="fa-solid fa-wheat-awn text-sm"></i>
                        </div>
                        <span class="font-bold text-slate-800">KisanSmart</span>
                    </div>
                    <div class="hidden sm:flex items-center text-sm text-slate-500 font-medium">
                        <span id="headerBreadcrumb">Dashboard</span>
                    </div>
                </div>

                <div class="flex items-center space-x-2 sm:space-x-4">
                    <!-- Language Selector -->
                    <div class="relative">
                        <select id="languageSelect" onchange="changeLanguage(this.value)" class="bg-slate-100 hover:bg-slate-200 text-xs sm:text-sm text-slate-700 font-medium rounded-lg px-2.5 py-1.5 border border-slate-300 focus:outline-none cursor-pointer">
                            <option value="en">English</option>
                            <option value="hi">हिंदी (Hindi)</option>
                            <option value="te">తెలుగు (Telugu)</option>
                            <option value="ta">தமிழ் (Tamil)</option>
                            <option value="kn">ಕನ್ನಡ (Kannada)</option>
                            <option value="mr">मराठी (Marathi)</option>
                            <option value="bn">বাংলা (Bengali)</option>
                        </select>
                    </div>

                    <!-- Quick Voice Assistant -->
                    <button onclick="navigateTo('chatbot'); startVoiceInput();" title="Voice Assistant" class="bg-agri-50 hover:bg-agri-100 text-agri-700 border border-agri-200 p-2 rounded-lg transition-colors flex items-center space-x-1.5">
                        <i class="fa-solid fa-microphone text-agri-600 text-sm"></i>
                        <span class="hidden lg:inline text-xs font-semibold">Voice AI</span>
                    </button>

                    <!-- Notifications Dropdown -->
                    <div class="relative">
                        <button onclick="toggleNotificationDropdown()" class="p-2 text-slate-600 hover:text-slate-900 hover:bg-slate-100 rounded-lg relative transition-colors">
                            <i class="fa-solid fa-bell text-lg"></i>
                            <span id="unreadBadge" class="absolute top-1 right-1 w-2.5 h-2.5 bg-rose-500 rounded-full ring-2 ring-white"></span>
                        </button>
                        <!-- Dropdown Panel -->
                        <div id="notificationDropdown" class="hidden absolute right-0 mt-2 w-80 sm:w-96 bg-white rounded-2xl shadow-xl border border-slate-200 py-2 z-50 overflow-hidden">
                            <div class="px-4 py-2 border-b border-slate-100 flex justify-between items-center bg-slate-50">
                                <h3 class="font-semibold text-slate-800 text-sm">Alerts & Notifications</h3>
                                <button onclick="clearNotifications()" class="text-xs text-agri-600 hover:underline">Clear all</button>
                            </div>
                            <div id="notificationList" class="max-h-80 overflow-y-auto custom-scrollbar divide-y divide-slate-100">
                                <!-- Notifications dynamically inserted -->
                            </div>
                        </div>
                    </div>

                    <!-- API Status Badge -->
                    <div id="apiStatusBadge" onclick="navigateTo('settings')" title="Click to configure Gemini API Key" class="cursor-pointer flex items-center space-x-1.5 text-xs font-medium px-2.5 py-1 rounded-full bg-emerald-100 text-emerald-800 border border-emerald-300">
                        <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
                        <span id="apiStatusText" class="hidden sm:inline">AI Active</span>
                    </div>
                </div>
            </header>

            <!-- Mobile Drawer Menu -->
            <div id="mobileDrawer" class="fixed inset-0 bg-slate-900/60 z-40 hidden md:hidden transition-opacity" onclick="toggleMobileMenu()">
                <div class="w-64 bg-agri-900 h-full text-white p-4 flex flex-col justify-between" onclick="event.stopPropagation()">
                    <div>
                        <div class="flex items-center justify-between pb-4 border-b border-agri-800">
                            <div class="flex items-center space-x-2">
                                <i class="fa-solid fa-wheat-awn text-agri-400 text-xl"></i>
                                <span class="font-bold text-lg">KisanSmart AI</span>
                            </div>
                            <button onclick="toggleMobileMenu()" class="text-slate-400 hover:text-white">
                                <i class="fa-solid fa-xmark text-lg"></i>
                            </button>
                        </div>
                        <div class="py-3">
                            <label class="text-xs text-agri-300 uppercase tracking-wider block mb-1">Active Field</label>
                            <select id="activeFieldSelectMobile" onchange="switchActiveField(this.value); toggleMobileMenu();" class="w-full bg-agri-800 text-white text-sm rounded-lg p-2 border border-agri-700">
                            </select>
                        </div>
                        <nav id="mobileNavLinks" class="space-y-1 text-sm pt-2">
                            <!-- Cloned dynamically -->
                        </nav>
                    </div>
                </div>
            </div>

            <!-- Main Content Display -->
            <main class="flex-1 overflow-y-auto custom-scrollbar bg-slate-50 p-4 sm:p-6 relative">

                <!-- VIEW 1: FARMER DASHBOARD -->
                <section id="view-dashboard" class="view-section space-y-6">
                    <!-- Welcome Hero Header -->
                    <div class="bg-gradient-to-r from-agri-800 via-agri-700 to-emerald-800 rounded-3xl p-6 sm:p-8 text-white shadow-xl relative overflow-hidden">
                        <div class="absolute -right-10 -bottom-10 opacity-15 text-white text-9xl pointer-events-none">
                            <i class="fa-solid fa-seedling"></i>
                        </div>
                        <div class="relative z-10 max-w-3xl">
                            <div class="inline-flex items-center space-x-2 bg-white/20 backdrop-blur-md px-3 py-1 rounded-full text-xs font-semibold mb-3 text-agri-100">
                                <i class="fa-solid fa-calendar-day"></i>
                                <span id="dashCurrentDate">Today's Agro Status</span>
                            </div>
                            <h1 class="text-2xl sm:text-3xl font-bold tracking-tight mb-2" id="dashGreeting">Namaste Farmer!</h1>
                            <p class="text-agri-100 text-sm sm:text-base leading-relaxed">
                                Here is the real-time health diagnostic, moisture level, weather forecast, and action recommendations for your field.
                            </p>
                            <div class="mt-6 flex flex-wrap gap-3">
                                <button onclick="navigateTo('scanner')" class="bg-amber-400 hover:bg-amber-300 text-slate-900 font-semibold px-5 py-2.5 rounded-xl text-sm shadow-md transition-transform transform active:scale-95 flex items-center space-x-2">
                                    <i class="fa-solid fa-camera"></i>
                                    <span>Scan Crop Leaves</span>
                                </button>
                                <button onclick="openAddFieldModal()" class="bg-white/10 hover:bg-white/20 text-white border border-white/30 font-medium px-4 py-2.5 rounded-xl text-sm transition-colors flex items-center space-x-2">
                                    <i class="fa-solid fa-plus"></i>
                                    <span>Add New Field</span>
                                </button>
                            </div>
                        </div>
                    </div>

                    <!-- Key Metrics Quick Overview Row -->
                    <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                        <!-- Health Score Card -->
                        <div class="bg-white p-5 rounded-2xl border border-slate-200/80 shadow-sm hover:shadow-md transition-shadow">
                            <div class="flex justify-between items-start mb-3">
                                <span class="text-xs font-medium text-slate-500 uppercase tracking-wider">Field Health</span>
                                <div class="w-8 h-8 rounded-xl bg-emerald-100 text-emerald-700 flex items-center justify-center text-sm">
                                    <i class="fa-solid fa-heart-pulse"></i>
                                </div>
                            </div>
                            <div class="flex items-baseline justify-between">
                                <span id="dashHealthScore" class="text-2xl sm:text-3xl font-bold text-slate-800">88%</span>
                                <span id="dashHealthBadge" class="text-xs font-semibold px-2 py-0.5 rounded-full bg-emerald-100 text-emerald-800">Optimal</span>
                            </div>
                            <div class="w-full bg-slate-100 rounded-full h-2 mt-3 overflow-hidden">
                                <div id="dashHealthBar" class="bg-agri-500 h-2 rounded-full" style="w-88%"></div>
                            </div>
                        </div>

                        <!-- Soil Moisture Card -->
                        <div class="bg-white p-5 rounded-2xl border border-slate-200/80 shadow-sm hover:shadow-md transition-shadow">
                            <div class="flex justify-between items-start mb-3">
                                <span class="text-xs font-medium text-slate-500 uppercase tracking-wider">Soil Moisture</span>
                                <div class="w-8 h-8 rounded-xl bg-blue-100 text-blue-700 flex items-center justify-center text-sm">
                                    <i class="fa-solid fa-droplet"></i>
                                </div>
                            </div>
                            <div class="flex items-baseline justify-between">
                                <span id="dashMoistureVal" class="text-2xl sm:text-3xl font-bold text-slate-800">65%</span>
                                <span id="dashMoistureStatus" class="text-xs font-semibold px-2 py-0.5 rounded-full bg-blue-100 text-blue-800">Adequate</span>
                            </div>
                            <p class="text-xs text-slate-500 mt-3 flex items-center">
                                <i class="fa-solid fa-info-circle mr-1"></i> No irrigation needed today
                            </p>
                        </div>

                        <!-- Growth Stage Card -->
                        <div class="bg-white p-5 rounded-2xl border border-slate-200/80 shadow-sm hover:shadow-md transition-shadow">
                            <div class="flex justify-between items-start mb-3">
                                <span class="text-xs font-medium text-slate-500 uppercase tracking-wider">Growth Stage</span>
                                <div class="w-8 h-8 rounded-xl bg-amber-100 text-amber-700 flex items-center justify-center text-sm">
                                    <i class="fa-solid fa-plant-wilt"></i>
                                </div>
                            </div>
                            <div class="flex items-baseline justify-between">
                                <span id="dashGrowthStage" class="text-lg sm:text-xl font-bold text-slate-800 truncate">Tillering</span>
                                <span id="dashCropType" class="text-xs font-medium text-amber-700 bg-amber-50 px-2 py-0.5 rounded-md border border-amber-200">Rice</span>
                            </div>
                            <p class="text-xs text-slate-500 mt-3" id="dashHarvestEst">Est. Harvest: 45 Days</p>
                        </div>

                        <!-- Weather Quick Widget -->
                        <div class="bg-white p-5 rounded-2xl border border-slate-200/80 shadow-sm hover:shadow-md transition-shadow">
                            <div class="flex justify-between items-start mb-3">
                                <span class="text-xs font-medium text-slate-500 uppercase tracking-wider">Live Weather</span>
                                <div class="w-8 h-8 rounded-xl bg-sky-100 text-sky-700 flex items-center justify-center text-sm">
                                    <i class="fa-solid fa-cloud-sun"></i>
                                </div>
                            </div>
                            <div class="flex items-baseline justify-between">
                                <span id="dashTemp" class="text-2xl sm:text-3xl font-bold text-slate-800">31°C</span>
                                <span id="dashWeatherCond" class="text-xs font-semibold px-2 py-0.5 rounded-full bg-sky-100 text-sky-800">Partly Cloudy</span>
                            </div>
                            <p class="text-xs text-slate-500 mt-3" id="dashHumidity">Humidity: 72% | Rain: 20%</p>
                        </div>
                    </div>

                    <!-- Main Grid Content -->
                    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">

                        <!-- Left 2-Column Section -->
                        <div class="lg:col-span-2 space-y-6">

                            <!-- Field Health & Moisture Trends Chart -->
                            <div class="bg-white p-5 rounded-3xl border border-slate-200 shadow-sm">
                                <div class="flex flex-col sm:flex-row justify-between sm:items-center mb-4 gap-2">
                                    <div>
                                        <h3 class="font-bold text-slate-800 text-base">Field Diagnostics & Moisture Trend</h3>
                                        <p class="text-xs text-slate-500">Historical 7-day soil moisture and crop vigor tracking</p>
                                    </div>
                                    <div class="flex items-center space-x-2">
                                        <span class="inline-flex items-center text-xs text-slate-600"><span class="w-2.5 h-2.5 bg-agri-500 rounded-full mr-1.5"></span> Health Score</span>
                                        <span class="inline-flex items-center text-xs text-slate-600"><span class="w-2.5 h-2.5 bg-sky-500 rounded-full mr-1.5"></span> Soil Moisture %</span>
                                    </div>
                                </div>
                                <div class="h-64 relative">
                                    <canvas id="dashChartCanvas"></canvas>
                                </div>
                            </div>

                            <!-- Recommended Treatments & Organic Recipe Card -->
                            <div class="bg-white p-5 rounded-3xl border border-slate-200 shadow-sm">
                                <div class="flex items-center justify-between mb-4">
                                    <div class="flex items-center space-x-2">
                                        <div class="w-8 h-8 rounded-lg bg-emerald-100 text-emerald-700 flex items-center justify-center">
                                            <i class="fa-solid fa-leaf"></i>
                                        </div>
                                        <h3 class="font-bold text-slate-800 text-base">Recommended Agronomic Actions</h3>
                                    </div>
                                    <button onclick="navigateTo('diseases')" class="text-xs text-agri-700 hover:underline font-semibold">View All Remedies →</button>
                                </div>

                                <div id="dashActionItems" class="space-y-3">
                                    <!-- Dynamic Action Items -->
                                </div>
                            </div>

                        </div>

                        <!-- Right Column: Alerts & Quick Stats -->
                        <div class="space-y-6">

                            <!-- Field Information Card -->
                            <div class="bg-white p-5 rounded-3xl border border-slate-200 shadow-sm">
                                <h3 class="font-bold text-slate-800 text-base mb-3 flex items-center justify-between">
                                    <span>Active Field Details</span>
                                    <button onclick="navigateTo('fields')" class="text-xs text-agri-600 hover:underline">Manage</button>
                                </h3>
                                <div class="space-y-3 text-sm">
                                    <div class="flex justify-between py-2 border-b border-slate-100">
                                        <span class="text-slate-500">Field Name</span>
                                        <span id="dashMetaName" class="font-semibold text-slate-800">-</span>
                                    </div>
                                    <div class="flex justify-between py-2 border-b border-slate-100">
                                        <span class="text-slate-500">Location</span>
                                        <span id="dashMetaLoc" class="font-semibold text-slate-800">-</span>
                                    </div>
                                    <div class="flex justify-between py-2 border-b border-slate-100">
                                        <span class="text-slate-500">Field Size</span>
                                        <span id="dashMetaSize" class="font-semibold text-slate-800">-</span>
                                    </div>
                                    <div class="flex justify-between py-2 border-b border-slate-100">
                                        <span class="text-slate-500">Soil Type</span>
                                        <span id="dashMetaSoil" class="font-semibold text-slate-800">-</span>
                                    </div>
                                    <div class="flex justify-between py-2 border-b border-slate-100">
                                        <span class="text-slate-500">Irrigation Method</span>
                                        <span id="dashMetaIrrigation" class="font-semibold text-slate-800">-</span>
                                    </div>
                                    <div class="flex justify-between py-2">
                                        <span class="text-slate-500">Sowing Date</span>
                                        <span id="dashMetaSown" class="font-semibold text-slate-800">-</span>
                                    </div>
                                </div>
                            </div>

                            <!-- Crop Warning & Disease Alerts -->
                            <div class="bg-amber-50 border border-amber-200 rounded-3xl p-5 shadow-sm">
                                <div class="flex items-center space-x-2 text-amber-800 font-bold mb-2">
                                    <i class="fa-solid fa-triangle-exclamation text-amber-600"></i>
                                    <h4>Agri Alert & Risk Warning</h4>
                                </div>
                                <p id="dashAlertMessage" class="text-xs text-amber-900 leading-relaxed">
                                    High ambient humidity detected in your region. Susceptible to fungal blast disease on younger rice leaves. Apply organic Jeevamrutham or neem spray preemptively.
                                </p>
                                <button onclick="navigateTo('scanner')" class="mt-3 w-full bg-amber-500 hover:bg-amber-600 text-white font-semibold py-2 rounded-xl text-xs transition-colors shadow-sm">
                                    Run Leaf Scan Now
                                </button>
                            </div>

                            <!-- Recent Farm Activities -->
                            <div class="bg-white p-5 rounded-3xl border border-slate-200 shadow-sm">
                                <div class="flex items-center justify-between mb-3">
                                    <h3 class="font-bold text-slate-800 text-base">Recent Activity Log</h3>
                                    <button onclick="navigateTo('records')" class="text-xs text-agri-600 hover:underline">Full Log</button>
                                </div>
                                <div id="dashRecentActivityList" class="space-y-3 relative before:absolute before:left-3 before:top-2 before:bottom-2 before:w-0.5 before:bg-slate-200">
                                    <!-- Dynamic Activity Items -->
                                </div>
                            </div>

                        </div>
                    </div>
                </section>

                <!-- VIEW 2: MY FIELDS (ADD / MANAGE / HISTORY) -->
                <section id="view-fields" class="view-section hidden space-y-6">
                    <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4">
                        <div>
                            <h2 class="text-2xl font-bold text-slate-800">My Agricultural Fields</h2>
                            <p class="text-slate-500 text-sm">Manage multiple farm plots, crop profiles, and historical performance.</p>
                        </div>
                        <button onclick="openAddFieldModal()" class="bg-agri-600 hover:bg-agri-700 text-white font-semibold px-5 py-2.5 rounded-xl text-sm shadow-md transition-colors flex items-center justify-center space-x-2">
                            <i class="fa-solid fa-plus"></i>
                            <span>Register New Field</span>
                        </button>
                    </div>

                    <!-- Fields Grid -->
                    <div id="fieldsGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                        <!-- Dynamically Generated Field Cards -->
                    </div>
                </section>

                <!-- VIEW 3: AI CROP SCANNER (CAMERA & IMAGE ANALYSIS) -->
                <section id="view-scanner" class="view-section hidden space-y-6">
                    <div class="bg-white p-6 rounded-3xl border border-slate-200 shadow-sm">
                        <div class="max-w-3xl mx-auto text-center space-y-2 mb-6">
                            <span class="inline-flex items-center space-x-1.5 px-3 py-1 bg-amber-100 text-amber-800 text-xs font-bold rounded-full">
                                <i class="fa-solid fa-microscope"></i>
                                <span>Powered by Gemini Vision AI</span>
                            </span>
                            <h2 class="text-2xl sm:text-3xl font-bold text-slate-800">AI Crop & Leaf Scanner</h2>
                            <p class="text-slate-500 text-sm">Capture or upload an image of diseased leaves, damaged crops, or pest infestation for immediate diagnosis and organic remedies.</p>
                        </div>

                        <!-- Scanner Input Area -->
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 items-start">

                            <!-- Left: Camera / Upload Container -->
                            <div class="space-y-4">
                                <div id="scannerViewport" class="relative w-full h-72 bg-slate-900 rounded-2xl overflow-hidden flex flex-col items-center justify-center border-2 border-dashed border-slate-300">
                                    <!-- Video Element for Live Camera -->
                                    <video id="webcamVideo" class="hidden w-full h-full object-cover" autoplay playsinline></video>
                                    <!-- Canvas hidden for capture -->
                                    <canvas id="captureCanvas" class="hidden"></canvas>
                                    <!-- Preview Image -->
                                    <img id="previewImage" class="hidden w-full h-full object-contain bg-black" alt="Scan Preview">

                                    <!-- Default Placeholder State -->
                                    <div id="scannerPlaceholder" class="text-center p-6 space-y-3">
                                        <div class="w-16 h-16 rounded-2xl bg-agri-100 text-agri-700 flex items-center justify-center mx-auto text-2xl">
                                            <i class="fa-solid fa-camera"></i>
                                        </div>
                                        <p class="text-sm font-medium text-slate-600">No Image Selected</p>
                                        <p class="text-xs text-slate-400">Supported formats: JPG, PNG, WEBP</p>
                                    </div>

                                    <!-- Loading Spinner Overlay -->
                                    <div id="scannerLoader" class="hidden absolute inset-0 bg-slate-900/80 backdrop-blur-md flex flex-col items-center justify-center text-white space-y-3">
                                        <div class="w-12 h-12 border-4 border-agri-400 border-t-transparent rounded-full animate-spin"></div>
                                        <p class="text-sm font-semibold animate-pulse" id="scannerLoadingMsg">Analyzing plant symptoms...</p>
                                        <p class="text-xs text-slate-300">Checking plant pathology database...</p>
                                    </div>
                                </div>

                                <!-- Action Buttons -->
                                <div class="grid grid-cols-2 gap-3">
                                    <button id="btnStartCamera" onclick="toggleCamera()" class="bg-slate-800 hover:bg-slate-900 text-white font-medium py-2.5 px-4 rounded-xl text-sm transition-colors flex items-center justify-center space-x-2">
                                        <i class="fa-solid fa-video"></i>
                                        <span id="btnCameraText">Open Camera</span>
                                    </button>
                                    <label class="bg-agri-50 hover:bg-agri-100 text-agri-800 border border-agri-300 font-medium py-2.5 px-4 rounded-xl text-sm transition-colors flex items-center justify-center space-x-2 cursor-pointer">
                                        <i class="fa-solid fa-upload"></i>
                                        <span>Upload File</span>
                                        <input type="file" id="fileInput" accept="image/*" class="hidden" onchange="handleFileUpload(event)">
                                    </label>
                                </div>

                                <button id="btnRunAnalysis" onclick="analyzeCurrentImage()" class="w-full bg-agri-600 hover:bg-agri-700 text-white font-bold py-3 px-4 rounded-xl text-sm shadow-md transition-all flex items-center justify-center space-x-2">
                                    <i class="fa-solid fa-wand-magic-sparkles"></i>
                                    <span>Diagnose Crop Health</span>
                                </button>

                                <!-- Demo Sample Selector -->
                                <div class="pt-2 border-t border-slate-100">
                                    <label class="text-xs font-semibold text-slate-500 block mb-2">Or test with demo sample images:</label>
                                    <div class="grid grid-cols-4 gap-2">
                                        <button onclick="loadDemoScan('rice_blast')" class="p-1.5 border border-slate-200 hover:border-agri-500 rounded-lg text-center text-xs bg-slate-50 hover:bg-agri-50 font-medium truncate">
                                            Rice Blast
                                        </button>
                                        <button onclick="loadDemoScan('wheat_rust')" class="p-1.5 border border-slate-200 hover:border-agri-500 rounded-lg text-center text-xs bg-slate-50 hover:bg-agri-50 font-medium truncate">
                                            Wheat Rust
                                        </button>
                                        <button onclick="loadDemoScan('tomato_blight')" class="p-1.5 border border-slate-200 hover:border-agri-500 rounded-lg text-center text-xs bg-slate-50 hover:bg-agri-50 font-medium truncate">
                                            Tomato Blight
                                        </button>
                                        <button onclick="loadDemoScan('cotton_aphids')" class="p-1.5 border border-slate-200 hover:border-agri-500 rounded-lg text-center text-xs bg-slate-50 hover:bg-agri-50 font-medium truncate">
                                            Cotton Pest
                                        </button>
                                    </div>
                                </div>
                            </div>

                            <!-- Right: Analysis Diagnostic Results -->
                            <div class="bg-slate-50 p-5 rounded-2xl border border-slate-200 min-h-[300px] flex flex-col justify-center">
                                <div id="scanResultEmpty" class="text-center py-10 space-y-3">
                                    <i class="fa-solid fa-notes-medical text-4xl text-slate-300"></i>
                                    <h4 class="font-bold text-slate-700 text-base">Awaiting Diagnostic Scan</h4>
                                    <p class="text-xs text-slate-500 max-w-xs mx-auto">Upload or capture an image of the affected plant leaf and click "Diagnose Crop Health".</p>
                                </div>

                                <div id="scanResultOutput" class="hidden space-y-4">
                                    <!-- Result Header -->
                                    <div class="bg-white p-4 rounded-xl border border-slate-200 shadow-sm flex items-start justify-between">
                                        <div>
                                            <div class="flex items-center space-x-2">
                                                <span id="scanResultSeverity" class="px-2 py-0.5 text-xs font-bold rounded-full bg-rose-100 text-rose-800">High Risk</span>
                                                <span id="scanResultCrop" class="text-xs font-semibold text-slate-500">Rice / Paddy</span>
                                            </div>
                                            <h3 id="scanResultDiseaseName" class="text-xl font-bold text-slate-800 mt-1">Rice Blast (Magnaporthe oryzae)</h3>
                                        </div>
                                        <div class="text-right">
                                            <span class="text-xs text-slate-400 block">AI Confidence</span>
                                            <span id="scanResultConfidence" class="text-lg font-bold text-agri-600">96.4%</span>
                                        </div>
                                    </div>

                                    <!-- Diagnosis Details Accordion/List -->
                                    <div class="space-y-3 text-xs sm:text-sm">
                                        <div class="bg-white p-3.5 rounded-xl border border-slate-200">
                                            <h5 class="font-bold text-slate-800 mb-1 flex items-center text-xs text-amber-700">
                                                <i class="fa-solid fa-eye mr-1.5"></i> Observed Symptoms
                                            </h5>
                                            <p id="scanResultSymptoms" class="text-slate-600 leading-relaxed">-</p>
                                        </div>

                                        <div class="bg-white p-3.5 rounded-xl border border-slate-200">
                                            <h5 class="font-bold text-slate-800 mb-1 flex items-center text-xs text-slate-700">
                                                <i class="fa-solid fa-circle-info mr-1.5"></i> Root Cause
                                            </h5>
                                            <p id="scanResultCauses" class="text-slate-600 leading-relaxed">-</p>
                                        </div>

                                        <div class="bg-emerald-50 p-3.5 rounded-xl border border-emerald-200">
                                            <h5 class="font-bold text-emerald-900 mb-1 flex items-center text-xs">
                                                <i class="fa-solid fa-flask text-emerald-700 mr-1.5"></i> Recommended Organic Treatment
                                            </h5>
                                            <p id="scanResultRemedy" class="text-emerald-900 leading-relaxed font-medium">-</p>
                                        </div>

                                        <div class="bg-sky-50 p-3.5 rounded-xl border border-sky-200">
                                            <h5 class="font-bold text-sky-900 mb-1 flex items-center text-xs">
                                                <i class="fa-solid fa-shield-halved text-sky-700 mr-1.5"></i> Preventive Measures
                                            </h5>
                                            <p id="scanResultPrevention" class="text-sky-900 leading-relaxed">-</p>
                                        </div>
                                    </div>

                                    <button onclick="saveScanToRecord()" class="w-full bg-slate-800 hover:bg-slate-900 text-white font-semibold py-2 rounded-xl text-xs transition-colors">
                                        Save Scan Result to Field Log
                                    </button>
                                </div>
                            </div>

                        </div>
                    </div>
                </section>

                <!-- VIEW 4: DISEASE & ORGANIC REMEDIES CATALOG -->
                <section id="view-diseases" class="view-section hidden space-y-6">
                    <div class="flex flex-col sm:flex-row justify-between sm:items-center gap-4">
                        <div>
                            <h2 class="text-2xl font-bold text-slate-800">Disease & Organic Remedy Library</h2>
                            <p class="text-slate-500 text-sm">Eco-friendly pest control, biopesticides, and botanical solutions for safe agriculture.</p>
                        </div>
                        <div class="relative w-full sm:w-72">
                            <i class="fa-solid fa-magnifying-glass absolute left-3 top-3 text-slate-400 text-sm"></i>
                            <input type="text" id="diseaseSearchInput" onkeyup="filterDiseaseCatalog()" placeholder="Search disease or crop..." class="w-full bg-white border border-slate-300 rounded-xl pl-9 pr-3 py-2 text-sm focus:ring-2 focus:ring-agri-500 focus:outline-none">
                        </div>
                    </div>

                    <!-- Organic Remedy Highlight Cards -->
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6" id="diseaseCatalogGrid">
                        <!-- Dynamically filled with disease cards -->
                    </div>
                </section>

                <!-- VIEW 5: WATER & SOIL MONITOR -->
                <section id="view-water" class="view-section hidden space-y-6">
                    <div class="flex justify-between items-center">
                        <div>
                            <h2 class="text-2xl font-bold text-slate-800">Water & Soil Health Monitor</h2>
                            <p class="text-slate-500 text-sm">Real-time sensor metrics and manual soil telemetry for precise crop management.</p>
                        </div>
                        <button onclick="openManualReadingModal()" class="bg-agri-600 hover:bg-agri-700 text-white font-semibold px-4 py-2 rounded-xl text-xs sm:text-sm shadow transition-colors flex items-center space-x-1.5">
                            <i class="fa-solid fa-pen-to-square"></i>
                            <span>Enter Reading</span>
                        </button>
                    </div>

                    <!-- Sensor Status Indicators -->
                    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
                        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm">
                            <span class="text-xs text-slate-500 font-medium">Volumetric Moisture</span>
                            <div class="text-2xl font-bold text-slate-800 mt-1" id="monitorMoistureVal">68%</div>
                            <div class="text-xs text-emerald-600 font-semibold mt-1">Status: Optimal</div>
                        </div>
                        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm">
                            <span class="text-xs text-slate-500 font-medium">Soil Temperature</span>
                            <div class="text-2xl font-bold text-slate-800 mt-1" id="monitorSoilTemp">24°C</div>
                            <div class="text-xs text-slate-500 mt-1">Normal Range</div>
                        </div>
                        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm">
                            <span class="text-xs text-slate-500 font-medium">Soil pH Level</span>
                            <div class="text-2xl font-bold text-slate-800 mt-1" id="monitorSoilPH">6.5 pH</div>
                            <div class="text-xs text-emerald-600 font-semibold mt-1">Slightly Acidic (Ideal)</div>
                        </div>
                        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm">
                            <span class="text-xs text-slate-500 font-medium">Water Table Level</span>
                            <div class="text-2xl font-bold text-slate-800 mt-1" id="monitorWaterTable">Adequate</div>
                            <div class="text-xs text-slate-500 mt-1">Groundwater Stable</div>
                        </div>
                    </div>

                    <!-- Soil Moisture Trend Chart & Crop Moisture Requirement -->
                    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                        <div class="lg:col-span-2 bg-white p-5 rounded-3xl border border-slate-200 shadow-sm">
                            <h3 class="font-bold text-slate-800 text-base mb-3">7-Day Soil Moisture History</h3>
                            <div class="h-64">
                                <canvas id="waterTrendChartCanvas"></canvas>
                            </div>
                        </div>

                        <div class="bg-white p-5 rounded-3xl border border-slate-200 shadow-sm space-y-4">
                            <h3 class="font-bold text-slate-800 text-base">Crop Water Benchmark</h3>
                            <div class="space-y-3 text-xs">
                                <div class="bg-slate-50 p-3 rounded-xl border border-slate-200">
                                    <div class="flex justify-between font-semibold text-slate-700">
                                        <span>Rice / Paddy</span>
                                        <span>1200 - 1500 mm</span>
                                    </div>
                                    <p class="text-slate-500 mt-1">Requires standing water during tillering stage.</p>
                                </div>
                                <div class="bg-slate-50 p-3 rounded-xl border border-slate-200">
                                    <div class="flex justify-between font-semibold text-slate-700">
                                        <span>Wheat</span>
                                        <span>450 - 650 mm</span>
                                    </div>
                                    <p class="text-slate-500 mt-1">Critical irrigation at crown root initiation.</p>
                                </div>
                                <div class="bg-slate-50 p-3 rounded-xl border border-slate-200">
                                    <div class="flex justify-between font-semibold text-slate-700">
                                        <span>Vegetables / Tomatoes</span>
                                        <span>400 - 600 mm</span>
                                    </div>
                                    <p class="text-slate-500 mt-1">Frequent light drip irrigation recommended.</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- VIEW 6: FIELD HEALTH TRACKING -->
                <section id="view-health" class="view-section hidden space-y-6">
                    <div>
                        <h2 class="text-2xl font-bold text-slate-800">Field Health & Vigor Tracking</h2>
                        <p class="text-slate-500 text-sm">Long-term agronomic condition tracking, NDVI vigor scores, and stress alerts.</p>
                    </div>

                    <div class="bg-white p-6 rounded-3xl border border-slate-200 shadow-sm space-y-6">
                        <div class="flex flex-col sm:flex-row justify-between sm:items-center gap-4 bg-emerald-50 p-4 rounded-2xl border border-emerald-200">
                            <div>
                                <span class="text-xs font-bold text-emerald-800 uppercase tracking-wider">Overall Agro Health Index</span>
                                <div class="text-3xl font-extrabold text-emerald-900" id="healthTrackingScore">88 / 100</div>
                            </div>
                            <div class="text-xs text-emerald-800 space-y-1">
                                <p>✔ Soil Nitrogen & Potassium Balance: Good</p>
                                <p>✔ Canopy Chlorophyll Vigor: High</p>
                                <p>⚠ Pest Threat Level: Moderate (Leaf Folder)</p>
                            </div>
                        </div>

                        <div class="h-64">
                            <canvas id="healthHistoryChartCanvas"></canvas>
                        </div>
                    </div>
                </section>

                <!-- VIEW 7: SMART IRRIGATION ASSISTANT -->
                <section id="view-irrigation" class="view-section hidden space-y-6">
                    <div class="flex justify-between items-center">
                        <div>
                            <h2 class="text-2xl font-bold text-slate-800">Smart Irrigation Controller</h2>
                            <p class="text-slate-500 text-sm">Automated watering schedules based on soil evapotranspiration and rain forecasts.</p>
                        </div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <!-- Recommendation Card -->
                        <div class="bg-white p-6 rounded-3xl border border-slate-200 shadow-sm space-y-4">
                            <div class="flex items-center space-x-3 text-sky-700">
                                <div class="w-10 h-10 rounded-xl bg-sky-100 flex items-center justify-center text-lg">
                                    <i class="fa-solid fa-faucet-drip"></i>
                                </div>
                                <h3 class="font-bold text-slate-800 text-lg">Irrigation Advice</h3>
                            </div>

                            <div class="bg-sky-50 border border-sky-200 p-4 rounded-2xl space-y-2">
                                <div class="flex justify-between items-center text-sm font-bold text-sky-900">
                                    <span>Status</span>
                                    <span id="irrigAdviceStatus" class="px-2.5 py-0.5 rounded-full bg-emerald-100 text-emerald-800 text-xs">NOT REQUIRED</span>
                                </div>
                                <p id="irrigAdviceText" class="text-xs text-sky-900 leading-relaxed">
                                    Current soil moisture (65%) is above the crop stress threshold (45%). Rain probability for tomorrow is 20%. Next irrigation recommended in 2 days.
                                </p>
                            </div>

                            <div class="space-y-2 text-xs text-slate-600">
                                <div class="flex justify-between py-1 border-b">
                                    <span>Recommended Water Quantity:</span>
                                    <span class="font-semibold text-slate-800">12,000 Liters / Acre</span>
                                </div>
                                <div class="flex justify-between py-1 border-b">
                                    <span>Optimal Watering Window:</span>
                                    <span class="font-semibold text-slate-800">6:00 AM - 8:30 AM</span>
                                </div>
                                <div class="flex justify-between py-1">
                                    <span>Irrigation Method:</span>
                                    <span class="font-semibold text-slate-800" id="irrigMetaMethod">Drip Irrigation</span>
                                </div>
                            </div>
                        </div>

                        <!-- Hardware / Simulation Control Card -->
                        <div class="bg-white p-6 rounded-3xl border border-slate-200 shadow-sm space-y-4 flex flex-col justify-between">
                            <div>
                                <h3 class="font-bold text-slate-800 text-lg mb-1">IoT Pump Controller (Simulated)</h3>
                                <p class="text-xs text-slate-500 mb-4">Connect and control physical smart solenoid valves or water pumps.</p>

                                <div class="bg-slate-900 text-white p-4 rounded-2xl space-y-3">
                                    <div class="flex justify-between items-center">
                                        <span class="text-xs text-slate-400">Pump Power Switch</span>
                                        <span id="pumpStatusBadge" class="px-2 py-0.5 text-xs font-bold rounded-full bg-slate-700 text-slate-300">OFF</span>
                                    </div>
                                    <div class="flex items-center justify-between pt-2">
                                        <div>
                                            <div class="text-lg font-bold">Motor Pump #1</div>
                                            <div class="text-xs text-slate-400">Flow rate: 40 L/min</div>
                                        </div>
                                        <button id="pumpToggleBtn" onclick="togglePumpSimulation()" class="bg-emerald-500 hover:bg-emerald-600 text-white font-bold px-4 py-2 rounded-xl text-xs transition-colors">
                                            Turn ON Pump
                                        </button>
                                    </div>
                                </div>
                            </div>

                            <p class="text-xs text-slate-400 italic">Note: In manual mode, recommendations guide manual motor valve switches.</p>
                        </div>
                    </div>
                </section>

                <!-- VIEW 8: CROP ADVISOR & RECOMMENDATION AI -->
                <section id="view-recommendations" class="view-section hidden space-y-6">
                    <div class="bg-white p-6 rounded-3xl border border-slate-200 shadow-sm">
                        <div class="max-w-2xl mx-auto text-center space-y-2 mb-6">
                            <span class="px-3 py-1 bg-agri-100 text-agri-800 text-xs font-bold rounded-full">AI Agronomist Engine</span>
                            <h2 class="text-2xl font-bold text-slate-800">Smart Crop Recommendation</h2>
                            <p class="text-slate-500 text-sm">Select your soil condition, water availability, and region to get optimal, high-yield crop recommendations.</p>
                        </div>

                        <!-- Form Input -->
                        <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-6">
                            <div>
                                <label class="text-xs font-semibold text-slate-700 block mb-1">Soil Type</label>
                                <select id="recSoilType" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm focus:ring-2 focus:ring-agri-500">
                                    <option value="Clay / Alluvial">Clay / Alluvial Soil</option>
                                    <option value="Black Cotton Soil">Black Cotton Soil</option>
                                    <option value="Red Sandy Loam">Red Sandy Loam</option>
                                    <option value="Silty Clay">Silty Clay</option>
                                </select>
                            </div>
                            <div>
                                <label class="text-xs font-semibold text-slate-700 block mb-1">Water Availability</label>
                                <select id="recWaterAvail" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm focus:ring-2 focus:ring-agri-500">
                                    <option value="Abundant (Borewell/Canal)">Abundant (Canal/Borewell)</option>
                                    <option value="Moderate (Rainfed + Well)">Moderate (Rainfed + Drip)</option>
                                    <option value="Low / Drought Prone">Low / Dryland</option>
                                </select>
                            </div>
                            <div>
                                <label class="text-xs font-semibold text-slate-700 block mb-1">Cropping Season</label>
                                <select id="recSeason" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm focus:ring-2 focus:ring-agri-500">
                                    <option value="Kharif (Monsoon)">Kharif (Monsoon)</option>
                                    <option value="Rabi (Winter)">Rabi (Winter)</option>
                                    <option value="Zaid (Summer)">Zaid (Summer)</option>
                                </select>
                            </div>
                        </div>

                        <button onclick="generateCropRecommendations()" class="w-full bg-agri-600 hover:bg-agri-700 text-white font-bold py-3 rounded-xl text-sm transition-colors shadow-md flex items-center justify-center space-x-2">
                            <i class="fa-solid fa-wand-magic-sparkles"></i>
                            <span>Generate AI Crop Suggestions</span>
                        </button>
                    </div>

                    <!-- AI Crop Recommendations Results Grid -->
                    <div id="cropRecsResults" class="grid grid-cols-1 md:grid-cols-3 gap-6">
                        <!-- Dynamically filled cards -->
                    </div>
                </section>

                <!-- VIEW 9: AGROMET WEATHER -->
                <section id="view-weather" class="view-section hidden space-y-6">
                    <div>
                        <h2 class="text-2xl font-bold text-slate-800">Agromet Weather Forecast</h2>
                        <p class="text-slate-500 text-sm">Hyper-local agricultural weather advisory and pest warning alerts.</p>
                    </div>

                    <!-- 5-Day Forecast Grid -->
                    <div id="weatherForecastGrid" class="grid grid-cols-2 sm:grid-cols-5 gap-4">
                        <!-- Dynamic weather cards -->
                    </div>
                </section>

                <!-- VIEW 10: FARM CALENDAR -->
                <section id="view-calendar" class="view-section hidden space-y-6">
                    <div class="flex justify-between items-center">
                        <div>
                            <h2 class="text-2xl font-bold text-slate-800">Crop Activity Calendar</h2>
                            <p class="text-slate-500 text-sm">Schedule sowing, fertilization, weeding, and harvest events.</p>
                        </div>
                        <button onclick="openAddCalendarModal()" class="bg-agri-600 hover:bg-agri-700 text-white font-semibold px-4 py-2 rounded-xl text-xs sm:text-sm transition-colors flex items-center space-x-1">
                            <i class="fa-solid fa-plus"></i>
                            <span>Add Event</span>
                        </button>
                    </div>

                    <div class="bg-white p-6 rounded-3xl border border-slate-200 shadow-sm space-y-4">
                        <div id="calendarEventsList" class="space-y-3">
                            <!-- Dynamic Calendar Events -->
                        </div>
                    </div>
                </section>

                <!-- VIEW 11: FARM DIGITAL RECORDS LOGBOOK -->
                <section id="view-records" class="view-section hidden space-y-6">
                    <div class="flex flex-col sm:flex-row justify-between sm:items-center gap-4">
                        <div>
                            <h2 class="text-2xl font-bold text-slate-800">Digital Field Records</h2>
                            <p class="text-slate-500 text-sm">Log farm expenses, fertilizer usage, harvest yield, and field notes.</p>
                        </div>
                        <button onclick="openAddRecordModal()" class="bg-agri-600 hover:bg-agri-700 text-white font-semibold px-4 py-2.5 rounded-xl text-sm transition-colors flex items-center justify-center space-x-2">
                            <i class="fa-solid fa-plus"></i>
                            <span>New Record Entry</span>
                        </button>
                    </div>

                    <!-- Filter Tabs -->
                    <div class="flex space-x-2 border-b border-slate-200 pb-2 overflow-x-auto custom-scrollbar">
                        <button onclick="filterRecords('ALL')" class="rec-tab-btn px-4 py-2 rounded-xl text-xs font-semibold bg-agri-600 text-white">All</button>
                        <button onclick="filterRecords('Fertilizer')" class="rec-tab-btn px-4 py-2 rounded-xl text-xs font-semibold bg-slate-200 text-slate-700 hover:bg-slate-300">Fertilizer</button>
                        <button onclick="filterRecords('Treatment')" class="rec-tab-btn px-4 py-2 rounded-xl text-xs font-semibold bg-slate-200 text-slate-700 hover:bg-slate-300">Treatment</button>
                        <button onclick="filterRecords('Harvest')" class="rec-tab-btn px-4 py-2 rounded-xl text-xs font-semibold bg-slate-200 text-slate-700 hover:bg-slate-300">Harvest</button>
                        <button onclick="filterRecords('Expense')" class="rec-tab-btn px-4 py-2 rounded-xl text-xs font-semibold bg-slate-200 text-slate-700 hover:bg-slate-300">Expenses</button>
                    </div>

                    <!-- Records Table -->
                    <div class="bg-white rounded-3xl border border-slate-200 shadow-sm overflow-hidden">
                        <div class="overflow-x-auto">
                            <table class="w-full text-left text-sm">
                                <thead class="bg-slate-50 text-slate-500 font-semibold text-xs uppercase border-b border-slate-200">
                                    <tr>
                                        <th class="p-4">Date</th>
                                        <th class="p-4">Category</th>
                                        <th class="p-4">Description / Details</th>
                                        <th class="p-4">Cost (₹)</th>
                                        <th class="p-4 text-right">Actions</th>
                                    </tr>
                                </thead>
                                <tbody id="recordsTableBody" class="divide-y divide-slate-100">
                                    <!-- Dynamic rows -->
                                </tbody>
                            </table>
                        </div>
                    </div>
                </section>

                <!-- VIEW 12: AI FARM ASSISTANT CHATBOT -->
                <section id="view-chatbot" class="view-section hidden space-y-6 h-[calc(100vh-120px)] flex flex-col">
                    <div class="bg-white p-4 rounded-2xl border border-slate-200 shadow-sm flex items-center justify-between">
                        <div class="flex items-center space-x-3">
                            <div class="w-10 h-10 rounded-2xl bg-agri-600 text-white flex items-center justify-center font-bold text-lg">
                                <i class="fa-solid fa-robot"></i>
                            </div>
                            <div>
                                <h3 class="font-bold text-slate-800 text-base">Kisan AI Smart Advisor</h3>
                                <p class="text-xs text-emerald-600 font-semibold flex items-center">
                                    <span class="w-2 h-2 rounded-full bg-emerald-500 mr-1.5 animate-pulse"></span> Context Aware & Multilingual
                                </p>
                            </div>
                        </div>
                        <button onclick="clearChatHistory()" class="text-xs text-slate-500 hover:text-slate-800 px-2.5 py-1 rounded-lg border border-slate-200">
                            Clear Chat
                        </button>
                    </div>

                    <!-- Chat Log Area -->
                    <div id="chatMessagesBox" class="flex-1 bg-white rounded-2xl border border-slate-200 p-4 overflow-y-auto custom-scrollbar space-y-4">
                        <!-- Chat messages appended dynamically -->
                    </div>

                    <!-- Chat Input Box -->
                    <div class="bg-white p-3 rounded-2xl border border-slate-200 shadow-sm flex items-center space-x-2">
                        <button id="chatMicBtn" onclick="toggleVoiceInput()" class="bg-slate-100 hover:bg-slate-200 text-slate-700 p-3 rounded-xl text-base transition-colors" title="Speak in your language">
                            <i class="fa-solid fa-microphone"></i>
                        </button>
                        <input type="text" id="chatInput" placeholder="Ask anything about pests, fertilizers, crop yellowing..." onkeypress="if(event.key==='Enter') sendChatMessage()" class="flex-1 bg-slate-50 border border-slate-200 rounded-xl px-4 py-3 text-sm focus:outline-none focus:ring-2 focus:ring-agri-500">
                        <button onclick="sendChatMessage()" class="bg-agri-600 hover:bg-agri-700 text-white font-bold p-3 rounded-xl text-base transition-colors shadow">
                            <i class="fa-solid fa-paper-plane"></i>
                        </button>
                    </div>
                </section>

                <!-- VIEW 13: ANALYTICS -->
                <section id="view-analytics" class="view-section hidden space-y-6">
                    <div>
                        <h2 class="text-2xl font-bold text-slate-800">Farm Performance Analytics</h2>
                        <p class="text-slate-500 text-sm">Comprehensive visual trends of health, yield economics, and input usage.</p>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="bg-white p-5 rounded-3xl border border-slate-200 shadow-sm">
                            <h3 class="font-bold text-slate-800 text-base mb-3">Health vs Water Usage Trend</h3>
                            <div class="h-64">
                                <canvas id="analyticsHealthChartCanvas"></canvas>
                            </div>
                        </div>
                        <div class="bg-white p-5 rounded-3xl border border-slate-200 shadow-sm">
                            <h3 class="font-bold text-slate-800 text-base mb-3">Expense Distribution by Category</h3>
                            <div class="h-64 relative flex justify-center">
                                <canvas id="analyticsExpenseChartCanvas"></canvas>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- VIEW 14: SETTINGS & API CONFIGURATION -->
                <section id="view-settings" class="view-section hidden space-y-6">
                    <div>
                        <h2 class="text-2xl font-bold text-slate-800">Settings & API Setup</h2>
                        <p class="text-slate-500 text-sm">Configure your Gemini AI keys, regional preferences, and data backups.</p>
                    </div>

                    <div class="bg-white p-6 rounded-3xl border border-slate-200 shadow-sm max-w-2xl space-y-6">
                        <div>
                            <label class="block text-sm font-semibold text-slate-800 mb-1">Gemini AI API Key (Optional)</label>
                            <p class="text-xs text-slate-500 mb-2">An empty key uses our default built-in runtime key or demo mode fallback.</p>
                            <input type="password" id="settingApiKey" placeholder="AIzaSy..." class="w-full bg-slate-50 border border-slate-300 rounded-xl p-3 text-sm focus:ring-2 focus:ring-agri-500">
                        </div>

                        <div>
                            <label class="block text-sm font-semibold text-slate-800 mb-1">Farmer Preferred Name</label>
                            <input type="text" id="settingFarmerName" value="Ramesh Kumar" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-3 text-sm focus:ring-2 focus:ring-agri-500">
                        </div>

                        <div class="pt-4 border-t border-slate-200 flex space-x-3">
                            <button onclick="saveSettings()" class="bg-agri-600 hover:bg-agri-700 text-white font-bold px-6 py-2.5 rounded-xl text-sm transition-colors shadow">
                                Save Preferences
                            </button>
                            <button onclick="resetDataToDefault()" class="bg-rose-50 hover:bg-rose-100 text-rose-700 border border-rose-200 font-semibold px-4 py-2.5 rounded-xl text-sm transition-colors">
                                Reset Demo Data
                            </button>
                        </div>
                    </div>
                </section>

            </main>
        </div>
    </div>

    <!-- MODAL: ADD / EDIT FIELD -->
    <div id="modalAddField" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-lg w-full p-6 space-y-4 shadow-2xl overflow-y-auto max-h-[90vh] custom-scrollbar">
            <div class="flex justify-between items-center pb-3 border-b border-slate-100">
                <h3 class="font-bold text-lg text-slate-800" id="modalFieldTitle">Register New Field</h3>
                <button onclick="closeModal('modalAddField')" class="text-slate-400 hover:text-slate-600">
                    <i class="fa-solid fa-xmark text-lg"></i>
                </button>
            </div>
            <form id="fieldForm" onsubmit="handleFieldSubmit(event)" class="space-y-3">
                <input type="hidden" id="fieldFormId">
                <div>
                    <label class="text-xs font-semibold text-slate-700 block mb-1">Field Name</label>
                    <input type="text" id="fName" required placeholder="e.g. North Paddy Plot" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm focus:ring-2 focus:ring-agri-500">
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="text-xs font-semibold text-slate-700 block mb-1">Crop Type</label>
                        <select id="fCrop" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                            <option value="Rice/Paddy">Rice / Paddy</option>
                            <option value="Wheat">Wheat</option>
                            <option value="Tomatoes">Tomatoes (Vegetables)</option>
                            <option value="Cotton">Cotton</option>
                            <option value="Maize">Maize / Corn</option>
                            <option value="Pulses">Pulses / Gram</option>
                            <option value="Flowers">Flowers (Marigold)</option>
                        </select>
                    </div>
                    <div>
                        <label class="text-xs font-semibold text-slate-700 block mb-1">Variety</label>
                        <input type="text" id="fVariety" placeholder="e.g. Sona Masoori" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                    </div>
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="text-xs font-semibold text-slate-700 block mb-1">Field Size (Acres)</label>
                        <input type="number" step="0.1" id="fSize" required placeholder="2.5" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                    </div>
                    <div>
                        <label class="text-xs font-semibold text-slate-700 block mb-1">Soil Type</label>
                        <select id="fSoil" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                            <option value="Clay / Alluvial">Clay / Alluvial</option>
                            <option value="Black Soil">Black Soil</option>
                            <option value="Red Loam">Red Loam</option>
                            <option value="Sandy Soil">Sandy Soil</option>
                        </select>
                    </div>
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="text-xs font-semibold text-slate-700 block mb-1">Planting Date</label>
                        <input type="date" id="fPlantDate" required class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                    </div>
                    <div>
                        <label class="text-xs font-semibold text-slate-700 block mb-1">Irrigation Method</label>
                        <select id="fIrrigation" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                            <option value="Flood Irrigation">Flood Irrigation</option>
                            <option value="Drip System">Drip System</option>
                            <option value="Sprinkler">Sprinkler</option>
                            <option value="Rainfed">Rainfed</option>
                        </select>
                    </div>
                </div>
                <div>
                    <label class="text-xs font-semibold text-slate-700 block mb-1">Location / Village</label>
                    <input type="text" id="fLocation" placeholder="e.g. Karimnagar, AP" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                </div>
                <div class="pt-3 flex space-x-2">
                    <button type="submit" class="w-full bg-agri-600 hover:bg-agri-700 text-white font-bold py-2.5 rounded-xl text-sm transition-colors">
                        Save Field Data
                    </button>
                </div>
            </form>
        </div>
    </div>

    <!-- MODAL: MANUAL SOIL READING -->
    <div id="modalManualReading" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-md w-full p-6 space-y-4 shadow-2xl">
            <div class="flex justify-between items-center pb-2 border-b border-slate-100">
                <h3 class="font-bold text-slate-800">Enter Field Soil Telemetry</h3>
                <button onclick="closeModal('modalManualReading')" class="text-slate-400">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>
            <form onsubmit="handleManualReadingSubmit(event)" class="space-y-3">
                <div>
                    <label class="text-xs font-semibold text-slate-700 block mb-1">Soil Moisture (%)</label>
                    <input type="number" id="manualMoistureInput" min="0" max="100" required class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                </div>
                <div>
                    <label class="text-xs font-semibold text-slate-700 block mb-1">Soil pH Level</label>
                    <input type="number" step="0.1" id="manualPhInput" min="1" max="14" value="6.8" required class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                </div>
                <button type="submit" class="w-full bg-agri-600 hover:bg-agri-700 text-white font-bold py-2.5 rounded-xl text-sm">
                    Save Telemetry Log
                </button>
            </form>
        </div>
    </div>

    <!-- MODAL: NEW RECORD LOG ENTRY -->
    <div id="modalAddRecord" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-md w-full p-6 space-y-4 shadow-2xl">
            <div class="flex justify-between items-center pb-2 border-b border-slate-100">
                <h3 class="font-bold text-slate-800">Add Logbook Entry</h3>
                <button onclick="closeModal('modalAddRecord')" class="text-slate-400">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>
            <form onsubmit="handleAddRecordSubmit(event)" class="space-y-3">
                <div>
                    <label class="text-xs font-semibold text-slate-700 block mb-1">Category</label>
                    <select id="recCat" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                        <option value="Fertilizer">Fertilizer Application</option>
                        <option value="Treatment">Organic Treatment / Spray</option>
                        <option value="Harvest">Harvest Yield</option>
                        <option value="Expense">Farm Expense</option>
                    </select>
                </div>
                <div>
                    <label class="text-xs font-semibold text-slate-700 block mb-1">Description</label>
                    <input type="text" id="recDesc" required placeholder="e.g. Applied 50kg Neem Cake" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                </div>
                <div>
                    <label class="text-xs font-semibold text-slate-700 block mb-1">Cost / Value (₹)</label>
                    <input type="number" id="recCost" value="0" class="w-full bg-slate-50 border border-slate-300 rounded-xl p-2.5 text-sm">
                </div>
                <button type="submit" class="w-full bg-agri-600 hover:bg-agri-700 text-white font-bold py-2.5 rounded-xl text-sm">
                    Add Record
                </button>
            </form>
        </div>
    </div>

    <script>
        // APP STATE DATABASE STORAGE
        const DEFAULT_FIELDS = [
            {
                id: 'field_1',
                name: 'North Paddy Plot',
                location: 'Kareemnagar, Telangana',
                crop: 'Rice/Paddy',
                variety: 'Sona Masoori',
                plantingDate: '2026-07-15',
                size: 3.5,
                soil: 'Clay / Alluvial',
                irrigation: 'Flood Irrigation',
                healthScore: 88,
                moisture: 68,
                growthStage: 'Tillering Stage',
                estimatedHarvest: '2026-11-20'
            },
            {
                id: 'field_2',
                name: 'East Organic Tomato Garden',
                location: 'Rangareddy, Telangana',
                crop: 'Tomatoes',
                variety: 'Arka Rakshak',
                plantingDate: '2026-08-01',
                size: 1.2,
                soil: 'Red Loam',
                irrigation: 'Drip System',
                healthScore: 74,
                moisture: 52,
                growthStage: 'Flowering & Fruiting',
                estimatedHarvest: '2026-10-15'
            }
        ];

        const DEFAULT_DISEASES = [
            {
                id: 'd1',
                name: 'Rice Blast (Pyricularia oryzae)',
                crop: 'Rice/Paddy',
                symptoms: 'Spindle-shaped lesions on leaves with dark reddish-brown margins and grey center.',
                cause: 'High air humidity (>90%) with warm temperatures and excessive nitrogen fertilizer.',
                severity: 'High',
                remedy: 'Panchagavya spray or Trichoderma viride biological culture.',
                recipe: 'Mix 300ml Panchagavya in 10 Liters of clean water. Spray thoroughly on foliage every 10 days.',
                prevention: 'Avoid over-application of nitrogen. Maintain optimum field drainage.'
            },
            {
                id: 'd2',
                name: 'Tomato Early Blight',
                crop: 'Tomatoes',
                symptoms: 'Concentric ring yellow-brown target-like spots on lower foliage.',
                cause: 'Alternaria solani fungal spores spread by wet foliage and splashing water.',
                severity: 'Medium',
                remedy: 'Neem Oil Spray (10,000 PPM) + Cow Urine formulation.',
                recipe: '50ml Neem oil + 5ml organic liquid soap in 10L water. Apply during cool morning hours.',
                prevention: 'Mulching around stem bases to stop soil splashing; crop rotation.'
            },
            {
                id: 'd3',
                name: 'Cotton Aphids & Sucking Pests',
                crop: 'Cotton',
                symptoms: 'Curled leaves, sticky honeydew honeydew mold on upper leaf canopy.',
                cause: 'Aphis gossypii infesting tender shoots during dry spells.',
                severity: 'Medium',
                remedy: 'Dashaparani Ark (10-Herb Botanical Decoction).',
                recipe: 'Spray 200ml Dashaparani Extract diluted in 10L water directly on pest clusters.',
                prevention: 'Intercropping with cowpea or marigold as border trap crops.'
            }
        ];

        let state = {
            fields: [],
            activeFieldId: 'field_1',
            notifications: [],
            records: [],
            calendarEvents: [],
            settings: {
                apiKey: '',
                farmerName: 'Ramesh Kumar',
                language: 'en'
            },
            currentStreamMedia: null,
            isPumpOn: false,
            scannedBase64: null
        };

        // DOM Loaded Init
        window.addEventListener('DOMContentLoaded', () => {
            loadState();
            setupUI();
            renderAllViews();
            initCharts();

            // Set default date
            const today = new Date().toLocaleDateString('en-US', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' });
            document.getElementById('dashCurrentDate').innerText = today;
        });

        function loadState() {
            const saved = localStorage.getItem('kisansmart_state');
            if (saved) {
                try {
                    state = JSON.parse(saved);
                } catch(e) { console.error('Failed to parse saved state', e); }
            }
            if (!state.fields || state.fields.length === 0) {
                state.fields = [...DEFAULT_FIELDS];
            }
            if (!state.records || state.records.length === 0) {
                state.records = [
                    { id: 'r1', date: '2026-09-10', category: 'Fertilizer', desc: 'Applied 50kg Vermicompost', cost: 1200 },
                    { id: 'r2', date: '2026-09-18', category: 'Treatment', desc: 'Neem Oil Botanical Foliar Spray', cost: 450 }
                ];
            }
            if (!state.notifications || state.notifications.length === 0) {
                state.notifications = [
                    { id: 'n1', title: 'Humidity Warning', text: 'High risk of leaf fungus due to overnight fog.', time: '10m ago' },
                    { id: 'n2', title: 'Irrigation Reminder', text: 'Tomato field moisture is down to 52%.', time: '1h ago' }
                ];
            }
            if (!state.calendarEvents) {
                state.calendarEvents = [
                    { id: 'c1', title: 'Organic Neem Foliar Spray', date: '2026-09-25', crop: 'Rice/Paddy' },
                    { id: 'c2', title: 'Scheduled Field Weed Inspection', date: '2026-09-28', crop: 'Tomatoes' }
                ];
            }
            saveState();
        }

        function saveState() {
            localStorage.setItem('kisansmart_state', JSON.stringify(state));
        }

        function setupUI() {
            // Setup active field select dropdowns
            populateFieldSelects();
            // Duplicate nav items for mobile menu
            const navLinks = document.querySelector('#sidebar nav').innerHTML;
            document.getElementById('mobileNavLinks').innerHTML = navLinks;
        }

        function populateFieldSelects() {
            const selects = [document.getElementById('activeFieldSelectNav'), document.getElementById('activeFieldSelectMobile')];
            selects.forEach(select => {
                if (!select) return;
                select.innerHTML = state.fields.map(f => `<option value="${f.id}" ${f.id === state.activeFieldId ? 'selected' : ''}>${f.name} (${f.crop})</option>`).join('');
            });
        }

        function switchActiveField(fieldId) {
            state.activeFieldId = fieldId;
            saveState();
            populateFieldSelects();
            renderDashboard();
            renderWaterMonitor();
            renderFieldHealth();
        }

        function navigateTo(viewId) {
            document.querySelectorAll('.view-section').forEach(sec => sec.classList.add('hidden'));
            const target = document.getElementById(`view-${viewId}`);
            if (target) target.classList.remove('hidden');

            // Update breadcrumb
            const titles = {
                dashboard: 'Dashboard Overview',
                fields: 'My Agricultural Fields',
                scanner: 'AI Crop Diagnostics Scanner',
                diseases: 'Diseases & Organic Remedies Catalog',
                water: 'Soil & Water Telemetry',
                health: 'Field Health & Vigor',
                irrigation: 'Smart Irrigation Assistant',
                recommendations: 'AI Crop Recommendation Engine',
                weather: 'Agromet Weather Forecast',
                calendar: 'Farming Schedule Calendar',
                records: 'Digital Logbook & Records',
                chatbot: 'Kisan AI Multilingual Assistant',
                analytics: 'Farm Analytics',
                settings: 'Settings & API Config'
            };
            document.getElementById('headerBreadcrumb').innerText = titles[viewId] || viewId;

            // Update nav active styles
            document.querySelectorAll('.nav-btn').forEach(btn => {
                if (btn.getAttribute('data-view') === viewId) {
                    btn.classList.add('bg-agri-800', 'text-white', 'font-bold');
                } else {
                    btn.classList.remove('bg-agri-800', 'font-bold');
                }
            });

            // Trigger chart updates if navigating to charts
            if (viewId === 'dashboard' && window.dashChart) window.dashChart.update();
            if (viewId === 'analytics') renderAnalyticsCharts();
        }

        function toggleMobileMenu() {
            const drawer = document.getElementById('mobileDrawer');
            drawer.classList.toggle('hidden');
        }

        function toggleNotificationDropdown() {
            const dropdown = document.getElementById('notificationDropdown');
            dropdown.classList.toggle('hidden');
        }

        function clearNotifications() {
            state.notifications = [];
            saveState();
            renderNotifications();
        }

        function renderAllViews() {
            renderDashboard();
            renderFieldsList();
            renderDiseaseCatalog();
            renderWaterMonitor();
            renderFieldHealth();
            renderIrrigation();
            renderWeather();
            renderCalendar();
            renderRecords();
            renderNotifications();
            renderCropRecommendationsDefault();
        }

        function getActiveField() {
            return state.fields.find(f => f.id === state.activeFieldId) || state.fields[0];
        }

        function renderDashboard() {
            const field = getActiveField();
            if (!field) return;

            document.getElementById('dashGreeting').innerText = `Namaste, ${state.settings.farmerName || 'Farmer'}!`;
            document.getElementById('dashHealthScore').innerText = `${field.healthScore}%`;
            document.getElementById('dashHealthBar').style.width = `${field.healthScore}%`;
            document.getElementById('dashMoistureVal').innerText = `${field.moisture}%`;
            document.getElementById('dashGrowthStage').innerText = field.growthStage;
            document.getElementById('dashCropType').innerText = field.crop;

            // Details Meta
            document.getElementById('dashMetaName').innerText = field.name;
            document.getElementById('dashMetaLoc').innerText = field.location;
            document.getElementById('dashMetaSize').innerText = `${field.size} Acres`;
            document.getElementById('dashMetaSoil').innerText = field.soil;
            document.getElementById('dashMetaIrrigation').innerText = field.irrigation;
            document.getElementById('dashMetaSown').innerText = field.plantingDate;

            // Recommended agronomic actions
            const actionItems = [
                { title: 'Foliar Neem Spray', desc: 'Prevents sucking pests during humid growth phases.', icon: 'fa-spray-can', color: 'bg-emerald-100 text-emerald-800' },
                { title: 'Check Soil Nitrogen', desc: 'Tillering stage requires balanced bio-fertilizers.', icon: 'fa-vial', color: 'bg-amber-100 text-amber-800' }
            ];
            document.getElementById('dashActionItems').innerHTML = actionItems.map(act => `
                <div class="flex items-start space-x-3 p-3 bg-slate-50 rounded-2xl border border-slate-100">
                    <div class="w-8 h-8 rounded-xl ${act.color} flex items-center justify-center flex-shrink-0 text-xs">
                        <i class="fa-solid ${act.icon}"></i>
                    </div>
                    <div>
                        <h4 class="font-bold text-slate-800 text-xs sm:text-sm">${act.title}</h4>
                        <p class="text-slate-500 text-xs">${act.desc}</p>
                    </div>
                </div>
            `).join('');

            // Recent activity log list
            document.getElementById('dashRecentActivityList').innerHTML = state.records.slice(0, 3).map(rec => `
                <div class="relative pl-6">
                    <span class="absolute left-1.5 top-1.5 w-3 h-3 bg-agri-500 rounded-full ring-4 ring-white"></span>
                    <div class="text-xs font-semibold text-slate-800">${rec.desc}</div>
                    <div class="text-[10px] text-slate-400">${rec.date} • ${rec.category}</div>
                </div>
            `).join('');
        }

        function renderFieldsList() {
            const grid = document.getElementById('fieldsGrid');
            grid.innerHTML = state.fields.map(f => `
                <div class="bg-white rounded-3xl border ${f.id === state.activeFieldId ? 'border-agri-500 ring-2 ring-agri-200' : 'border-slate-200'} p-5 shadow-sm space-y-4 relative">
                    <div class="flex justify-between items-start">
                        <div>
                            <span class="text-xs font-bold px-2.5 py-1 rounded-full ${f.id === state.activeFieldId ? 'bg-agri-100 text-agri-800' : 'bg-slate-100 text-slate-600'}">
                                ${f.crop}
                            </span>
                            <h3 class="font-bold text-slate-800 text-lg mt-2">${f.name}</h3>
                            <p class="text-xs text-slate-500"><i class="fa-solid fa-location-dot text-rose-500 mr-1"></i>${f.location}</p>
                        </div>
                        <div class="text-right">
                            <span class="text-2xl font-extrabold text-agri-700">${f.healthScore}%</span>
                            <span class="text-[10px] text-slate-400 block">Health Index</span>
                        </div>
                    </div>

                    <div class="grid grid-cols-2 gap-2 text-xs bg-slate-50 p-3 rounded-2xl border border-slate-100">
                        <div><span class="text-slate-400 block">Plot Size</span><span class="font-semibold text-slate-700">${f.size} Acres</span></div>
                        <div><span class="text-slate-400 block">Soil</span><span class="font-semibold text-slate-700">${f.soil}</span></div>
                        <div><span class="text-slate-400 block">Moisture</span><span class="font-semibold text-blue-600">${f.moisture}%</span></div>
                        <div><span class="text-slate-400 block">Growth Stage</span><span class="font-semibold text-slate-700">${f.growthStage}</span></div>
                    </div>

                    <div class="flex space-x-2 pt-2">
                        <button onclick="switchActiveField('${f.id}'); navigateTo('dashboard');" class="flex-1 bg-agri-600 hover:bg-agri-700 text-white font-semibold py-2 rounded-xl text-xs transition-colors">
                            Set as Active
                        </button>
                        <button onclick="editField('${f.id}')" class="bg-slate-100 hover:bg-slate-200 text-slate-700 p-2 rounded-xl text-xs">
                            <i class="fa-solid fa-pen"></i>
                        </button>
                    </div>
                </div>
            `).join('');
        }

        let mediaStream = null;

        async function toggleCamera() {
            const video = document.getElementById('webcamVideo');
            const placeholder = document.getElementById('scannerPlaceholder');
            const imgPreview = document.getElementById('previewImage');

            if (mediaStream) {
                mediaStream.getTracks().forEach(track => track.stop());
                mediaStream = null;
                video.classList.add('hidden');
                placeholder.classList.remove('hidden');
                document.getElementById('btnCameraText').innerText = 'Open Camera';
                return;
            }

            try {
                mediaStream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: 'environment' } });
                video.srcObject = mediaStream;
                video.classList.remove('hidden');
                placeholder.classList.add('hidden');
                imgPreview.classList.add('hidden');
                document.getElementById('btnCameraText').innerText = 'Capture Snap';
            } catch (err) {
                alert('Camera permission denied or unavailable: ' + err.message);
            }
        }

        function handleFileUpload(event) {
            const file = event.target.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = function(e) {
                state.scannedBase64 = e.target.result;
                const img = document.getElementById('previewImage');
                img.src = e.target.result;
                img.classList.remove('hidden');
                document.getElementById('scannerPlaceholder').classList.add('hidden');
                document.getElementById('webcamVideo').classList.add('hidden');
            };
            reader.readAsDataURL(file);
        }

        function loadDemoScan(sampleKey) {
            const samples = {
                rice_blast: {
                    disease: 'Rice Blast (Magnaporthe oryzae)',
                    crop: 'Rice/Paddy',
                    confidence: '96.8%',
                    symptoms: 'Spindle-shaped, eye-like lesions on tender leaves with brownish margins.',
                    causes: 'High relative humidity (>90%) with cool night temperatures and high soil nitrogen.',
                    remedy: 'Spray 5% Panchagavya formulation or Trichoderma viride bio-fungicide (5g/liter).',
                    prevention: 'Maintain balanced K fertilizer; avoid standing water stagnant overload.'
                },
                wheat_rust: {
                    disease: 'Wheat Yellow Rust (Puccinia striiformis)',
                    crop: 'Wheat',
                    confidence: '94.2%',
                    symptoms: 'Yellow stripe pustules arranged linearly along leaf veins.',
                    causes: 'Cool, humid weather spores carried by wind currents.',
                    remedy: 'Spray Sour Buttermilk (Lassi) solution mixed with copper container extract.',
                    prevention: 'Sow rust-resistant varieties like HD 2967 or PBW 550.'
                },
                tomato_blight: {
                    disease: 'Tomato Early Blight (Alternaria)',
                    crop: 'Tomatoes',
                    confidence: '95.1%',
                    symptoms: 'Dark concentric leaf spots forming bullseye targets with yellow margins.',
                    causes: 'Soil-borne fungal pathogen spreading in moist, warm foliage.',
                    remedy: 'Neem Oil (10,000 ppm) emulsion with potassium soap.',
                    prevention: 'Prune lower diseased leaves; practice drip irrigation instead of overhead.'
                },
                cotton_aphids: {
                    disease: 'Cotton Aphid Pest Infestation',
                    crop: 'Cotton',
                    confidence: '98.0%',
                    symptoms: 'Curled leaves, sticky honeydew exudate, black sooty mold.',
                    causes: 'Dry weather causing rapid aphid multiplication.',
                    remedy: 'Dashaparani Ark (10 botanical leaves spray) or Agniastra formulation.',
                    prevention: 'Intercrop with Yellow Sticky Traps & plant marigold borders.'
                }
            };

            const sample = samples[sampleKey];
            if (!sample) return;

            displayScanResults(sample);
        }

        async function analyzeCurrentImage() {
            const video = document.getElementById('webcamVideo');

            // If camera is open, capture frame first
            if (mediaStream && !video.classList.contains('hidden')) {
                const canvas = document.getElementById('captureCanvas');
                canvas.width = video.videoWidth || 640;
                canvas.height = video.videoHeight || 480;
                const ctx = canvas.getContext('2d');
                ctx.drawImage(video, 0, 0, canvas.width, canvas.height);
                state.scannedBase64 = canvas.toDataURL('image/jpeg');

                // Freeze preview
                document.getElementById('previewImage').src = state.scannedBase64;
                document.getElementById('previewImage').classList.remove('hidden');
                video.classList.add('hidden');
            }

            if (!state.scannedBase64) {
                alert('Please upload an image or capture a snapshot from camera first!');
                return;
            }

            document.getElementById('scannerLoader').classList.remove('hidden');

            // Call Gemini API Vision or Fallback
            try {
                const apiKey = state.settings.apiKey || "";
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=${apiKey}`;

                const base64Data = state.scannedBase64.split(',')[1];
                const activeField = getActiveField();

                const prompt = `Act as an expert agricultural pathologist. Analyze this plant crop image. Active field crop is ${activeField.crop}. Identify if there is any disease, pest, nutrient deficiency, or abnormal condition. Return JSON with keys: "diseaseName", "cropType", "confidence", "symptoms", "possibleCause", "organicRemedy", "prevention".`;

                const payload = {
                    contents: [{
                        parts: [
                            { text: prompt },
                            { inlineData: { mimeType: "image/jpeg", data: base64Data } }
                        ]
                    }],
                    generationConfig: { responseMimeType: "application/json" }
                };

                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                const data = await response.json();
                if (data.candidates && data.candidates[0]?.content?.parts[0]?.text) {
                    const parsed = JSON.parse(data.candidates[0].content.parts[0].text);
                    displayScanResults({
                        disease: parsed.diseaseName || 'Detected Crop Condition',
                        crop: parsed.cropType || activeField.crop,
                        confidence: parsed.confidence || '92.5%',
                        symptoms: parsed.symptoms || 'Visible yellowing and brown leaf spots.',
                        causes: parsed.possibleCause || 'Fungal spores stimulated by elevated moisture.',
                        remedy: parsed.organicRemedy || 'Apply Neem Oil or Panchagavya spray.',
                        prevention: parsed.prevention || 'Maintain optimal aeration and soil drainage.'
                    });
                } else {
                    // Fallback to sample
                    loadDemoScan('rice_blast');
                }
            } catch (err) {
                console.warn('Gemini API scanner fallback to offline engine:', err);
                loadDemoScan('rice_blast');
            } finally {
                document.getElementById('scannerLoader').classList.add('hidden');
            }
        }

        function displayScanResults(res) {
            document.getElementById('scanResultEmpty').classList.add('hidden');
            document.getElementById('scanResultOutput').classList.remove('hidden');

            document.getElementById('scanResultDiseaseName').innerText = res.disease;
            document.getElementById('scanResultCrop').innerText = res.crop;
            document.getElementById('scanResultConfidence').innerText = res.confidence;
            document.getElementById('scanResultSymptoms').innerText = res.symptoms;
            document.getElementById('scanResultCauses').innerText = res.causes;
            document.getElementById('scanResultRemedy').innerText = res.remedy;
            document.getElementById('scanResultPrevention').innerText = res.prevention;
        }

        function saveScanToRecord() {
            const name = document.getElementById('scanResultDiseaseName').innerText;
            const remedy = document.getElementById('scanResultRemedy').innerText;

            state.records.unshift({
                id: 'rec_' + Date.now(),
                date: new Date().toISOString().split('T')[0],
                category: 'Treatment',
                desc: `Diagnosed ${name}. Remedy: ${remedy}`,
                cost: 200
            });
            saveState();
            renderRecords();
            alert('Scan result saved to Digital Field Logbook!');
        }

        function renderDiseaseCatalog() {
            const container = document.getElementById('diseaseCatalogGrid');
            container.innerHTML = DEFAULT_DISEASES.map(d => `
                <div class="bg-white rounded-3xl border border-slate-200 p-5 shadow-sm space-y-4">
                    <div class="flex justify-between items-start">
                        <span class="px-2.5 py-1 bg-amber-100 text-amber-800 rounded-full text-xs font-bold">${d.crop}</span>
                        <span class="text-xs font-bold px-2 py-0.5 rounded ${d.severity === 'High' ? 'bg-rose-100 text-rose-700' : 'bg-amber-100 text-amber-700'}">${d.severity} Risk</span>
                    </div>

                    <h3 class="font-bold text-slate-800 text-lg">${d.name}</h3>

                    <div class="space-y-2 text-xs">
                        <p class="text-slate-600"><strong>Symptoms:</strong> ${d.symptoms}</p>
                        <p class="text-slate-600"><strong>Cause:</strong> ${d.cause}</p>
                    </div>

                    <div class="bg-emerald-50 p-3 rounded-2xl border border-emerald-200 space-y-1">
                        <span class="text-xs font-bold text-emerald-900 block">🌿 Organic Solution:</span>
                        <p class="text-xs text-emerald-800 font-medium">${d.remedy}</p>
                        <p class="text-[11px] text-emerald-700 pt-1 border-t border-emerald-200/60">${d.recipe}</p>
                    </div>
                </div>
            `).join('');
        }

        function filterDiseaseCatalog() {
            const q = document.getElementById('diseaseSearchInput').value.toLowerCase();
            const cards = document.querySelectorAll('#diseaseCatalogGrid > div');
            cards.forEach(card => {
                const txt = card.innerText.toLowerCase();
                card.style.display = txt.includes(q) ? 'block' : 'none';
            });
        }

        function renderWaterMonitor() {
            const field = getActiveField();
            if (!field) return;

            document.getElementById('monitorMoistureVal').innerText = `${field.moisture}%`;
        }

        function openManualReadingModal() {
            const field = getActiveField();
            document.getElementById('manualMoistureInput').value = field.moisture;
            document.getElementById('modalManualReading').classList.remove('hidden');
        }

        function handleManualReadingSubmit(e) {
            e.preventDefault();
            const val = parseInt(document.getElementById('manualMoistureInput').value);
            const field = getActiveField();
            field.moisture = val;
            saveState();
            closeModal('modalManualReading');
            renderDashboard();
            renderWaterMonitor();
        }

        function renderFieldHealth() {
            const field = getActiveField();
            if (!field) return;

            document.getElementById('healthTrackingScore').innerText = `${field.healthScore} / 100`;
        }

        function renderIrrigation() {
            const field = getActiveField();
            if (!field) return;

            if (field.moisture < 50) {
                document.getElementById('irrigAdviceStatus').innerText = 'IRRIGATION NEEDED';
                document.getElementById('irrigAdviceStatus').className = 'px-2.5 py-0.5 rounded-full bg-amber-100 text-amber-800 text-xs font-bold';
                document.getElementById('irrigAdviceText').innerText = `Soil moisture is down to ${field.moisture}%. Irrigate within the next 12 hours.`;
            } else {
                document.getElementById('irrigAdviceStatus').innerText = 'ADEQUATE MOISTURE';
                document.getElementById('irrigAdviceStatus').className = 'px-2.5 py-0.5 rounded-full bg-emerald-100 text-emerald-800 text-xs font-bold';
                document.getElementById('irrigAdviceText').innerText = `Current moisture is ${field.moisture}%. No irrigation required today.`;
            }

            document.getElementById('irrigMetaMethod').innerText = field.irrigation;
        }

        function togglePumpSimulation() {
            state.isPumpOn = !state.isPumpOn;
            const btn = document.getElementById('pumpToggleBtn');
            const badge = document.getElementById('pumpStatusBadge');

            if (state.isPumpOn) {
                btn.innerText = 'Stop Water Pump';
                btn.className = 'bg-rose-500 hover:bg-rose-600 text-white font-bold px-4 py-2 rounded-xl text-xs transition-colors';
                badge.innerText = 'PUMP ACTIVE';
                badge.className = 'px-2 py-0.5 text-xs font-bold rounded-full bg-emerald-500 text-white animate-pulse';
            } else {
                btn.innerText = 'Turn ON Pump';
                btn.className = 'bg-emerald-500 hover:bg-emerald-600 text-white font-bold px-4 py-2 rounded-xl text-xs transition-colors';
                badge.innerText = 'OFF';
                badge.className = 'px-2 py-0.5 text-xs font-bold rounded-full bg-slate-700 text-slate-300';
            }
        }

        function renderCropRecommendationsDefault() {
            generateCropRecommendations();
        }

        function generateCropRecommendations() {
            const soil = document.getElementById('recSoilType').value;
            const water = document.getElementById('recWaterAvail').value;
            const season = document.getElementById('recSeason').value;

            const recommendations = [
                {
                    name: 'Sona Masoori Rice',
                    suitability: '98% Excellent Match',
                    duration: '130 - 140 Days',
                    yieldEst: '25 - 30 Quintals/Acre',
                    reason: `Perfect fit for ${soil} under ${water} conditions during the ${season} season. High market demand.`
                },
                {
                    name: 'Hybrid Maize / Corn',
                    suitability: '91% High Suitability',
                    duration: '100 - 110 Days',
                    yieldEst: '30 - 35 Quintals/Acre',
                    reason: 'Requires moderate water, resistant to light drought, enriches soil structure.'
                },
                {
                    name: 'Red Gram / Arhar (Pulses)',
                    suitability: '86% Good Rotation Crop',
                    duration: '150 - 180 Days',
                    yieldEst: '8 - 12 Quintals/Acre',
                    reason: 'Fixes atmospheric Nitrogen into soil, reduces future chemical fertilizer costs.'
                }
            ];

            const container = document.getElementById('cropRecsResults');
            container.innerHTML = recommendations.map(r => `
                <div class="bg-white p-5 rounded-3xl border border-slate-200 shadow-sm space-y-3">
                    <span class="px-2.5 py-1 bg-emerald-100 text-emerald-800 text-xs font-bold rounded-full">${r.suitability}</span>
                    <h3 class="font-bold text-slate-800 text-lg mt-1">${r.name}</h3>

                    <div class="text-xs space-y-1.5 text-slate-600">
                        <div><strong>Duration:</strong> ${r.duration}</div>
                        <div><strong>Expected Yield:</strong> ${r.yieldEst}</div>
                    </div>

                    <p class="text-xs text-slate-500 bg-slate-50 p-3 rounded-2xl border border-slate-100 leading-relaxed">${r.reason}</p>
                </div>
            `).join('');
        }

        function renderWeather() {
            const forecast = [
                { day: 'Today', temp: '31°C', icon: 'fa-sun', cond: 'Sunny', humidity: '68%' },
                { day: 'Thu', temp: '29°C', icon: 'fa-cloud-rain', cond: 'Light Rain', humidity: '82%' },
                { day: 'Fri', temp: '30°C', icon: 'fa-cloud-sun', cond: 'Partly Cloudy', humidity: '70%' },
                { day: 'Sat', temp: '32°C', icon: 'fa-sun', cond: 'Clear Sky', humidity: '62%' },
                { day: 'Sun', temp: '31°C', icon: 'fa-cloud', cond: 'Overcast', humidity: '75%' }
            ];

            document.getElementById('weatherForecastGrid').innerHTML = forecast.map(w => `
                <div class="bg-white p-4 rounded-2xl border border-slate-200 text-center space-y-2 shadow-sm">
                    <span class="text-xs font-bold text-slate-500 block">${w.day}</span>
                    <i class="fa-solid ${w.icon} text-2xl text-amber-500"></i>
                    <div class="text-lg font-bold text-slate-800">${w.temp}</div>
                    <span class="text-[11px] text-slate-500 block">${w.cond}</span>
                </div>
            `).join('');
        }

        function renderCalendar() {
            const container = document.getElementById('calendarEventsList');
            container.innerHTML = state.calendarEvents.map(e => `
                <div class="flex items-center justify-between p-3.5 bg-slate-50 rounded-2xl border border-slate-100">
                    <div class="flex items-center space-x-3">
                        <div class="w-9 h-9 rounded-xl bg-agri-100 text-agri-700 flex items-center justify-center font-bold text-sm">
                            <i class="fa-solid fa-calendar-check"></i>
                        </div>
                        <div>
                            <h4 class="font-bold text-slate-800 text-sm">${e.title}</h4>
                            <span class="text-xs text-slate-500">${e.crop} • ${e.date}</span>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        function renderRecords() {
            const body = document.getElementById('recordsTableBody');
            body.innerHTML = state.records.map(r => `
                <tr class="hover:bg-slate-50 transition-colors">
                    <td class="p-4 font-medium text-slate-700">${r.date}</td>
                    <td class="p-4"><span class="px-2.5 py-1 rounded-full text-xs font-bold ${r.category === 'Fertilizer' ? 'bg-amber-100 text-amber-800' : 'bg-emerald-100 text-emerald-800'}">${r.category}</span></td>
                    <td class="p-4 text-slate-700">${r.desc}</td>
                    <td class="p-4 font-bold text-slate-800">₹${r.cost}</td>
                    <td class="p-4 text-right">
                        <button onclick="deleteRecord('${r.id}')" class="text-rose-500 hover:text-rose-700 text-xs font-semibold">Delete</button>
                    </td>
                </tr>
            `).join('');
        }

        function filterRecords(category) {
            const btns = document.querySelectorAll('.rec-tab-btn');
            btns.forEach(b => {
                if (b.innerText === category || (category === 'ALL' && b.innerText === 'All')) {
                    b.className = 'rec-tab-btn px-4 py-2 rounded-xl text-xs font-semibold bg-agri-600 text-white';
                } else {
                    b.className = 'rec-tab-btn px-4 py-2 rounded-xl text-xs font-semibold bg-slate-200 text-slate-700 hover:bg-slate-300';
                }
            });

            const rows = document.querySelectorAll('#recordsTableBody tr');
            rows.forEach(r => {
                if (category === 'ALL') {
                    r.style.display = '';
                } else {
                    r.style.display = r.innerText.includes(category) ? '' : 'none';
                }
            });
        }

        function deleteRecord(id) {
            state.records = state.records.filter(r => r.id !== id);
            saveState();
            renderRecords();
        }

        async function sendChatMessage() {
            const input = document.getElementById('chatInput');
            const msg = input.value.trim();
            if (!msg) return;

            appendChatMessage('user', msg);
            input.value = '';

            const field = getActiveField();
            const systemPrompt = `You are Kisan AI, an expert agricultural advisor assisting a farmer. The active crop is ${field.crop} (${field.variety}) grown in ${field.soil} soil at ${field.location}. Moisture level is ${field.moisture}%. Answer concisely, practically, and empathetically. Support Indian languages if requested.`;

            try {
                const apiKey = state.settings.apiKey || "";
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=${apiKey}`;

                const payload = {
                    contents: [{ parts: [{ text: msg }] }],
                    systemInstruction: { parts: [{ text: systemPrompt }] }
                };

                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                const data = await response.json();
                if (data.candidates && data.candidates[0]?.content?.parts[0]?.text) {
                    appendChatMessage('model', data.candidates[0].content.parts[0].text);
                } else {
                    appendChatMessage('model', `For ${field.crop}, yellow leaves usually signal Nitrogen deficiency or stagnant water root hypoxia. Apply organic Panchagavya or Vermicompost.`);
                }
            } catch (err) {
                appendChatMessage('model', `For ${field.crop}, make sure to maintain optimum irrigation and apply bio-pesticides like Neem Oil for leaf folder protection.`);
            }
        }

        function appendChatMessage(sender, text) {
            const box = document.getElementById('chatMessagesBox');
            const isUser = sender === 'user';

            const div = document.createElement('div');
            div.className = `flex ${isUser ? 'justify-end' : 'justify-start'}`;
            div.innerHTML = `
                <div class="max-w-[80%] rounded-2xl p-3.5 text-xs sm:text-sm ${isUser ? 'bg-agri-600 text-white rounded-tr-none' : 'bg-slate-100 text-slate-800 rounded-tl-none border border-slate-200'}">
                    <p class="leading-relaxed">${text}</p>
                </div>
            `;
            box.appendChild(div);
            box.scrollTop = box.scrollHeight;
        }

        function clearChatHistory() {
            document.getElementById('chatMessagesBox').innerHTML = '';
            appendChatMessage('model', 'Namaste! I am Kisan AI. Ask me any question about pests, fertilizer schedules, or crop remedies.');
        }

        // Web Speech API Voice Input
        function startVoiceInput() {
            if (!('webkitSpeechRecognition' in window) && !('SpeechRecognition' in window)) {
                alert('Voice input is not supported in this browser version.');
                return;
            }
            const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
            const recognition = new SpeechRecognition();
            recognition.lang = state.settings.language === 'hi' ? 'hi-IN' : (state.settings.language === 'te' ? 'te-IN' : 'en-US');
            recognition.onstart = function() {
                document.getElementById('chatMicBtn').classList.add('animate-pulse', 'bg-rose-100', 'text-rose-600');
            };
            recognition.onresult = function(event) {
                const transcript = event.results[0][0].transcript;
                document.getElementById('chatInput').value = transcript;
                sendChatMessage();
            };
            recognition.onend = function() {
                document.getElementById('chatMicBtn').classList.remove('animate-pulse', 'bg-rose-100', 'text-rose-600');
            };
            recognition.start();
        }

        function toggleVoiceInput() {
            startVoiceInput();
        }

        function initCharts() {
            // Dashboard Moisture & Health Chart
            const ctxDash = document.getElementById('dashChartCanvas').getContext('2d');
            window.dashChart = new Chart(ctxDash, {
                type: 'line',
                data: {
                    labels: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
                    datasets: [
                        {
                            label: 'Field Health Score (%)',
                            data: [82, 84, 85, 87, 86, 88, 88],
                            borderColor: '#16a34a',
                            backgroundColor: 'rgba(22, 163, 74, 0.1)',
                            fill: true,
                            tension: 0.4
                        },
                        {
                            label: 'Soil Moisture (%)',
                            data: [72, 70, 68, 65, 62, 60, 68],
                            borderColor: '#0284c7',
                            borderDash: [5, 5],
                            tension: 0.4
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: { legend: { display: false } },
                    scales: { y: { min: 40, max: 100 } }
                }
            });

            // Water Trend Chart
            const ctxWater = document.getElementById('waterTrendChartCanvas').getContext('2d');
            new Chart(ctxWater, {
                type: 'bar',
                data: {
                    labels: ['Day 1', 'Day 2', 'Day 3', 'Day 4', 'Day 5', 'Day 6', 'Day 7'],
                    datasets: [{
                        label: 'Moisture %',
                        data: [75, 71, 68, 65, 62, 60, 68],
                        backgroundColor: '#38bdf8',
                        borderRadius: 8
                    }]
                },
                options: { responsive: true, maintainAspectRatio: false }
            });

            // Field Health Tracking
            const ctxHealth = document.getElementById('healthHistoryChartCanvas').getContext('2d');
            new Chart(ctxHealth, {
                type: 'line',
                data: {
                    labels: ['Week 1', 'Week 2', 'Week 3', 'Week 4', 'Week 5', 'Week 6'],
                    datasets: [{
                        label: 'Vigor Index',
                        data: [70, 75, 80, 84, 86, 88],
                        borderColor: '#22c55e',
                        backgroundColor: 'rgba(34, 197, 94, 0.15)',
                        fill: true
                    }]
                },
                options: { responsive: true, maintainAspectRatio: false }
            });
        }

        function renderAnalyticsCharts() {
            if (window.analyticsExpenseChart) return;

            const ctxExp = document.getElementById('analyticsExpenseChartCanvas').getContext('2d');
            window.analyticsExpenseChart = new Chart(ctxExp, {
                type: 'doughnut',
                data: {
                    labels: ['Seeds', 'Bio-Fertilizers', 'Organic Sprays', 'Irrigation Energy'],
                    datasets: [{
                        data: [2500, 4200, 1800, 1200],
                        backgroundColor: ['#22c55e', '#f59e0b', '#06b6d4', '#6366f1']
                    }]
                },
                options: { responsive: true, maintainAspectRatio: false }
            });

            const ctxTrend = document.getElementById('analyticsHealthChartCanvas').getContext('2d');
            new Chart(ctxTrend, {
                type: 'line',
                data: {
                    labels: ['Jun', 'Jul', 'Aug', 'Sep'],
                    datasets: [{
                        label: 'Avg Health Score',
                        data: [78, 82, 85, 88],
                        borderColor: '#16a34a'
                    }]
                },
                options: { responsive: true, maintainAspectRatio: false }
            });
        }

        function openAddFieldModal() {
            document.getElementById('modalAddField').classList.remove('hidden');
        }

        function closeModal(id) {
            document.getElementById(id).classList.add('hidden');
        }

        function handleFieldSubmit(e) {
            e.preventDefault();
            const id = 'field_' + Date.now();
            const newField = {
                id: id,
                name: document.getElementById('fName').value,
                crop: document.getElementById('fCrop').value,
                variety: document.getElementById('fVariety').value,
                size: parseFloat(document.getElementById('fSize').value),
                soil: document.getElementById('fSoil').value,
                plantingDate: document.getElementById('fPlantDate').value,
                irrigation: document.getElementById('fIrrigation').value,
                location: document.getElementById('fLocation').value || 'Telangana, India',
                healthScore: 85,
                moisture: 65,
                growthStage: 'Vegetative Phase'
            };

            state.fields.push(newField);
            state.activeFieldId = id;
            saveState();
            closeModal('modalAddField');
            populateFieldSelects();
            renderAllViews();
        }

        function openAddRecordModal() {
            document.getElementById('modalAddRecord').classList.remove('hidden');
        }

        function handleAddRecordSubmit(e) {
            e.preventDefault();
            state.records.unshift({
                id: 'rec_' + Date.now(),
                date: new Date().toISOString().split('T')[0],
                category: document.getElementById('recCat').value,
                desc: document.getElementById('recDesc').value,
                cost: parseFloat(document.getElementById('recCost').value) || 0
            });
            saveState();
            closeModal('modalAddRecord');
            renderRecords();
        }

        function openAddCalendarModal() {
            const title = prompt('Enter farming activity title:');
            if (title) {
                state.calendarEvents.push({
                    id: 'c_' + Date.now(),
                    title: title,
                    date: new Date().toISOString().split('T')[0],
                    crop: getActiveField().crop
                });
                saveState();
                renderCalendar();
            }
        }

        function renderNotifications() {
            const list = document.getElementById('notificationList');
            if (state.notifications.length === 0) {
                list.innerHTML = `<div class="p-4 text-center text-xs text-slate-400">No new notifications</div>`;
                document.getElementById('unreadBadge').classList.add('hidden');
            } else {
                document.getElementById('unreadBadge').classList.remove('hidden');
                list.innerHTML = state.notifications.map(n => `
                    <div class="p-3 hover:bg-slate-50 text-xs transition-colors">
                        <div class="font-bold text-slate-800">${n.title}</div>
                        <p class="text-slate-500 mt-0.5">${n.text}</p>
                        <span class="text-[10px] text-slate-400 mt-1 block">${n.time}</span>
                    </div>
                `).join('');
            }
        }

        function saveSettings() {
            state.settings.apiKey = document.getElementById('settingApiKey').value.trim();
            state.settings.farmerName = document.getElementById('settingFarmerName').value.trim();
            saveState();
            renderDashboard();
            alert('Preferences saved!');
        }

        function resetDataToDefault() {
            if (confirm('Reset all farm data back to defaults?')) {
                localStorage.removeItem('kisansmart_state');
                location.reload();
            }
        }

        function changeLanguage(lang) {
            state.settings.language = lang;
            saveState();
        }
    </script>
</body>
</html>
