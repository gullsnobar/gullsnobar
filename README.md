<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gull Snobar - Web Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2d2b55;
            --secondary: #4a467d;
            --accent: #ff79c6;
            --text: #f8f8f2;
            --background: #1a1835;
            --card-bg: rgba(45, 43, 85, 0.7);
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--background) 0%, #131127 100%);
            color: var(--text);
            min-height: 100vh;
            line-height: 1.6;
            padding: 0;
            margin: 0;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 0;
            margin-bottom: 2rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--accent);
            text-decoration: none;
            display: flex;
            align-items: center;
        }
        
        .nav-links {
            display: flex;
            gap: 2rem;
        }
        
        .nav-links a {
            color: var(--text);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }
        
        .nav-links a:after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            transition: var(--transition);
        }
        
        .nav-links a:hover:after {
            width: 100%;
        }
        
        .hero {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            margin-bottom: 4rem;
        }
        
        .hero-content h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(90deg, var(--accent) 0%, #bd93f9 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .hero-content h2 {
            font-size: 1.5rem;
            font-weight: 500;
            margin-bottom: 1.5rem;
            color: #bd93f9;
        }
        
        .hero-content p {
            margin-bottom: 2rem;
            font-size: 1.1rem;
            opacity: 0.9;
        }
        
        .hero-image {
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .hero-image img {
            max-width: 100%;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }
        
        .section-title {
            font-size: 2rem;
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
            padding-bottom: 1rem;
        }
        
        .section-title:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: var(--accent);
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-bottom: 4rem;
        }
        
        .skill-category {
            background: var(--card-bg);
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transition: var(--transition);
        }
        
        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }
        
        .skill-category h3 {
            color: var(--accent);
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }
        
        .skill-list {
            list-style: none;
        }
        
        .skill-list li {
            padding: 0.5rem 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
        }
        
        .skill-list li:before {
            content: '▹';
            color: var(--accent);
            margin-right: 10px;
        }
        
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }
        
        .project-card {
            background: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transition: var(--transition);
        }
        
        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }
        
        .project-content {
            padding: 1.5rem;
        }
        
        .project-card h3 {
            color: var(--accent);
            margin-bottom: 0.5rem;
            font-size: 1.3rem;
        }
        
        .project-card p {
            margin-bottom: 1rem;
            opacity: 0.9;
        }
        
        .project-link {
            display: inline-block;
            color: var(--accent);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
        }
        
        .project-link:hover {
            transform: translateX(5px);
        }
        
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-bottom: 4rem;
        }
        
        .stat-card {
            background: var(--card-bg);
            padding: 1.5rem;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .stat-card h3 {
            color: var(--accent);
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
        }
        
        .contact-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 4rem;
        }
        
        .contact-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: var(--card-bg);
            color: var(--text);
            border-radius: 50%;
            text-decoration: none;
            font-size: 1.5rem;
            transition: var(--transition);
        }
        
        .contact-link:hover {
            background: var(--accent);
            transform: translateY(-5px);
        }
        
        footer {
            text-align: center;
            padding: 2rem 0;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            margin-top: 2rem;
        }
        
        @media (max-width: 768px) {
            .hero {
                grid-template-columns: 1fr;
            }
            
            .nav-links {
                display: none;
            }
            
            .hero-content h1 {
                font-size: 2.5rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <a href="#" class="logo">Gull Snobar</a>
            <nav class="nav-links">
                <a href="#skills">Skills</a>
                <a href="#projects">Projects</a>
                <a href="#stats">Stats</a>
                <a href="#contact">Contact</a>
            </nav>
        </header>
        
        <section class="hero">
            <div class="hero-content">
                <h1>Gull Snobar</h1>
                <h2>Frontend Engineer & Web Developer</h2>
                <p>I build scalable web applications with React.js, Next.js, and TypeScript, with experience in Node.js, Express, and MongoDB for full-stack development. Focused on writing clean, performant code and delivering efficient solutions.</p>
                <div class="ai-tools">
                    <h3>AI Tools Expertise</h3>
                    <p>Lovable, Cursor, Windsurf, Replit, Trae AI, Claude, Deepseek</p>
                </div>
            </div>
            <div class="hero-image">
                <img src="https://raw.githubusercontent.com/gullsnobar/gullsnobar/main/snobar.png" alt="Gull Snobar Banner">
            </div>
        </section>
        
        <section id="skills">
            <h2 class="section-title">Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3>Frontend</h3>
                    <ul class="skill-list">
                        <li>HTML</li>
                        <li>CSS3</li>
                        <li>Sass</li>
                        <li>Bootstrap</li>
                        <li>JavaScript (ES6+)</li>
                        <li>TypeScript</li>
                        <li>React.js</li>
                        <li>Next.js</li>
                        <li>MUI</li>
                        <li>Tailwind CSS</li>
                        <li>Figma</li>
                        <li>Framer Motion</li>
                        <li>Redux</li>
                    </ul>
                </div>
                
                <div class="skill-category">
                    <h3>Backend & Databases</h3>
                    <ul class="skill-list">
                        <li>Node.js</li>
                        <li>Express.js</li>
                        <li>Firebase</li>
                        <li>MongoDB</li>
                        <li>Supabase</li>
                        <li>PostgreSQL</li>
                    </ul>
                </div>
                
                <div class="skill-category">
                    <h3>Testing & Tools</h3>
                    <ul class="skill-list">
                        <li>Jest</li>
                        <li>Postman</li>
                        <li>Git</li>
                        <li>GitHub</li>
                        <li>Jira</li>
                        <li>Agile Methodologies</li>
                        <li>Bash</li>
                    </ul>
                </div>
            </div>
        </section>
        
        <section id="projects">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-content">
                        <h3>LMS Website</h3>
                        <p>Fully responsive learning platform built with React.js.</p>
                        <a href="https://github.com/gullsnobar/LMS-Website" class="project-link">View Project</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-content">
                        <h3>QuickShop</h3>
                        <p>E-commerce application with cart management and dynamic product display.</p>
                        <a href="https://github.com/gullsnobar/QuickShop" class="project-link">View Project</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-content">
                        <h3>React Movie App</h3>
                        <p>Movie browser using API integration with React.js.</p>
                        <a href="https://github.com/gullsnobar/React-Movie-App" class="project-link">View Project</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-content">
                        <h3>Authentication Form</h3>
                        <p>Login & signup system with password hashing and session handling.</p>
                        <a href="https://github.com/gullsnobar/Authentication-Form" class="project-link">View Project</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-content">
                        <h3>Countries & Capitals Quiz</h3>
                        <p>Interactive quiz app with React.js & TypeScript.</p>
                        <a href="https://github.com/gullsnobar/Countries-Capitals-Quiz" class="project-link">View Project</a>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="stats">
            <h2 class="section-title">GitHub Statistics</h2>
            <div class="stats-container">
                <div class="stat-card">
                    <h3>50+</h3>
                    <p>Projects Completed</p>
                </div>
                <div class="stat-card">
                    <h3>100+</h3>
                    <p>Contributions</p>
                </div>
                <div class="stat-card">
                    <h3>15+</h3>
                    <p>Technologies Mastered</p>
                </div>
            </div>
        </section>
        
        <section id="contact">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-links">
                <a href="mailto:gullsnobar07@gmail.com" class="contact-link">
                    <i class="fas fa-envelope"></i>
                </a>
                <a href="https://drive.google.com/file/d/1CspY9yO3z3iFPxfoew6i8j_TEELanFmX/view?usp=sharing" class="contact-link">
                    <i class="fas fa-file-alt"></i>
                </a>
                <a href="https://www.linkedin.com/in/gullsanobar/" class="contact-link">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a href="https://github.com/gullsnobar" class="contact-link">
                    <i class="fab fa-github"></i>
                </a>
            </div>
        </section>
        
        <footer>
            <p>© 2023 Gull Snobar. All rights reserved.</p>
        </footer>
    </div>

    <script>
        // Simple animation for elements when they come into view
        document.addEventListener('DOMContentLoaded', function() {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });
            
            // Observe all section elements for animation
            document.querySelectorAll('section').forEach(section => {
                section.style.opacity = 0;
                section.style.transform = 'translateY(20px)';
                section.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
