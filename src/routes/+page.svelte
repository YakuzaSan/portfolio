<script lang="ts">
    import { dev } from '$app/environment';
    import { inject } from '@vercel/analytics';
    inject({ mode: dev ? 'development' : 'production' });

    // Skills Data - Using official icons from CDNs
    const skills = {
        frontend: [
            { name: 'TypeScript', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg' },
            { name: 'React', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg' },
            { name: 'Svelte', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/svelte/svelte-original.svg' },
            { name: 'Next.js', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg' },
            { name: 'Tailwind CSS', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-original.svg' },
            { name: 'HTML', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg' },
            { name: 'CSS', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg' }
        ],
        backend: [
            { name: 'JavaScript', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg' },
            { name: 'Node.js', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg' },
            { name: 'PHP', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg' },
            { name: 'C#', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg' }
        ],
        database: [
            { name: 'MongoDB', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg' },
            { name: 'MySQL', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg' },
            { name: 'SQL Server', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/microsoftsqlserver/microsoftsqlserver-plain.svg' }
        ],
        devops: [
            { name: 'Vercel', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vercel/vercel-original.svg' },
            { name: 'GitHub', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg' },
            { name: 'Apache', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/apache/apache-original.svg' },
            { name: 'Git', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg' }
        ],
        tools: [
            { name: 'VS Code', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg' },
            { name: 'IntelliJ', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/intellij/intellij-original.svg' },
            { name: 'Visual Studio', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/visualstudio/visualstudio-plain.svg' }
        ]
    };

    let activeSection = $state('home');
    let mobileMenuOpen = $state(false);

    function scrollToSection(id: string) {
        const element = document.getElementById(id);
        if (element) {
            element.scrollIntoView({ behavior: 'smooth' });
            mobileMenuOpen = false;
        }
    }
</script>

<svelte:head>
    <title>Lin Yihang - Full Stack Developer</title>
    <meta name="description" content="Lin Yihang - Informatik Student & Full Stack Developer. Spezialisiert auf Server, Cloud & Web Development.">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Lin Yihang - Full Stack Developer">
    <meta property="og:type" content="website">
    <meta property="og:title" content="Lin Yihang - Full Stack Developer">
    <meta property="og:url" content="https://lin-yihang.de">
</svelte:head>

<!-- Navigation -->
<nav class="fixed top-0 left-0 right-0 z-50 bg-slate-950/80 backdrop-blur-lg border-b border-slate-800">
    <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="flex items-center justify-between h-16">
            <a href="#home" onclick={(e) => { e.preventDefault(); scrollToSection('home'); }} class="text-xl font-bold bg-gradient-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent">
                Lin Yihang
            </a>

            <!-- Desktop Menu -->
            <div class="hidden md:flex items-center gap-8">
                <a href="#about" onclick={(e) => { e.preventDefault(); scrollToSection('about'); }} class="text-slate-300 hover:text-white transition-colors">Über mich</a>
                <a href="#skills" onclick={(e) => { e.preventDefault(); scrollToSection('skills'); }} class="text-slate-300 hover:text-white transition-colors">Skills</a>
                <a href="#projects" onclick={(e) => { e.preventDefault(); scrollToSection('projects'); }} class="text-slate-300 hover:text-white transition-colors">Projekte</a>
                <a href="#contact" onclick={(e) => { e.preventDefault(); scrollToSection('contact'); }} class="px-6 py-2 bg-blue-600 hover:bg-blue-700 rounded-lg transition-colors">Kontakt</a>
            </div>

            <!-- Mobile Menu Button -->
            <button onclick={() => mobileMenuOpen = !mobileMenuOpen} class="md:hidden text-white" aria-label="Toggle mobile menu">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                </svg>
            </button>
        </div>
    </div>

    <!-- Mobile Menu -->
    {#if mobileMenuOpen}
        <div class="md:hidden bg-slate-900 border-t border-slate-800">
            <div class="px-6 py-4 space-y-3">
                <a href="#about" onclick={(e) => { e.preventDefault(); scrollToSection('about'); }} class="block text-slate-300 hover:text-white">Über mich</a>
                <a href="#skills" onclick={(e) => { e.preventDefault(); scrollToSection('skills'); }} class="block text-slate-300 hover:text-white">Skills</a>
                <a href="#projects" onclick={(e) => { e.preventDefault(); scrollToSection('projects'); }} class="block text-slate-300 hover:text-white">Projekte</a>
                <a href="#contact" onclick={(e) => { e.preventDefault(); scrollToSection('contact'); }} class="block text-slate-300 hover:text-white">Kontakt</a>
            </div>
        </div>
    {/if}
</nav>

<main class="bg-slate-950 text-white">
    <!-- Hero Section -->
    <section id="home" class="min-h-screen flex items-center justify-center px-6 pt-16">
        <div class="max-w-4xl text-center">
            <div class="mb-8 animate-fade-in">
                <span class="inline-block px-4 py-2 bg-blue-500/10 border border-blue-500/30 rounded-full text-blue-400 text-sm font-medium">
                    👋 Willkommen auf meinem Portfolio
                </span>
            </div>
            <h1 class="text-5xl md:text-7xl font-black mb-6 animate-slide-up">
                Hi, ich bin <span class="bg-gradient-to-r from-blue-400 via-cyan-400 to-blue-400 bg-clip-text text-transparent">Lin Yihang</span>
            </h1>
            <p class="text-xl md:text-2xl text-slate-300 mb-12 animate-slide-up-delay">
                Full Stack Developer & Informatik Student aus Deutschland
            </p>
            <div class="flex flex-wrap justify-center gap-4 animate-fade-in-delay">
                <button onclick={() => scrollToSection('projects')} class="px-8 py-3 bg-blue-600 hover:bg-blue-700 rounded-lg font-semibold transition-all hover:scale-105">
                    Meine Projekte
                </button>
                <button onclick={() => scrollToSection('contact')} class="px-8 py-3 border border-slate-600 hover:border-blue-400 rounded-lg font-semibold transition-all hover:scale-105">
                    Kontakt aufnehmen
                </button>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-24 px-6">
        <div class="max-w-6xl mx-auto">
            <h2 class="text-4xl md:text-5xl font-black mb-12 text-center">Über mich</h2>
            <div class="grid md:grid-cols-2 gap-12">
                <div class="space-y-6 text-lg text-slate-300">
                    <p>
                        Ich bin <span class="text-blue-400 font-semibold">Lin Yihang</span>, 23 Jahre alt und studiere Informatik in Deutschland.
                        Meine Leidenschaft für Technologie begann früh und hat mich dazu gebracht, mich intensiv mit
                        Full Stack Development, Server-Infrastruktur und Cloud-Technologien auseinanderzusetzen.
                    </p>
                    <p>
                        Seit 2023 entwickle ich professionelle Web-Anwendungen und habe umfangreiche Erfahrung mit
                        modernen Technologie-Stacks gesammelt. Mein Fokus liegt auf sauberer Code-Architektur,
                        Skalierbarkeit und benutzerfreundlichen Interfaces.
                    </p>
                </div>
                <div class="bg-slate-900 border border-slate-800 rounded-xl p-8">
                    <h3 class="text-2xl font-bold mb-6 text-blue-400">Was ich mache</h3>
                    <ul class="space-y-4">
                        <li class="flex items-start gap-3">
                            <span class="text-blue-400 text-xl">✓</span>
                            <span class="text-slate-300">Full Stack Web Development</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <span class="text-blue-400 text-xl">✓</span>
                            <span class="text-slate-300">Server & Cloud Infrastruktur</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <span class="text-blue-400 text-xl">✓</span>
                            <span class="text-slate-300">Moderne Frontend Frameworks</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <span class="text-blue-400 text-xl">✓</span>
                            <span class="text-slate-300">Backend & Datenbank Design</span>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="py-24 px-6 bg-slate-900/50 overflow-hidden">
        <div class="max-w-7xl mx-auto">
            <h2 class="text-4xl md:text-5xl font-black mb-4 text-center">Technologien & Skills</h2>
            <p class="text-slate-400 text-center mb-16">Die Tools und Technologien, mit denen ich arbeite</p>

            <div class="space-y-8">
                <!-- Row 1 - Scrolling Right -->
                <div class="carousel-container">
                    <div class="carousel-track animate-scroll-right">
                        {#each [...skills.frontend, ...skills.frontend] as skill}
                            <div class="skill-card-carousel group">
                                <img src={skill.img} alt={skill.name} class="w-16 h-16 object-contain group-hover:scale-110 transition-transform" />
                                <span class="text-sm text-slate-400 group-hover:text-white transition-colors mt-2">{skill.name}</span>
                            </div>
                        {/each}
                    </div>
                </div>

                <!-- Row 2 - Scrolling Left -->
                <div class="carousel-container">
                    <div class="carousel-track animate-scroll-left">
                        {#each [...skills.backend, ...skills.database, ...skills.backend, ...skills.database] as skill}
                            <div class="skill-card-carousel group">
                                <img src={skill.img} alt={skill.name} class="w-16 h-16 object-contain group-hover:scale-110 transition-transform" />
                                <span class="text-sm text-slate-400 group-hover:text-white transition-colors mt-2">{skill.name}</span>
                            </div>
                        {/each}
                    </div>
                </div>

                <!-- Row 3 - Scrolling Right -->
                <div class="carousel-container">
                    <div class="carousel-track animate-scroll-right">
                        {#each [...skills.devops, ...skills.tools, ...skills.devops, ...skills.tools] as skill}
                            <div class="skill-card-carousel group">
                                <img src={skill.img} alt={skill.name} class="w-16 h-16 object-contain group-hover:scale-110 transition-transform" />
                                <span class="text-sm text-slate-400 group-hover:text-white transition-colors mt-2">{skill.name}</span>
                            </div>
                        {/each}
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="py-24 px-6">
        <div class="max-w-6xl mx-auto">
            <h2 class="text-4xl md:text-5xl font-black mb-4 text-center">Projekte</h2>
            <p class="text-slate-400 text-center mb-16">Eine Auswahl meiner Arbeiten</p>

            <div class="grid md:grid-cols-2 gap-8">
                <div class="project-card group">
                    <div class="flex items-center gap-4 mb-4">
                        <span class="text-4xl">🖥️</span>
                        <h3 class="text-2xl font-bold">Server Infrastruktur</h3>
                    </div>
                    <p class="text-slate-300 mb-6">
                        Aufbau und Verwaltung von eigenen Server-Infrastrukturen mit Linux, Docker und modernen DevOps-Praktiken.
                    </p>
                    <div class="flex flex-wrap gap-2">
                        <span class="tech-tag">Linux</span>
                        <span class="tech-tag">Docker</span>
                        <span class="tech-tag">DevOps</span>
                        <span class="tech-tag">Apache</span>
                    </div>
                </div>

                <div class="project-card group">
                    <div class="flex items-center gap-4 mb-4">
                        <span class="text-4xl">☁️</span>
                        <h3 class="text-2xl font-bold">Cloud Solutions</h3>
                    </div>
                    <p class="text-slate-300 mb-6">
                        Deployment und Verwaltung von Cloud-Anwendungen mit modernen Plattformen und Skalierungslösungen.
                    </p>
                    <div class="flex flex-wrap gap-2">
                        <span class="tech-tag">Vercel</span>
                        <span class="tech-tag">AWS</span>
                        <span class="tech-tag">Cloud</span>
                        <span class="tech-tag">CI/CD</span>
                    </div>
                </div>

                <div class="project-card group">
                    <div class="flex items-center gap-4 mb-4">
                        <span class="text-4xl">🌐</span>
                        <h3 class="text-2xl font-bold">Web Applications</h3>
                    </div>
                    <p class="text-slate-300 mb-6">
                        Entwicklung moderner, responsiver Web-Anwendungen mit aktuellen Frameworks und Best Practices.
                    </p>
                    <div class="flex flex-wrap gap-2">
                        <span class="tech-tag">Svelte</span>
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">TypeScript</span>
                        <span class="tech-tag">Tailwind</span>
                    </div>
                </div>

                <div class="project-card group">
                    <div class="flex items-center gap-4 mb-4">
                        <span class="text-4xl">🗄️</span>
                        <h3 class="text-2xl font-bold">Backend & Datenbanken</h3>
                    </div>
                    <p class="text-slate-300 mb-6">
                        Robuste Backend-Systeme und Datenbankarchitekturen für skalierbare Anwendungen.
                    </p>
                    <div class="flex flex-wrap gap-2">
                        <span class="tech-tag">Node.js</span>
                        <span class="tech-tag">MongoDB</span>
                        <span class="tech-tag">MySQL</span>
                        <span class="tech-tag">API Design</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-24 px-6 bg-slate-900/50">
        <div class="max-w-4xl mx-auto text-center">
            <h2 class="text-4xl md:text-5xl font-black mb-4">Lass uns zusammenarbeiten</h2>
            <p class="text-slate-400 mb-12">Hast du ein Projekt im Kopf? Kontaktiere mich!</p>

            <div class="grid md:grid-cols-3 gap-6">
                <a href="https://www.linkedin.com/in/lin-yihang/" target="_blank" rel="noopener noreferrer" class="contact-card group">
                    <div class="text-5xl mb-4 group-hover:scale-110 transition-transform">💼</div>
                    <h3 class="text-xl font-bold mb-2">LinkedIn</h3>
                    <p class="text-slate-400 text-sm">Professionelles Netzwerk</p>
                </a>

                <a href="https://github.com/YakuzaSan" target="_blank" rel="noopener noreferrer" class="contact-card group">
                    <div class="text-5xl mb-4 group-hover:scale-110 transition-transform">🐙</div>
                    <h3 class="text-xl font-bold mb-2">GitHub</h3>
                    <p class="text-slate-400 text-sm">Meine Open Source Projekte</p>
                </a>

                <a href="mailto:contact@lin-yihang.de" class="contact-card group">
                    <div class="text-5xl mb-4 group-hover:scale-110 transition-transform">✉️</div>
                    <h3 class="text-xl font-bold mb-2">Email</h3>
                    <p class="text-slate-400 text-sm">Direkter Kontakt</p>
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="border-t border-slate-800 py-8 px-6 text-center text-slate-400">
        <p>© 2024 Lin Yihang. Made with ❤️ using SvelteKit & Tailwind CSS</p>
    </footer>
</main>

<style>
    :global(html) {
        scroll-behavior: smooth;
    }

    :global(body) {
        overflow-x: hidden;
    }

    .carousel-container {
        position: relative;
        width: 100%;
        overflow: hidden;
    }

    .carousel-container::before,
    .carousel-container::after {
        content: '';
        position: absolute;
        top: 0;
        bottom: 0;
        width: 100px;
        z-index: 10;
        pointer-events: none;
    }

    .carousel-container::before {
        left: 0;
        background: linear-gradient(to right, rgb(15 23 42 / 0.5), transparent);
    }

    .carousel-container::after {
        right: 0;
        background: linear-gradient(to left, rgb(15 23 42 / 0.5), transparent);
    }

    .carousel-track {
        @apply flex gap-8 w-max;
    }

    .skill-card-carousel {
        @apply bg-slate-900 border border-slate-800 rounded-xl p-6 flex flex-col items-center justify-center text-center hover:border-blue-500/50 hover:bg-slate-800/50 transition-all cursor-pointer min-w-[140px];
    }

    .project-card {
        @apply bg-slate-900 border border-slate-800 rounded-xl p-8 hover:border-blue-500/50 hover:bg-slate-800/50 transition-all hover:-translate-y-2;
    }

    .contact-card {
        @apply bg-slate-900 border border-slate-800 rounded-xl p-8 hover:border-blue-500/50 hover:bg-slate-800/50 transition-all hover:-translate-y-2;
    }

    .tech-tag {
        @apply px-3 py-1 bg-blue-500/20 text-blue-300 rounded-lg text-sm border border-blue-500/30;
    }

    @keyframes fadeIn {
        from { opacity: 0; }
        to { opacity: 1; }
    }

    @keyframes slideUp {
        from {
            opacity: 0;
            transform: translateY(30px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    @keyframes scrollRight {
        from {
            transform: translateX(0);
        }
        to {
            transform: translateX(-50%);
        }
    }

    @keyframes scrollLeft {
        from {
            transform: translateX(-50%);
        }
        to {
            transform: translateX(0);
        }
    }

    .animate-scroll-right {
        animation: scrollRight 30s linear infinite;
    }

    .animate-scroll-right:hover {
        animation-play-state: paused;
    }

    .animate-scroll-left {
        animation: scrollLeft 30s linear infinite;
    }

    .animate-scroll-left:hover {
        animation-play-state: paused;
    }

    .animate-fade-in {
        animation: fadeIn 1s ease-out;
    }

    .animate-fade-in-delay {
        animation: fadeIn 1s ease-out 0.4s both;
    }

    .animate-slide-up {
        animation: slideUp 0.8s ease-out 0.2s both;
    }

    .animate-slide-up-delay {
        animation: slideUp 0.8s ease-out 0.4s both;
    }
</style>








