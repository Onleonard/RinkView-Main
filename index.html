<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Versions Hub - Modernes Portal</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <!-- App-Logik -->
    <script>
        function appData() {
            return {
                versions: [
                    {
                        id: "v3.0.0",
                        name: "Project Nova Release",
                        date: "06. April 2026",
                        status: "Stable",
                        link: "#",
                        whatsNew: ["Modernes Glassmorphism UI", "KI-Integration", "Cloud Sync"],
                        bugFixes: ["Mobile Fixes", "Memory Leak behoben"],
                        comments: [
                            { id: 1, user: "Verfasser", text: "Dies ist der finale Build für dieses Quartal. Alle Core-Features sind stabil.", time: "Vor 2 Std." },
                            { id: 2, user: "Verfasser", text: "Hinweis: Das Update benötigt mindestens 500MB freien Speicher.", time: "Vor 1 Std." }
                        ]
                    },
                    {
                        id: "v2.8.0",
                        name: "Speed Update",
                        date: "20. März 2026",
                        status: "Update",
                        link: "#",
                        whatsNew: ["3x schnelleres Laden", "Neues Dashboard"],
                        bugFixes: ["Safari Bugfix"],
                        comments: [
                            { id: 1, user: "Verfasser", text: "Performance-Tests zeigen eine signifikante Verbesserung der Latenz.", time: "20. März" }
                        ]
                    }
                ],
                init() {
                    lucide.createIcons();
                }
            }
        }
    </script>

    <!-- Alpine.js mit defer -->
    <script src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>

    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap');
        
        body {
            font-family: 'Inter', sans-serif;
            background-color: #020617;
        }

        .glass {
            background: rgba(15, 23, 42, 0.8);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .custom-scrollbar::-webkit-scrollbar {
            width: 5px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.02);
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-up {
            animation: fadeInUp 0.6s ease-out forwards;
        }
    </style>
</head>
<body class="text-slate-200 overflow-x-hidden" x-data="appData()">

    <!-- Hintergrund Effekte -->
    <div class="fixed top-[-10%] left-[-10%] w-[40vw] h-[40vw] rounded-full bg-cyan-600/10 blur-[120px] pointer-events-none"></div>
    <div class="fixed bottom-[-10%] right-[-10%] w-[40vw] h-[40vw] rounded-full bg-blue-600/10 blur-[120px] pointer-events-none"></div>

    <div class="relative z-10 max-w-4xl mx-auto px-4 py-16 flex flex-col gap-12">
        
        <!-- Header -->
        <header class="text-center space-y-4 animate-up">
            <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-white/5 border border-white/10 text-cyan-400 text-sm font-medium mb-4">
                <i data-lucide="star" class="w-3.5 h-3.5"></i> Verfasser-Portal
            </div>
            <h1 class="text-5xl md:text-7xl font-extrabold tracking-tight text-transparent bg-clip-text bg-gradient-to-r from-white via-cyan-100 to-slate-400">
                Versions Hub
            </h1>
            <p class="text-lg md:text-xl text-slate-400 max-w-2xl mx-auto font-light">
                Offizielle Dokumentation und Anmerkungen des Verfassers zu jedem Release.
            </p>
        </header>

        <!-- Liste der Versionen -->
        <div class="space-y-10 relative before:absolute before:inset-0 before:ml-5 before:h-full before:w-0.5 before:bg-gradient-to-b before:from-transparent before:via-white/10 before:to-transparent">
            
            <template x-for="(version, index) in versions" :key="version.id">
                <div class="relative z-10 animate-up" :style="'animation-delay: ' + (index * 150) + 'ms'">
                    
                    <div class="absolute -inset-0.5 bg-gradient-to-r from-cyan-500 to-blue-600 rounded-2xl blur opacity-10 transition duration-500 group-hover:opacity-30"></div>
                    
                    <div class="relative glass rounded-2xl p-6 md:p-8 flex flex-col gap-6" x-data="{ activeTab: 'details' }">
                        
                        <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
                            <div>
                                <div class="flex items-center gap-3 mb-2">
                                    <h2 class="text-3xl font-bold text-white" x-text="version.id"></h2>
                                    <span x-text="version.status" 
                                          :class="version.status === 'Stable' ? 'bg-emerald-500/10 text-emerald-400 border-emerald-500/20' : 'bg-blue-500/10 text-blue-400 border-blue-500/20'"
                                          class="px-3 py-1 rounded-full text-xs font-semibold border"></span>
                                </div>
                                <div class="flex items-center gap-2 text-sm text-slate-400">
                                    <span class="text-slate-200" x-text="version.name"></span>
                                    <span class="w-1 h-1 rounded-full bg-slate-700"></span>
                                    <i data-lucide="clock" class="w-3.5 h-3.5"></i>
                                    <span x-text="version.date"></span>
                                </div>
                            </div>

                            <a :href="version.link" target="_blank" class="flex items-center justify-center gap-2 px-6 py-3 bg-gradient-to-r from-cyan-500 to-blue-600 text-white font-semibold rounded-xl transition-all hover:scale-105 hover:shadow-[0_0_20px_rgba(6,182,212,0.3)]">
                                Öffnen <i data-lucide="external-link" class="w-4 h-4"></i>
                            </a>
                        </div>

                        <hr class="border-white/5">

                        <!-- Tabs -->
                        <div class="flex gap-4 p-1 bg-white/5 rounded-xl">
                            <button @click="activeTab = 'details'" 
                                    :class="activeTab === 'details' ? 'bg-white/10 text-white shadow-lg' : 'text-slate-400'"
                                    class="flex-1 py-2 text-sm font-medium rounded-lg transition-all">Details & Fixes</button>
                            <button @click="activeTab = 'comments'" 
                                    :class="activeTab === 'comments' ? 'bg-white/10 text-white shadow-lg' : 'text-slate-400'"
                                    class="flex-1 py-2 text-sm font-medium rounded-lg transition-all flex items-center justify-center gap-2">
                                Anmerkungen <span class="bg-cyan-500/20 text-cyan-400 px-2 py-0.5 rounded-full text-[10px]" x-text="version.comments.length"></span>
                            </button>
                        </div>

                        <!-- Content Bereich -->
                        <div class="min-h-[220px]">
                            <!-- Details Tab -->
                            <div x-show="activeTab === 'details'" class="space-y-6">
                                <div class="space-y-3">
                                    <h3 class="flex items-center gap-2 text-emerald-400 font-semibold"><i data-lucide="sparkles" class="w-4 h-4"></i> Was ist neu?</h3>
                                    <ul class="space-y-2">
                                        <template x-for="item in version.whatsNew">
                                            <li class="flex items-start gap-2 text-slate-300 text-sm">
                                                <i data-lucide="chevron-right" class="w-4 h-4 mt-0.5 text-emerald-500/40 shrink-0"></i>
                                                <span x-text="item"></span>
                                            </li>
                                        </template>
                                    </ul>
                                </div>
                                <div class="space-y-3" x-show="version.bugFixes.length > 0">
                                    <h3 class="flex items-center gap-2 text-orange-400 font-semibold"><i data-lucide="bug" class="w-4 h-4"></i> Fehlerbehebungen</h3>
                                    <ul class="space-y-2">
                                        <template x-for="item in version.bugFixes">
                                            <li class="flex items-start gap-2 text-slate-300 text-sm">
                                                <i data-lucide="chevron-right" class="w-4 h-4 mt-0.5 text-orange-500/40 shrink-0"></i>
                                                <span x-text="item"></span>
                                            </li>
                                        </template>
                                    </ul>
                                </div>
                            </div>

                            <!-- Kommentare Tab (Nur Anzeige) -->
                            <div x-show="activeTab === 'comments'" class="flex flex-col h-full space-y-4">
                                <div class="space-y-3 max-h-[300px] overflow-y-auto pr-2 custom-scrollbar">
                                    <template x-if="version.comments.length === 0">
                                        <div class="text-center py-10 text-slate-500 italic text-sm">Keine Anmerkungen vom Verfasser.</div>
                                    </template>
                                    <template x-for="comment in version.comments" :key="comment.id">
                                        <div class="bg-white/5 border border-white/5 rounded-xl p-4">
                                            <div class="flex justify-between items-center mb-1">
                                                <div class="flex items-center gap-2">
                                                    <div class="w-2 h-2 rounded-full bg-cyan-500"></div>
                                                    <span class="text-cyan-400 font-bold text-xs" x-text="comment.user"></span>
                                                </div>
                                                <span class="text-[10px] text-slate-500" x-text="comment.time"></span>
                                            </div>
                                            <p class="text-slate-300 text-sm leading-relaxed" x-text="comment.text"></p>
                                        </div>
                                    </template>
                                </div>
                            </div>
                        </div>

                    </div>
                </div>
            </template>

        </div>

        <footer class="text-center pt-8 border-t border-white/5 text-slate-600 text-xs">
            <p>&copy; 2026 Versions Hub - Nur autorisierte Einträge</p>
        </footer>
    </div>

</body>
</html>
