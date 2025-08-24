<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Galuh Meibinar Keinaryosih - Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
        
        * {
            font-family: 'Poppins', sans-serif;
        }
        
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }
        
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        .slide-in-left {
            opacity: 0;
            transform: translateX(-50px);
            transition: all 0.8s ease;
        }
        
        .slide-in-left.visible {
            opacity: 1;
            transform: translateX(0);
        }
        
        .slide-in-right {
            opacity: 0;
            transform: translateX(50px);
            transition: all 0.8s ease;
        }
        
        .slide-in-right.visible {
            opacity: 1;
            transform: translateX(0);
        }
        
        .scale-in {
            opacity: 0;
            transform: scale(0.8);
            transition: all 0.8s ease;
        }
        
        .scale-in.visible {
            opacity: 1;
            transform: scale(1);
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        
        .card-hover {
            transition: all 0.3s ease;
        }
        
        .card-hover:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }
        
        .btn-hover {
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .btn-hover::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }
        
        .btn-hover:hover::before {
            left: 100%;
        }
        
        .floating {
            animation: floating 3s ease-in-out infinite;
        }
        
        @keyframes floating {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }
        
        .typing {
            overflow: hidden;
            border-right: 3px solid #667eea;
            white-space: nowrap;
            animation: typing 3s steps(40, end), blink-caret 0.75s step-end infinite;
        }
        
        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent; }
            50% { border-color: #667eea; }
        }
        
        .skill-bar {
            width: 0%;
            transition: width 2s ease-in-out;
        }
        
        .skill-bar.animate {
            width: 90%;
        }
        
        .portfolio-item {
            position: relative;
            overflow: hidden;
            border-radius: 15px;
        }
        
        .portfolio-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.9), rgba(118, 75, 162, 0.9));
            opacity: 0;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }
        
        .nav-link {
            position: relative;
            transition: all 0.3s ease;
        }
        
        .nav-link::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 50%;
            background: #667eea;
            transition: all 0.3s ease;
        }
        
        .nav-link:hover::after {
            width: 100%;
            left: 0;
        }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Navigation -->
    <nav class="fixed top-0 w-full bg-white/90 backdrop-blur-md z-50 shadow-lg">
        <div class="container mx-auto px-6 py-4">
            <div class="flex justify-between items-center">
                <div class="text-2xl font-bold gradient-bg bg-clip-text text-transparent">
                    Galuh Portfolio
                </div>
                <div class="hidden md:flex space-x-8">
                    <a href="#home" class="nav-link text-gray-700 hover:text-purple-600 font-medium">Home</a>
                    <a href="#about" class="nav-link text-gray-700 hover:text-purple-600 font-medium">About</a>
                    <a href="#skills" class="nav-link text-gray-700 hover:text-purple-600 font-medium">Skills</a>
                    <a href="#portfolio" class="nav-link text-gray-700 hover:text-purple-600 font-medium">Portfolio</a>
                    <a href="#contact" class="nav-link text-gray-700 hover:text-purple-600 font-medium">Contact</a>
                </div>
                <button id="mobile-menu-btn" class="md:hidden text-gray-700">
                    <i class="fas fa-bars text-xl"></i>
                </button>
            </div>
            <div id="mobile-menu" class="hidden md:hidden mt-4 pb-4">
                <a href="#home" class="block py-2 text-gray-700 hover:text-purple-600">Home</a>
                <a href="#about" class="block py-2 text-gray-700 hover:text-purple-600">About</a>
                <a href="#skills" class="block py-2 text-gray-700 hover:text-purple-600">Skills</a>
                <a href="#portfolio" class="block py-2 text-gray-700 hover:text-purple-600">Portfolio</a>
                <a href="#contact" class="block py-2 text-gray-700 hover:text-purple-600">Contact</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="min-h-screen gradient-bg flex items-center justify-center pt-20">
        <div class="container mx-auto px-6">
            <div class="flex flex-col lg:flex-row items-center justify-between">
                <div class="lg:w-1/2 text-white mb-10 lg:mb-0">
                    <h1 class="text-5xl lg:text-7xl font-bold mb-6 fade-in">
                        Halo! Saya
                        <span class="block typing">Galuh Meibinar</span>
                    </h1>
                    <p class="text-xl lg:text-2xl mb-8 fade-in opacity-90">
                        Siswa SMAN 1 Saradan | Digital Creative Enthusiast
                    </p>
                    <div class="flex flex-col sm:flex-row gap-4 fade-in">
                        <button onclick="scrollToSection('portfolio')" class="btn-hover bg-white text-purple-600 px-8 py-4 rounded-full font-semibold hover:bg-gray-100 transition-all">
                            Lihat Portfolio
                        </button>
                        <button onclick="scrollToSection('contact')" class="btn-hover border-2 border-white text-white px-8 py-4 rounded-full font-semibold hover:bg-white hover:text-purple-600 transition-all">
                            Hubungi Saya
                        </button>
                    </div>
                </div>
                <div class="lg:w-1/2 flex justify-center">
                    <div class="floating">
                        <img src="https://freeimage.host/i/Fyncenf" alt="Galuh Meibinar Keinaryosih" 
                             class="w-80 h-80 lg:w-96 lg:h-96 rounded-full object-cover shadow-2xl border-8 border-white/20 scale-in"
                             onerror="this.src=''; this.alt='Foto profil tidak dapat dimuat'; this.style.display='none';">
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20 bg-white">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16">
                <h2 class="text-4xl lg:text-5xl font-bold text-gray-800 mb-4 fade-in">Tentang Saya</h2>
                <div class="w-24 h-1 gradient-bg mx-auto fade-in"></div>
            </div>
            
            <div class="grid lg:grid-cols-2 gap-12 items-center">
                <div class="slide-in-left">
                    <h3 class="text-3xl font-bold text-gray-800 mb-6">Kenalan Lebih Dekat</h3>
                    <div class="space-y-4 text-lg text-gray-600">
                        <div class="flex items-center">
                            <i class="fas fa-user text-purple-600 w-6 mr-4"></i>
                            <span><strong>Nama:</strong> Galuh Meibinar Keinaryosih</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-graduation-cap text-purple-600 w-6 mr-4"></i>
                            <span><strong>Kelas:</strong> XI A</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-school text-purple-600 w-6 mr-4"></i>
                            <span><strong>Sekolah:</strong> SMAN 1 Saradan</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-heart text-purple-600 w-6 mr-4"></i>
                            <span><strong>Hobi:</strong> Traveling</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-certificate text-purple-600 w-6 mr-4"></i>
                            <span><strong>Program:</strong> Digital Skill</span>
                        </div>
                    </div>
                    <p class="mt-6 text-gray-600 leading-relaxed">
                        Saya adalah siswa yang passionate dalam bidang digital creative. Melalui program Digital Skill, 
                        saya terus mengembangkan kemampuan dalam berbagai aspek kreatif digital dan selalu antusias 
                        untuk belajar hal-hal baru.
                    </p>
                </div>
                
                <div class="slide-in-right">
                    <div class="bg-gradient-to-br from-purple-100 to-blue-100 p-8 rounded-2xl">
                        <h4 class="text-2xl font-bold text-gray-800 mb-6">Passion & Goals</h4>
                        <div class="space-y-4">
                            <div class="flex items-center">
                                <div class="w-4 h-4 gradient-bg rounded-full mr-4"></div>
                                <span class="text-gray-700">Mengembangkan kreativitas digital</span>
                            </div>
                            <div class="flex items-center">
                                <div class="w-4 h-4 gradient-bg rounded-full mr-4"></div>
                                <span class="text-gray-700">Belajar teknologi terbaru</span>
                            </div>
                            <div class="flex items-center">
                                <div class="w-4 h-4 gradient-bg rounded-full mr-4"></div>
                                <span class="text-gray-700">Berbagi pengetahuan dengan teman</span>
                            </div>
                            <div class="flex items-center">
                                <div class="w-4 h-4 gradient-bg rounded-full mr-4"></div>
                                <span class="text-gray-700">Menjadi digital creative professional</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="py-20 bg-gray-50">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16">
                <h2 class="text-4xl lg:text-5xl font-bold text-gray-800 mb-4 fade-in">Keahlian Saya</h2>
                <div class="w-24 h-1 gradient-bg mx-auto fade-in"></div>
                <p class="text-xl text-gray-600 mt-6 fade-in">Berikut adalah skill yang saya kuasai</p>
            </div>
            
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div class="card-hover bg-white p-8 rounded-2xl shadow-lg text-center scale-in">
                    <div class="w-20 h-20 gradient-bg rounded-full flex items-center justify-center mx-auto mb-6">
                        <i class="fas fa-code text-white text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold text-gray-800 mb-4">Website Development</h3>
                    <p class="text-gray-600 mb-4">Membuat website yang menarik dan fungsional</p>
                    <div class="bg-gray-200 rounded-full h-2 mb-2">
                        <div class="skill-bar bg-gradient-to-r from-purple-500 to-blue-500 h-2 rounded-full"></div>
                    </div>
                    <span class="text-sm text-gray-500">90%</span>
                </div>
                
                <div class="card-hover bg-white p-8 rounded-2xl shadow-lg text-center scale-in">
                    <div class="w-20 h-20 gradient-bg rounded-full flex items-center justify-center mx-auto mb-6">
                        <i class="fas fa-video text-white text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold text-gray-800 mb-4">Video Promosi</h3>
                    <p class="text-gray-600 mb-4">Membuat video promosi yang engaging dan profesional</p>
                    <div class="bg-gray-200 rounded-full h-2 mb-2">
                        <div class="skill-bar bg-gradient-to-r from-purple-500 to-blue-500 h-2 rounded-full"></div>
                    </div>
                    <span class="text-sm text-gray-500">90%</span>
                </div>
                
                <div class="card-hover bg-white p-8 rounded-2xl shadow-lg text-center scale-in">
                    <div class="w-20 h-20 gradient-bg rounded-full flex items-center justify-center mx-auto mb-6">
                        <i class="fas fa-palette text-white text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold text-gray-800 mb-4">Poster Design</h3>
                    <p class="text-gray-600 mb-4">Mendesain poster yang eye-catching dan informatif</p>
                    <div class="bg-gray-200 rounded-full h-2 mb-2">
                        <div class="skill-bar bg-gradient-to-r from-purple-500 to-blue-500 h-2 rounded-full"></div>
                    </div>
                    <span class="text-sm text-gray-500">90%</span>
                </div>
                
                <div class="card-hover bg-white p-8 rounded-2xl shadow-lg text-center scale-in">
                    <div class="w-20 h-20 gradient-bg rounded-full flex items-center justify-center mx-auto mb-6">
                        <i class="fas fa-camera text-white text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold text-gray-800 mb-4">Fotografi</h3>
                    <p class="text-gray-600 mb-4">Mengabadikan momen dengan komposisi yang indah</p>
                    <div class="bg-gray-200 rounded-full h-2 mb-2">
                        <div class="skill-bar bg-gradient-to-r from-purple-500 to-blue-500 h-2 rounded-full"></div>
                    </div>
                    <span class="text-sm text-gray-500">90%</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio" class="py-20 bg-white">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16">
                <h2 class="text-4xl lg:text-5xl font-bold text-gray-800 mb-4 fade-in">Portfolio Karya</h2>
                <div class="w-24 h-1 gradient-bg mx-auto fade-in"></div>
                <p class="text-xl text-gray-600 mt-6 fade-in">Beberapa karya terbaik saya</p>
            </div>
            
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div class="portfolio-item card-hover scale-in">
                    <img src="https://freeimage.host/i/FynMHCu" alt="Karya Portfolio 1" 
                         class="w-full h-64 object-cover"
                         onerror="this.src=''; this.alt='Karya tidak dapat dimuat'; this.parentElement.style.display='none';">
                    <div class="portfolio-overlay">
                        <div class="text-center text-white">
                            <h3 class="text-xl font-bold mb-2">Project Creative</h3>
                            <p class="mb-4">Salah satu karya kreatif terbaik</p>
                            <button class="bg-white text-purple-600 px-6 py-2 rounded-full font-semibold hover:bg-gray-100 transition-all">
                                Lihat Detail
                            </button>
                        </div>
                    </div>
                </div>
                
                <div class="portfolio-item card-hover scale-in">
                    <img src="https://freeimage.host/i/FynGyQe" alt="Karya Portfolio 2" 
                         class="w-full h-64 object-cover"
                         onerror="this.src=''; this.alt='Karya tidak dapat dimuat'; this.parentElement.style.display='none';">
                    <div class="portfolio-overlay">
                        <div class="text-center text-white">
                            <h3 class="text-xl font-bold mb-2">Digital Design</h3>
                            <p class="mb-4">Desain digital yang menarik</p>
                            <button class="bg-white text-purple-600 px-6 py-2 rounded-full font-semibold hover:bg-gray-100 transition-all">
                                Lihat Detail
                            </button>
                        </div>
                    </div>
                </div>
                
                <div class="portfolio-item card-hover scale-in bg-gradient-to-br from-purple-100 to-blue-100 flex items-center justify-center h-64">
                    <div class="text-center text-gray-700">
                        <i class="fas fa-plus text-4xl mb-4 text-purple-600"></i>
                        <h3 class="text-xl font-bold mb-2">More Projects</h3>
                        <p>Dan masih banyak karya lainnya</p>
                        <a href="more.html" class="block py-2 text-gray-700 hover:text-purple-600">More</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-20 gradient-bg">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16">
                <h2 class="text-4xl lg:text-5xl font-bold text-white mb-4 fade-in">Mari Berkolaborasi</h2>
                <div class="w-24 h-1 bg-white mx-auto fade-in"></div>
                <p class="text-xl text-white/90 mt-6 fade-in">Tertarik untuk bekerja sama? Hubungi saya!</p>
            </div>
            
            <div class="max-w-4xl mx-auto">
                <div class="grid md:grid-cols-2 gap-12 items-center">
                    <div class="slide-in-left">
                        <h3 class="text-3xl font-bold text-white mb-8">Get In Touch</h3>
                        <div class="space-y-6">
                            <div class="flex items-center text-white">
                                <i class="fab fa-instagram text-2xl w-8 mr-4"></i>
                                <div>
                                    <p class="font-semibold">Instagram</p>
                                    <a href="https://instagram.com/galuhmeibinar_" target="_blank" class="text-white/80 hover:text-white transition-all">
                                        @galuhmeibinar_
                                    </a>
                                </div>
                            </div>
                            <div class="flex items-center text-white">
                                <i class="fas fa-graduation-cap text-2xl w-8 mr-4"></i>
                                <div>
                                    <p class="font-semibold">Program</p>
                                    <p class="text-white/80">Digital Skill Participant</p>
                                </div>
                            </div>
                            <div class="flex items-center text-white">
                                <i class="fas fa-map-marker-alt text-2xl w-8 mr-4"></i>
                                <div>
                                    <p class="font-semibold">Lokasi</p>
                                    <p class="text-white/80">SMAN 1 Saradan</p>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="slide-in-right">
                        <div class="bg-white/10 backdrop-blur-md p-8 rounded-2xl">
                            <h4 class="text-2xl font-bold text-white mb-6">Kirim Pesan</h4>
                            <form class="space-y-4">
                                <input type="text" placeholder="Nama Anda" 
                                       class="w-full px-4 py-3 rounded-lg bg-white/20 text-white placeholder-white/70 border border-white/30 focus:border-white focus:outline-none transition-all">
                                <input type="email" placeholder="Email Anda" 
                                       class="w-full px-4 py-3 rounded-lg bg-white/20 text-white placeholder-white/70 border border-white/30 focus:border-white focus:outline-none transition-all">
                                <textarea placeholder="Pesan Anda" rows="4" 
                                          class="w-full px-4 py-3 rounded-lg bg-white/20 text-white placeholder-white/70 border border-white/30 focus:border-white focus:outline-none transition-all resize-none"></textarea>
                                <button type="button" onclick="showContactDemo()" 
                                        class="btn-hover w-full bg-white text-purple-600 py-3 rounded-lg font-semibold hover:bg-gray-100 transition-all">
                                    Kirim Pesan (Demo)
                                </button>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-12">
        <div class="container mx-auto px-6">
            <div class="text-center">
                <h3 class="text-2xl font-bold mb-4">Galuh Meibinar Keinaryosih</h3>
                <p class="text-gray-400 mb-6">Digital Creative Enthusiast | SMAN 1 Saradan</p>
                <div class="flex justify-center space-x-6 mb-8">
                    <a href="https://instagram.com/galuhmeibinar_" target="_blank" 
                       class="w-12 h-12 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full flex items-center justify-center hover:scale-110 transition-all">
                        <i class="fab fa-instagram text-xl"></i>
                    </a>
                </div>
                <div class="border-t border-gray-800 pt-8">
                    <p class="text-gray-400">
                        © 2024 Galuh Meibinar Keinaryosih. Made with ❤️ for Digital Skill Program
                    </p>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Smooth scrolling
        function scrollToSection(sectionId) {
            document.getElementById(sectionId).scrollIntoView({
                behavior: 'smooth'
            });
        }

        // Mobile menu toggle
        document.getElementById('mobile-menu-btn').addEventListener('click', function() {
            const mobileMenu = document.getElementById('mobile-menu');
            mobileMenu.classList.toggle('hidden');
        });

        // Animation on scroll
        function animateOnScroll() {
            const elements = document.querySelectorAll('.fade-in, .slide-in-left, .slide-in-right, .scale-in');
            
            elements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
                
                if (elementTop < window.innerHeight - elementVisible) {
                    element.classList.add('visible');
                }
            });
        }

        // Skill bar animation
        function animateSkillBars() {
            const skillBars = document.querySelectorAll('.skill-bar');
            skillBars.forEach(bar => {
                const barTop = bar.getBoundingClientRect().top;
                if (barTop < window.innerHeight - 100) {
                    bar.classList.add('animate');
                }
            });
        }

        // Contact form demo
        function showContactDemo() {
            alert('Demo: Terima kasih atas pesan Anda! Ini adalah demo form. Untuk menghubungi saya, silakan gunakan Instagram @galuhmeibinar_');
        }

        // Navigation active state
        function updateActiveNav() {
            const sections = ['home', 'about', 'skills', 'portfolio', 'contact'];
            const navLinks = document.querySelectorAll('.nav-link');
            
            sections.forEach((sectionId, index) => {
                const section = document.getElementById(sectionId);
                const rect = section.getBoundingClientRect();
                
                if (rect.top <= 100 && rect.bottom >= 100) {
                    navLinks.forEach(link => link.classList.remove('text-purple-600'));
                    if (navLinks[index]) {
                        navLinks[index].classList.add('text-purple-600');
                    }
                }
            });
        }

        // Event listeners
        window.addEventListener('scroll', function() {
            animateOnScroll();
            animateSkillBars();
            updateActiveNav();
        });

        window.addEventListener('load', function() {
            animateOnScroll();
            animateSkillBars();
        });

        // Mobile menu links
        document.querySelectorAll('#mobile-menu a').forEach(link => {
            link.addEventListener('click', function() {
                document.getElementById('mobile-menu').classList.add('hidden');
            });
        });

        // Parallax effect for hero section
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const hero = document.getElementById('home');
            if (hero) {
                hero.style.transform = `translateY(${scrolled * 0.5}px)`;
            }
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9723266dd1895f70',t:'MTc1NTcwNjExNC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
