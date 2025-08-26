<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio - Muhamad Naufal Alifa Sanusi</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #1f2937, #374151);
            color: #d1d5db;
            min-height: 100vh;
            line-height: 1.6;
            font-size: 16px;
        }
        
        /* Mobile-first approach */
        header {
            background: rgba(0, 0, 0, 0.95);
            backdrop-filter: blur(10px);
            padding: 1rem;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.4);
        }
        
        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-wrap: wrap;
            gap: 0.5rem;
        }
        
        nav a {
            color: #d1d5db;
            text-decoration: none;
            margin: 0.25rem 0.75rem;
            font-weight: 600;
            font-size: 0.9rem;
            transition: color 0.3s ease, transform 0.3s ease;
            padding: 0.5rem;
        }
        
        nav a:hover {
            color: #2dd4bf;
            transform: translateY(-2px);
        }
        
        .section {
            max-width: 1200px;
            margin: 1rem auto;
            padding: 1.5rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
        }
        
        .hero {
            text-align: center;
            padding: 3rem 1.5rem;
        }
        
        .hero h1 {
            font-size: 2rem;
            font-weight: 700;
            color: #2dd4bf;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.1rem;
            color: #9ca3af;
            margin-bottom: 2rem;
            line-height: 1.4;
        }
        
        .hero-buttons {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
        }
        
        .hero-buttons a, .project-card button, .submit-btn {
            background: #f59e0b;
            color: #d1d5db;
            padding: 0.75rem 1.25rem;
            border: none;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.9rem;
            transition: background 0.3s ease, transform 0.3s ease;
            cursor: pointer;
            display: inline-block;
            min-width: 120px;
            text-align: center;
        }
        
        .hero-buttons a:hover, .project-card button:hover, .submit-btn:hover {
            background: #d97706;
            transform: scale(1.05);
        }
        
        .section h2 {
            color: #2dd4bf;
            font-size: 1.8rem;
            font-weight: 600;
            margin-bottom: 1.5rem;
            text-align: center;
        }
        
        .about p {
            color: #d1d5db;
            font-weight: 300;
            text-align: justify;
            line-height: 1.7;
        }
        
        .skills-grid, .projects-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.5rem;
        }
        
        .skill-card, .project-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 1.5rem;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .skill-card:hover, .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.4);
        }
        
        .skill-card h3, .project-card h3 {
            color: #f59e0b;
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }
        
        .skill-card p, .project-card p {
            color: #9ca3af;
            font-size: 0.95rem;
            line-height: 1.5;
        }
        
        .project-card img {
            max-width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 1rem;
            border: 2px solid #2dd4bf;
            background: rgba(255, 255, 255, 0.1);
        }
        
        .contact form {
            display: flex;
            flex-direction: column;
            gap: 1.2rem;
            max-width: 600px;
            margin: 0 auto;
        }
        
        input, textarea {
            padding: 1rem;
            border: none;
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.15);
            color: #d1d5db;
            font-family: 'Inter', sans-serif;
            font-size: 1rem;
            width: 100%;
        }
        
        input::placeholder, textarea::placeholder {
            color: #6b7280;
        }
        
        input:focus, textarea:focus {
            background: rgba(255, 255, 255, 0.2);
            box-shadow: 0 0 10px rgba(45, 212, 191, 0.5);
            outline: none;
        }
        
        textarea {
            resize: vertical;
            min-height: 120px;
        }
        
        footer {
            text-align: center;
            padding: 1.5rem;
            background: rgba(0, 0, 0, 0.95);
            color: #9ca3af;
            font-size: 0.85rem;
            margin-top: 2rem;
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            justify-content: center;
            align-items: center;
            z-index: 2000;
            padding: 1rem;
        }
        
        .modal-content {
            background: #1f2937;
            color: #d1d5db;
            padding: 2rem;
            border-radius: 15px;
            max-width: 400px;
            width: 100%;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.4);
            text-align: center;
        }
        
        .modal-content h2 {
            color: #f59e0b;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }
        
        .modal-content input[type="file"] {
            margin-bottom: 1rem;
            padding: 0.5rem;
            width: 100%;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 5px;
            color: #d1d5db;
        }
        
        .modal-buttons {
            display: flex;
            gap: 0.5rem;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        .modal-content button {
            background: #f59e0b;
            color: #d1d5db;
            padding: 0.75rem 1.25rem;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            margin: 0.25rem;
            min-width: 80px;
        }
        
        .modal-content button:hover {
            background: #d97706;
            transform: scale(1.05);
        }
        
        .close-btn {
            background: #6b7280 !important;
        }
        
        .close-btn:hover {
            background: #4b5563 !important;
        }
        
        /* Tablet styles */
        @media (min-width: 768px) {
            .section {
                margin: 2rem auto;
                padding: 2.5rem;
            }
            
            .hero {
                padding: 4rem 2.5rem;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            .section h2 {
                font-size: 2rem;
            }
            
            .skills-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .projects-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            nav a {
                font-size: 1rem;
                margin: 0 1rem;
            }
        }
        
        /* Desktop styles */
        @media (min-width: 1024px) {
            .hero h1 {
                font-size: 3rem;
            }
            
            .hero p {
                font-size: 1.3rem;
            }
            
            .skills-grid {
                grid-template-columns: repeat(4, 1fr);
            }
            
            .projects-grid {
                grid-template-columns: repeat(3, 1fr);
            }
            
            nav a {
                font-size: 1.1rem;
                margin: 0 1.5rem;
            }
            
            .skill-card:hover, .project-card:hover {
                transform: translateY(-10px);
            }
        }
        
        /* Large desktop */
        @media (min-width: 1200px) {
            .projects-grid {
                grid-template-columns: repeat(4, 1fr);
            }
        }
        
        /* Animation */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .section, footer {
            animation: fadeIn 0.8s ease-out;
        }
        
        /* Touch improvements for mobile */
        @media (max-width: 767px) {
            nav a {
                padding: 0.75rem;
                min-height: 44px;
                display: inline-flex;
                align-items: center;
                justify-content: center;
            }
            
            .hero-buttons a, .project-card button {
                min-height: 44px;
                display: inline-flex;
                align-items: center;
                justify-content: center;
            }
            
            .project-card {
                padding: 1rem;
            }
            
            .skill-card {
                padding: 1rem;
            }
        }
        
        /* Prevent horizontal scroll on mobile */
        body {
            overflow-x: hidden;
        }
        
        .section {
            margin-left: 0.5rem;
            margin-right: 0.5rem;
        }
        
        @media (min-width: 768px) {
            .section {
                margin-left: auto;
                margin-right: auto;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <a href="#home">Home</a>
            <a href="#about">About Me</a>
            <a href="#skills">Skills</a>
            <a href="#projects">Projects</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <section id="home" class="section hero">
        <h1>Welcome to My Portfolio</h1>
        <p>Student of Pelita Nusantara Vocational High School</p>
        <div class="hero-buttons">
    <a href="#projects">Lihat Proyek</a>
   <a href="img/cv_naufal.pdf.pdf" class="btn">Unduh CV</a>
</div>

    </section>

    <section id="about" class="section about">
        <h2>About Me</h2>
        <p>I am a student of Pelita Nusantara High School specializing in Computer Network Engineering with foundational skills in installing, configuring, and maintaining computer networks. Passionate about technological advancement, I actively enhance my expertise through training, hands-on practice, and personal projects. I am responsible, quick to learn, and eager to contribute to both company and workplace.</p>
    </section>

    <section id="skills" class="section skills">
        <h2>My Skills</h2>
        <div class="skills-grid">
            <div class="skill-card">
                <h3>Mikrotik</h3>
                <p>Configuring VLAN and hotspot, blocking web, troubleshooting network issues</p>
            </div>
            <div class="skill-card">
                <h3>Fiber Optic</h3>
                <p>Splicing and installation techniques for fiber optic networks</p>
            </div>
            <div class="skill-card">
                <h3>Server</h3>
                <p>Operating system administration and server management</p>
            </div>
            <div class="skill-card">
                <h3>Electrical</h3>
                <p>Basic electrical engineering and network infrastructure</p>
            </div>
        </div>
    </section>

    <section id="projects" class="section projects">
        <h2>My Projects</h2>
        <div class="projects-grid">
            <div class="project-card">
                <h3>SMART LAMP AUTOMATICALLY</h3>
                <p>setup and splicing cable fiber and attenuation.</p>
                <img src="img/IMG-11.jpeg" alt="Project 1" class="project-img">
            </div>
            <div class="project-card">
                <h3>SPLICING CABLE AND ANTENUATION</h3>
                <img src="img/IMG-12.jpeg" alt="Project 2" class="project-img">
            </div>
            <div class="project-card">
                <h3>NETWORK CONFIGURATION</h3>
                <img src="img/IMG-13.jpeg" alt="Project 3" class="project-img">
            </div>
            <div class="project-card">
                <h3>MONITORING SOUND SYSTEM</h3>
                <img src="img/IMG-14.jpeg" alt="Project 4" class="project-img">
              
            </div>
            <div class="project-card">
                <h3>MONITORING QUALITY </h3>
                <img src="img/IMG-15.jpeg" alt="Project 5" class="project-img">
               
            </div>
            <div class="project-card">
                <h3>INTALASI AND SPLITER CABLE FIBER OPTIK</h3>
                <img src="img/IMG-16.jpeg" alt="Project 6" class="project-img">
               
            </div>
            <div class="project-card">
                <h3>INTALASI AND CONFIGURATON PPOE</h3>
                <img src="img/IMG-17.jpeg" alt="Project 7" class="project-img">
               
            </div>
            <div class="project-card">
                <h3>TROUBLESHOOTING NETWORK</h3>
                <img src="img/IMG-18.jpeg" alt="Project 8" class="project-img">
               
            </div>
            <div class="project-card">
                <h3>SERTIFIKAT MIKROTIK DASAR</h3>
                <img src="img/IMG-19.jpeg" alt="Project 9" class="project-img">
            </div>
            <div class="project-card">
                <h3>SERTIFIKAT IMPLEMENTASI IPV6</h3>
                <img src="img/IMG-20.jpeg".jpeg" alt="Project 10" class="project-img">
            </div>
            <div class="project-card">
                <h3>SERTIFIKAT WEBINAR TELKOM</h3>
                <img src="img/IMG-21.jpeg" alt="Project 11" class="project-img">
            </div>
        </div>
    </section>

    <section id="contact" class="section contact">
    <h2>Contact Me</h2>
    <form action="https://formspree.io/f/mqadznbl" method="POST">
        <input type="text" name="name" placeholder="Nama Kamu" required>
        <input type="email" name="email" placeholder="Email Kamu" required>
        <textarea name="message" placeholder="Pesan Kamu" required></textarea>
        <!-- Wajib tambahkan input hidden untuk format JSON -->
        <input type="hidden" name="_replyto" value="">
        <input type="hidden" name="_subject" value="Pesan Baru dari Portfolio">
        <button type="submit" class="submit-btn">Kirim Pesan</button>
    </form>
</section>

<script>
// Optional: menampilkan alert jika form sukses terkirim
const form = document.querySelector('form');
form.addEventListener('submit', async function(e) {
    e.preventDefault();
    const data = new FormData(form);
    const response = await fetch(form.action, {
        method: form.method,
        body: data,
        headers: { 'Accept': 'application/json' }
    });
    if (response.ok) {
        alert("Pesan berhasil dikirim!");
        form.reset();
    } else {
        alert("Terjadi kesalahan, coba lagi.");
    }
});
</script>

    </section>

    <footer>
        <p>© 2025 Muhamad Naufal Alifa Sanusi Portfolio. All Rights Reserved.</p>
    </footer>

    <div id="modal" class="modal">
        <div class="modal-content">
            <h2>Add Photo</h2>
            <input type="file" id="photoInput" accept="image/*">
            <div class="modal-buttons">
                <button onclick="uploadPhoto()">Upload</button>
                <button class="close-btn" onclick="closeModal()">Close</button>
            </div>
        </div>
    </div>

    <script>
        let currentProject = '';

        // Persistent image storage system
        const projectImages = {};

        // Load saved images on page load
        window.addEventListener('load', function() {
            loadSavedImages();
        });

        function loadSavedImages() {
            // Try to load from localStorage if available, otherwise use session storage
            try {
                for (let i = 1; i <= 8; i++) {
                    const projectKey = `project${i}`;
                    let savedImage = null;
                    
                    // Try localStorage first
                    try {
                        savedImage = localStorage.getItem(`projectImage_${projectKey}`);
                    } catch (e) {
                        // If localStorage fails, try sessionStorage
                        try {
                            savedImage = sessionStorage.getItem(`projectImage_${projectKey}`);
                        } catch (e) {
                            // If both fail, use memory storage
                            savedImage = projectImages[projectKey];
                        }
                    }
                    
                    if (savedImage) {
                        const imgElement = document.querySelector(`.project-card img[alt="Project ${i}"]`);
                        if (imgElement) {
                            imgElement.src = savedImage;
                            // Also store in memory as backup
                            projectImages[projectKey] = savedImage;
                        }
                    }
                }
            } catch (error) {
                console.log('Loading images from memory storage only');
            }
        }

        function saveImage(projectKey, imageData) {
            // Store in memory first
            projectImages[projectKey] = imageData;
            
            // Try to save to localStorage
            try {
                localStorage.setItem(`projectImage_${projectKey}`, imageData);
                console.log(`Image saved to localStorage for ${projectKey}`);
            } catch (e) {
                // If localStorage fails, try sessionStorage
                try {
                    sessionStorage.setItem(`projectImage_${projectKey}`, imageData);
                    console.log(`Image saved to sessionStorage for ${projectKey}`);
                } catch (e) {
                    console.log(`Image saved to memory only for ${projectKey}`);
                }
            }
        }

        function openModal(project) {
            currentProject = project;
            document.getElementById('modal').style.display = 'flex';
        }

        function closeModal() {
            document.getElementById('modal').style.display = 'none';
            document.getElementById('photoInput').value = '';
        }

        function uploadPhoto() {
            const fileInput = document.getElementById('photoInput');
            const file = fileInput.files[0];
            
            if (file) {
                // Validate file size (max 5MB)
                if (file.size > 5 * 1024 * 1024) {
                    alert('File size too large. Please choose an image smaller than 5MB.');
                    return;
                }
                
                // Validate file type
                if (!file.type.startsWith('image/')) {
                    alert('Please select a valid image file.');
                    return;
                }
                
                const reader = new FileReader();
                reader.onload = function(e) {
                    const projectNumber = currentProject.replace('project', '');
                    const imgElement = document.querySelector(`.project-card img[alt="Project ${projectNumber}"]`);
                    
                    if (imgElement) {
                        // Compress image if too large
                        const img = new Image();
                        img.onload = function() {
                            const canvas = document.createElement('canvas');
                            const ctx = canvas.getContext('2d');
                            
                            // Calculate new dimensions (max 800px width)
                            let { width, height } = img;
                            const maxWidth = 800;
                            
                            if (width > maxWidth) {
                                height = (height * maxWidth) / width;
                                width = maxWidth;
                            }
                            
                            canvas.width = width;
                            canvas.height = height;
                            
                            // Draw and compress
                            ctx.drawImage(img, 0, 0, width, height);
                            const compressedData = canvas.toDataURL('image/jpeg', 0.8);
                            
                            // Update display
                            imgElement.src = compressedData;
                            
                            // Save the image
                            saveImage(currentProject, compressedData);
                            
                            closeModal();
                            
                            // Show success message
                            showMessage('Photo uploaded successfully!', 'success');
                        };
                        img.src = e.target.result;
                    }
                };
                reader.readAsDataURL(file);
            }
        }

        function showMessage(message, type = 'info') {
            // Create message element
            const messageEl = document.createElement('div');
            messageEl.style.cssText = `
                position: fixed;
                top: 100px;
                right: 20px;
                background: ${type === 'success' ? '#10b981' : '#f59e0b'};
                color: white;
                padding: 1rem 1.5rem;
                border-radius: 10px;
                box-shadow: 0 4px 12px rgba(0,0,0,0.3);
                z-index: 3000;
                animation: slideIn 0.3s ease;
                max-width: 300px;
                font-weight: 600;
            `;
            
            messageEl.textContent = message;
            document.body.appendChild(messageEl);
            
            // Remove after 3 seconds
            setTimeout(() => {
                messageEl.style.animation = 'slideOut 0.3s ease';
                setTimeout(() => {
                    if (messageEl.parentNode) {
                        messageEl.parentNode.removeChild(messageEl);
                    }
                }, 300);
            }, 3000);
        }

        // Add CSS for message animations
        const messageStyles = document.createElement('style');
        messageStyles.textContent = `
            @keyframes slideIn {
                from { transform: translateX(100%); opacity: 0; }
                to { transform: translateX(0); opacity: 1; }
            }
            @keyframes slideOut {
                from { transform: translateX(0); opacity: 1; }
                to { transform: translateX(100%); opacity: 0; }
            }
        `;
        document.head.appendChild(messageStyles);

        // Close modal when clicking outside
        document.getElementById('modal').addEventListener('click', function(e) {
            if (e.target === this) {
                closeModal();
            }
        });

        // Add keyboard support for modal
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape' && document.getElementById('modal').style.display === 'flex') {
                closeModal();
            }
        });

        // Form submission
        document.querySelector('form').addEventListener('submit', (e) => {
            e.preventDefault();
            showMessage('Message sent successfully! I will respond soon.', 'success');
            e.target.reset();
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add loading states for better UX
        function showLoading(button) {
            const originalText = button.textContent;
            button.textContent = 'Loading...';
            button.disabled = true;
            
            setTimeout(() => {
                button.textContent = originalText;
                button.disabled = false;
            }, 1000);
        }

        // Optimize images for mobile
        function optimizeImageForMobile(img) {
            if (window.innerWidth <= 768) {
                img.loading = 'lazy';
            }
        }

        // Apply optimizations on load
        document.addEventListener('DOMContentLoaded', function() {
            const images = document.querySelectorAll('.project-img');
            images.forEach(optimizeImageForMobile);
        });

        // Auto-save functionality - save images periodically
        setInterval(function() {
            // Backup current images
            Object.keys(projectImages).forEach(key => {
                if (projectImages[key]) {
                    try {
                        sessionStorage.setItem(`backup_${key}`, projectImages[key]);
                    } catch (e) {
                        // Storage full, continue silently
                    }
                }
            });
        }, 30000); // Auto-save every 30 seconds

        // Handle page visibility change to save data
        document.addEventListener('visibilitychange', function() {
            if (document.hidden) {
                // Page is hidden, save current state
                Object.keys(projectImages).forEach(key => {
                    if (projectImages[key]) {
                        saveImage(key, projectImages[key]);
                    }
                });
            }
        });

        // Handle before page unload
        window.addEventListener('beforeunload', function() {
            // Last chance to save data
            Object.keys(projectImages).forEach(key => {
                if (projectImages[key]) {
                    try {
                        sessionStorage.setItem(`lastSave_${key}`, projectImages[key]);
                    } catch (e) {
                        // Continue silently
                    }
                }
            });
        });
    </script>
</body>
</html>
