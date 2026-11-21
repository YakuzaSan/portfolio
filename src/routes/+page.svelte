$c = @'
<script lang="ts">
    import { dev } from '$app/environment';
    import { inject } from '@vercel/analytics';
    inject({ mode: dev ? 'development' : 'production' });

    const di = (p: string) => `https://cdn.jsdelivr.net/gh/devicons/devicon/icons/${p}`;

    const skillRows: { name: string; img?: string; short?: string }[][] = [
        [
            { name: 'Cisco', img: 'https://cdn.simpleicons.org/cisco/1BA0D7' },
            { name: 'Windows Server', img: di('windows11/windows11-original.svg') },
            { name: 'Azure / Intune', img: di('azure/azure-original.svg') },
            { name: 'PowerShell', img: di('powershell/powershell-original.svg') },
            { name: 'Linux', img: di('linux/linux-original.svg') },
            { name: 'Ubuntu', img: di('ubuntu/ubuntu-original.svg') },
            { name: 'Docker', img: di('docker/docker-original.svg') },
            { name: 'PRTG', img: 'https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/paessler-prtg.svg' },
            { name: 'GFOS MES', img: 'https://www.google.com/s2/favicons?domain=gfos.com&sz=128' }
        ],
        [
            { name: 'Bash', img: di('bash/bash-original.svg') },
            { name: 'Git', img: di('git/git-original.svg') },
            { name: 'GitHub', img: di('github/github-original.svg') },
            { name: 'Nginx', img: di('nginx/nginx-original.svg') },
            { name: 'Apache', img: di('apache/apache-original.svg') },
            { name: 'SQL Server', img: di('microsoftsqlserver/microsoftsqlserver-plain.svg') },
            { name: 'MySQL', img: di('mysql/mysql-original.svg') }
        ],
        [
            { name: 'TypeScript', img: di('typescript/typescript-original.svg') },
            { name: 'Svelte', img: di('svelte/svelte-original.svg') },
            { name: 'C#', img: di('csharp/csharp-original.svg') },
            { name: 'Unity', img: di('unity/unity-original.svg') },
            { name: 'Python', img: di('python/python-original.svg') },
            { name: 'Tailwind', img: di('tailwindcss/tailwindcss-original.svg') },
            { name: 'VS Code', img: di('vscode/vscode-original.svg') }
        ]
    ];

    const focus = [
        { file: 'netzwerk.conf', color: 'text-emerald-400', items: ['VLANs & Switchports', '802.1X · MAB · RADIUS', 'DHCP Fehlersuche', 'Monitoring mit PRTG'] },
        { file: 'clients.ps1', color: 'text-cyan-400', items: ['Windows Rollout', 'Intune & GPO', 'Kiosk PCs', 'Universal Print · Zebra'] },
        { file: 'produktion.log', color: 'text-amber-400', items: ['Maschinen & Messgeräte', 'GFOS MES', 'SAP Schnittstellen', 'Shopfloor bis ERP'] },
        { file: 'support.md', color: 'text-fuchsia-400', items: ['Mehrere Standorte', 'VoIP Umstellung', 'Hardware Diagnose', 'Saubere Doku'] }
    ];

    const timeline = [
        {
            when: '01/2026 bis heute',
            title: 'Werkstudent IT Infrastruktur',
            where: 'Otto Krahn Group · Zülpich & Hamburg',
            points: [
                'Desk Sharing und Besuchermanagement: Planung, Konfiguration und Rollout an 5 Standorten inkl. internationalem Rollout und Schulung der Mitarbeiter',
                'Netzwerk: Port Logik mit 802.1X, MAB und VLANs, Analyse von Verbindungsabbrüchen, Monitoring mit PRTG',
                'Unterstützung bei Infrastrukturprojekten rund um Netzwerk, Server und Cloud Anbindungen',
                'Installation, Konfiguration und Support für Clients, Drucker und Netzwerkkomponenten, Austausch der Telefonie auf VoIP, Kiosk PCs',
                'Wartung und Konfiguration der Zebra Etikettendrucker in der Produktion',
                'Produktions IT: GFOS MES, SAP Anbindung, Systemlandschaft dokumentiert und IT Dokumentation gepflegt'
            ]
        },
        {
            when: 'Praxisprojekt',
            title: 'Automatisierung Messdaten Abruf',
            where: 'Produktions IT · Pilot an einem Extruder · laufend',
            points: [
                'Ausgangslage: Ein Messsystem zur Qualitätsüberwachung am Extruder speichert nur die letzten 1500 Ereignisse. Der Schichtführer holt das Logbuch per USB Stick und schneidet es von Hand pro Fertigungsauftrag zu',
                'Bestandsaufnahme vor Ort: Gerät, Schnittstellen, Netzwerkkonfiguration und Switchport aufgenommen und mit Fotos und Quellen dokumentiert, Fakten und Annahmen getrennt',
                'Datenanalyse: Logbuchexporte ausgewertet, Volumen pro Schicht bestimmt, festgestellt, dass das Logbuch keine Auftragsnummer enthält',
                'Abstimmung mit Netzwerk Team, Hersteller und Produktion: Netzanbindung, Schnittstellen des Geräts und Quelle der Auftragszeiten',
                'Netzwerkkonzept: Erreichbarkeit des Geräts über IP, Gateway bzw. VLAN, abgestimmt mit der Umstellung der Switchports auf 802.1X und MAB',
                'Lösung: Skript als geplante Aufgabe unter einem Dienstkonto, nur lesend, holt neue Einträge alle 8 Stunden, speichert Rohdaten unverändert und ordnet sie über die Auftragszeiten aus dem MES den Fertigungsaufträgen zu',
                'Abruf auf Knopfdruck für Schichtführer über eine Trigger Datei, ohne dass Client PCs direkten Zugriff auf das Gerät brauchen',
                'Betrieb: Protokoll jedes Laufs, Meldung bei Fehlern, Ablage nach abgestimmter Ordnerstruktur',
                'Ziel: kein USB Stick mehr, weniger Handarbeit, nachvollziehbare Daten je Auftrag. Pilot an einem Extruder, danach Ausrollen auf weitere Linien'
            ]
        },
        {
            when: '09/2022 bis 03/2027',
            title: 'B.Sc. Informatik',
            where: 'FH Aachen · Abschluss voraussichtlich März 2027',
            points: [
                'Smart Bird Feeder: IoT Vogelhaus mit Raspberry Pi, 2 Kameras, Bewegungs- und Gewichtssensor, Solarbetrieb und KI Vogelerkennung in Python',
                'Backend mit Laravel und PostgreSQL, Mobile App mit React Native Expo',
                'SPS Programmierung in Structured Text und PID Motorsteuerung mit Raspberry Pi 5',
                'Parallel: Vorbereitung auf die Cisco CCNA (200-301)'
            ]
        }
    ];

    const projects = [
        { icon: '🖥️', title: 'Homelab', text: 'Selbst geplanter Heimserver mit Unraid und RAID-Z1. Unifi Gateway als Firewall mit 5 getrennten VLANs, Tailscale VPN statt offener Ports, Reverse Proxy, NAS mit Rechten pro Nutzer und eigener Domain Controller mit Active Directory.', tags: ['Unraid', 'Unifi / VLAN', 'Tailscale', 'Docker', 'Active Directory'] },
        { icon: '📡', title: 'CCNA Lab', text: 'Netzwerk Labs in Packet Tracer: VLANs, Trunks, Routing, STP, ACLs und DHCP als Vorbereitung auf die CCNA.', tags: ['Cisco', 'Packet Tracer', 'Routing', 'Switching'] },
        { icon: '🐦', title: 'Smart Bird Feeder', text: 'FH Projekt: IoT Vogelhaus mit Raspberry Pi, Kameras, Sensoren und Solarpanel. KI erkennt die Vogelart, Daten landen in PostgreSQL und in einer App.', tags: ['Raspberry Pi', 'Python', 'IoT', 'PostgreSQL'] },
        { icon: '💬', title: 'SpringsChat', text: 'Selbst gehostete Chat und Kollaborationsplattform mit Fokus auf Datenschutz. Läuft auf meinem Homelab.', tags: ['Java', 'Spring Boot', 'PostgreSQL', 'Self Hosted'] },
        { icon: '🏠', title: 'Smart Home', text: 'Home Assistant mit eigenen Automatisierungen in YAML.', tags: ['Home Assistant', 'YAML'] },
        { icon: '🎮', title: 'False Frame', text: '2D Spiel in Unity als Hobbyprojekt neben Studium und Arbeit.', tags: ['Unity', 'C#', '2D'] }
    ];

    let mobileMenuOpen = $state(false);
    const nav = [['about', 'Über mich'], ['experience', 'Erfahrung'], ['skills', 'Technologien'], ['projects', 'Projekte']];

    function go(e: Event, id: string) {
        e.preventDefault();
        document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });
        mobileMenuOpen = false;
    }
</script>

<svelte:head>
    <title>Lin Yihang · IT Infrastructure</title>
    <meta name="description" content="Lin Yihang, Informatik Student und Werkstudent IT Infrastruktur. Netzwerk, Client Management und Produktions IT.">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Lin Yihang · IT Infrastructure">
    <meta property="og:type" content="website">
    <meta property="og:title" content="Lin Yihang · IT Infrastructure">
    <meta property="og:url" content="https://lin-yihang.de">
</svelte:head>

<nav class="fixed top-0 inset-x-0 z-50 bg-slate-950/70 backdrop-blur-lg border-b border-slate-800/80">
    <div class="max-w-6xl mx-auto px-6 flex items-center justify-between h-16">
        <a href="#home" onclick={(e) => go(e, 'home')} class="font-mono font-bold text-emerald-400">~/lin-yihang<span class="blink">_</span></a>
        <div class="hidden md:flex items-center gap-8 text-sm">
            {#each nav as [id, label]}
                <a href={'#' + id} onclick={(e) => go(e, id)} class="text-slate-400 hover:text-white transition-colors">{label}</a>
            {/each}
            <a href="#contact" onclick={(e) => go(e, 'contact')} class="px-5 py-2 bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-semibold rounded-lg transition-colors">Kontakt</a>
        </div>
        <button onclick={() => (mobileMenuOpen = !mobileMenuOpen)} class="md:hidden text-white" aria-label="Menü">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" /></svg>
        </button>
    </div>
    {#if mobileMenuOpen}
        <div class="md:hidden bg-slate-900 border-t border-slate-800 px-6 py-4 space-y-3">
            {#each [...nav, ['contact', 'Kontakt']] as [id, label]}
                <a href={'#' + id} onclick={(e) => go(e, id)} class="block text-slate-300 hover:text-white">{label}</a>
            {/each}
        </div>
    {/if}
</nav>

<main class="bg-slate-950 text-white">
    <section id="home" class="hero relative min-h-screen flex items-center px-6 pt-16 overflow-hidden">
        <div class="grid-bg"></div>
        <div class="relative max-w-6xl mx-auto w-full grid md:grid-cols-2 gap-12 items-center">
            <div>
                <span class="inline-flex items-center gap-2 px-3 py-1 rounded-full border border-emerald-500/30 bg-emerald-500/10 text-emerald-300 text-sm mb-6 animate-fade-in">
                    <span class="w-2 h-2 rounded-full bg-emerald-400 pulse"></span> Werkstudent IT Infrastruktur
                </span>
                <h1 class="text-5xl md:text-6xl font-black leading-tight mb-6 animate-slide-up">
                    Hi, ich bin <span class="bg-gradient-to-r from-emerald-400 to-cyan-400 bg-clip-text text-transparent">Lin Yihang</span>
                </h1>
                <p class="text-lg md:text-xl text-slate-300 mb-10 animate-slide-up-delay">
                    Ich sorge dafür, dass Netzwerk, Clients und Produktions IT einfach laufen. Informatik Student an der FH Aachen.
                </p>
                <div class="flex flex-wrap gap-4 animate-fade-in-delay">
                    <button onclick={(e) => go(e, 'experience')} class="group font-mono text-sm px-5 py-2.5 rounded-md border border-emerald-500/40 bg-emerald-500/10 text-emerald-300 hover:bg-emerald-500/20 hover:border-emerald-400 transition-colors"><span class="text-emerald-500">$</span> cd ./erfahrung <span class="inline-block transition-transform group-hover:translate-x-1">→</span></button>
                    <button onclick={(e) => go(e, 'contact')} class="font-mono text-sm px-5 py-2.5 rounded-md border border-cyan-500/40 bg-cyan-500/10 text-cyan-300 hover:bg-cyan-500/20 hover:border-cyan-400 transition-colors"><span class="text-cyan-500">$</span> ./kontakt.sh</button>
                </div>
            </div>
            <div class="terminal animate-fade-in-delay hidden md:block">
                <div class="flex gap-2 px-4 py-3 border-b border-slate-800">
                    <span class="w-3 h-3 rounded-full bg-red-500/80"></span><span class="w-3 h-3 rounded-full bg-yellow-500/80"></span><span class="w-3 h-3 rounded-full bg-green-500/80"></span>
                </div>
                <pre class="p-5 text-sm leading-relaxed font-mono text-slate-300"><span class="text-emerald-400">yihang@infra</span>:~$ whoami
Werkstudent IT Infrastruktur
<span class="text-emerald-400">yihang@infra</span>:~$ show focus
 Netzwerk        <span class="text-cyan-400">VLAN · 802.1X · MAB · DHCP</span>
 Clients         <span class="text-cyan-400">Windows · Intune · Print</span>
 Produktions IT  <span class="text-cyan-400">MES · SAP · Maschinen</span>
<span class="text-emerald-400">yihang@infra</span>:~$ cat lernziel.txt
Cisco CCNA 200-301
<span class="text-emerald-400">yihang@infra</span>:~$ <span class="blink">▋</span></pre>
            </div>
        </div>
    </section>

    <section id="about" class="py-24 px-6">
        <div class="max-w-6xl mx-auto">
            <h2 class="section-title">Über mich</h2>
            <div class="terminal max-w-4xl mx-auto mb-12">
                <div class="flex items-center gap-2 px-4 py-3 border-b border-slate-800">
                    <span class="w-3 h-3 rounded-full bg-red-500/80"></span><span class="w-3 h-3 rounded-full bg-yellow-500/80"></span><span class="w-3 h-3 rounded-full bg-green-500/80"></span>
                    <span class="ml-3 text-xs font-mono text-slate-500">about.txt</span>
                </div>
                <div class="p-6 font-mono text-sm md:text-base leading-relaxed text-slate-300">
                    <p class="mb-3"><span class="text-emerald-400">yihang@infra</span>:~$ cat about.txt</p>
                    <p>Angefangen habe ich mit <span class="text-cyan-400">Webentwicklung</span>, gelandet bin ich in der <span class="text-emerald-400">Infrastruktur</span>.
                    Heute arbeite ich als Werkstudent in der IT Infrastruktur eines international tätigen Unternehmens der Kunststoff- und Chemiebranche
                    und kümmere mich um alles zwischen <span class="text-emerald-400">Switchport</span>, <span class="text-cyan-400">Endgerät</span> und <span class="text-amber-400">Maschine</span>.</p>
                    <p class="mt-3 text-slate-400"># Ziel: Systeme verstehen, sauber dokumentieren, wiederkehrende Arbeit automatisieren.</p>
                </div>
            </div>
            <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
                {#each focus as f}
                    <div class="terminal hover:-translate-y-1 transition-transform">
                        <div class="flex items-center gap-1.5 px-3 py-2.5 border-b border-slate-800">
                            <span class="w-2.5 h-2.5 rounded-full bg-red-500/80"></span><span class="w-2.5 h-2.5 rounded-full bg-yellow-500/80"></span><span class="w-2.5 h-2.5 rounded-full bg-green-500/80"></span>
                            <span class="ml-2 text-xs font-mono text-slate-500">{f.file}</span>
                        </div>
                        <ul class="p-4 font-mono text-sm space-y-1.5">
                            {#each f.items as it}
                                <li class="text-slate-300"><span class={f.color}>▸</span> {it}</li>
                            {/each}
                        </ul>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <section id="experience" class="py-24 px-6 bg-slate-900/40">
        <div class="max-w-4xl mx-auto">
            <h2 class="section-title">Erfahrung</h2>
            <ol class="relative border-l border-slate-700 ml-3 space-y-12">
                {#each timeline as t}
                    <li class="pl-8 relative">
                        <span class="absolute -left-[9px] top-1.5 w-4 h-4 rounded-full bg-emerald-400 ring-4 ring-slate-950"></span>
                        <span class="text-xs font-mono uppercase tracking-wider text-emerald-400">{t.when}</span>
                        <h3 class="text-2xl font-bold mt-1">{t.title}</h3>
                        <p class="text-slate-400 mb-4">{t.where}</p>
                        <ul class="space-y-2">
                            {#each t.points as p}
                                <li class="flex gap-3 text-slate-300"><span class="text-emerald-400">▸</span>{p}</li>
                            {/each}
                        </ul>
                    </li>
                {/each}
            </ol>
        </div>
    </section>

    <section id="skills" class="py-24 px-6 overflow-hidden">
        <div class="max-w-6xl mx-auto">
            <h2 class="section-title">Technologien</h2>
            <div class="space-y-6">
                {#each skillRows as row, i}
                    <div class="carousel-container">
                        <div class="carousel-track {i % 2 ? 'animate-scroll-left' : 'animate-scroll-right'}">
                            {#each [...row, ...row] as s}
                                <div class="skill group">
                                    {#if s.img}
                                        <img src={s.img} alt={s.name} class="w-12 h-12 object-contain group-hover:scale-110 transition-transform" loading="lazy" onerror={(e) => ((e.currentTarget as HTMLImageElement).style.visibility = 'hidden')} />
                                    {:else}
                                        <div class="w-12 h-12 rounded-lg bg-emerald-500/15 border border-emerald-500/30 flex items-center justify-center font-mono font-bold text-[11px] text-emerald-300 group-hover:scale-110 transition-transform">{s.short}</div>
                                    {/if}
                                    <span class="text-xs text-slate-400 group-hover:text-white mt-2">{s.name}</span>
                                </div>
                            {/each}
                        </div>
                    </div>
                {/each}
            </div>
            <div class="flex flex-wrap justify-center gap-2 mt-12">
                {#each ['VLAN', '802.1X', 'MAB', 'RADIUS', 'DHCP', 'DNS', 'Active Directory', 'GPO', 'VMware ESXi', 'Intune', 'PRTG', 'GFOS', 'VoIP', 'OPC UA', 'SAP', 'MES'] as tag}
                    <span class="tag">{tag}</span>
                {/each}
            </div>
        </div>
    </section>

    <section id="projects" class="py-24 px-6 bg-slate-900/40">
        <div class="max-w-6xl mx-auto">
            <h2 class="section-title">Projekte</h2>
            <div class="grid md:grid-cols-2 gap-8">
                {#each projects as p}
                    <div class="card hover:-translate-y-1">
                        <div class="flex items-center gap-4 mb-4"><span class="text-4xl">{p.icon}</span><h3 class="text-2xl font-bold">{p.title}</h3></div>
                        <p class="text-slate-300 mb-6">{p.text}</p>
                        <div class="flex flex-wrap gap-2">{#each p.tags as t}<span class="tag">{t}</span>{/each}</div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <section id="contact" class="py-24 px-6">
        <div class="max-w-4xl mx-auto text-center">
            <h2 class="section-title">Kontakt</h2>
            <p class="text-slate-400 -mt-8 mb-12">Fragen, Austausch oder ein spannendes Infrastruktur Thema? Schreib mir.</p>
            <div class="grid md:grid-cols-3 gap-6">
                <a href="https://www.linkedin.com/in/lin-yihang/" target="_blank" rel="noopener noreferrer" class="card group"><div class="text-4xl mb-3 group-hover:scale-110 transition-transform">💼</div><h3 class="font-bold">LinkedIn</h3></a>
                <a href="https://github.com/YakuzaSan" target="_blank" rel="noopener noreferrer" class="card group"><div class="text-4xl mb-3 group-hover:scale-110 transition-transform">🐙</div><h3 class="font-bold">GitHub</h3></a>
                <a href="mailto:lin.yihang@outlook.de" class="card group"><div class="text-4xl mb-3 group-hover:scale-110 transition-transform">✉️</div><h3 class="font-bold">E-Mail</h3></a>
            </div>
        </div>
    </section>

    <footer class="border-t border-slate-800 py-8 px-6 text-center text-slate-500 text-sm">
        © {new Date().getFullYear()} Lin Yihang · <a href="/policy" class="hover:text-white">Datenschutz</a>
    </footer>
</main>

<style>
    :global(html) { scroll-behavior: smooth; }
    :global(body) { overflow-x: hidden; background: #020617; }
    .section-title { @apply text-4xl md:text-5xl font-black mb-12 text-center; }
    .card { @apply block bg-slate-900/70 border border-slate-800 rounded-xl p-6 transition-all hover:border-emerald-500/50 hover:bg-slate-800/50; }
    .tag { @apply px-3 py-1 bg-emerald-500/10 text-emerald-300 rounded-md text-sm border border-emerald-500/25 font-mono; }
    .skill { @apply bg-slate-900 border border-slate-800 rounded-xl p-5 flex flex-col items-center min-w-[120px] hover:border-emerald-500/50 transition-all; }
    .terminal { @apply bg-slate-900/80 border border-slate-800 rounded-xl shadow-2xl shadow-emerald-500/10; }
    .grid-bg {
        position: absolute; inset: 0;
        background-image: linear-gradient(rgb(52 211 153 / 0.06) 1px, transparent 1px), linear-gradient(90deg, rgb(52 211 153 / 0.06) 1px, transparent 1px);
        background-size: 48px 48px;
        mask-image: radial-gradient(ellipse at center, black 30%, transparent 75%);
    }
    .carousel-container { position: relative; overflow: hidden; mask-image: linear-gradient(90deg, transparent, black 10%, black 90%, transparent); }
    .carousel-track { @apply flex gap-6 w-max; }
    @keyframes scrollR { to { transform: translateX(-50%); } }
    @keyframes scrollL { from { transform: translateX(-50%); } to { transform: translateX(0); } }
    .animate-scroll-right { animation: scrollR 35s linear infinite; }
    .animate-scroll-left { animation: scrollL 35s linear infinite; }
    .carousel-track:hover { animation-play-state: paused; }
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    @keyframes slideUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: none; } }
    @keyframes blink { 50% { opacity: 0; } }
    @keyframes pulse { 50% { opacity: 0.4; } }
    .blink { animation: blink 1s step-end infinite; }
    .pulse { animation: pulse 2s ease-in-out infinite; }
    .animate-fade-in { animation: fadeIn 1s ease-out; }
    .animate-fade-in-delay { animation: fadeIn 1s ease-out 0.4s both; }
    .animate-slide-up { animation: slideUp 0.8s ease-out 0.2s both; }
    .animate-slide-up-delay { animation: slideUp 0.8s ease-out 0.4s both; }
    @media (prefers-reduced-motion: reduce) { .carousel-track, .blink, .pulse { animation: none; } }
</style>
'@
[IO.File]::WriteAllText("$PWD\src\routes\+page.svelte", $c, (New-Object System.Text.UTF8Encoding $false)); git status --short; npm.cmd run dev