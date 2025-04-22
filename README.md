<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Professional Portfolio</title>
    <style>
        /* Global Styles */
        :root {
            --primary-color: #3498db;
            --secondary-color: #2c3e50;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #2c3e50;
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        
        a {
            text-decoration: none;
            color: var(--primary-color);
            transition: var(--transition);
        }
        
        a:hover {
            color: var(--accent-color);
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }
        
        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--secondary-color);
        }
        
        .logo span {
            color: var(--primary-color);
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 30px;
        }
        
        .nav-links a {
            color: var(--dark-color);
            font-weight: 500;
            position: relative;
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            bottom: -5px;
            left: 0;
            transition: var(--transition);
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 80px;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        }
        
        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .hero-text {
            flex: 1;
            padding-right: 50px;
        }
        
        .hero-text h1 {
            font-size: 48px;
            margin-bottom: 20px;
            color: var(--secondary-color);
        }
        
        .hero-text h1 span {
            color: var(--primary-color);
        }
        
        .hero-text p {
            font-size: 18px;
            margin-bottom: 30px;
            color: #666;
        }
        
        .hero-image {
            flex: 1;
            text-align: center;
        }
        
        .hero-image img {
            max-width: 100%;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        
        .btn {
            display: inline-block;
            background: var(--primary-color);
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            font-weight: 500;
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background: var(--accent-color);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid var(--primary-color);
            color: var(--primary-color);
            margin-left: 15px;
        }
        
        .btn-outline:hover {
            background: var(--primary-color);
            color: white;
        }
        
        /* About Section */
        .section {
            padding: 100px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .section-title h2 {
            font-size: 36px;
            color: var(--secondary-color);
            position: relative;
            display: inline-block;
            padding-bottom: 15px;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            width: 50%;
            height: 3px;
            background: var(--primary-color);
            bottom: 0;
            left: 25%;
        }
        
        .about-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .about-text {
            flex: 1;
            padding-right: 50px;
        }
        
        .about-text h3 {
            font-size: 24px;
            margin-bottom: 20px;
            color: var(--secondary-color);
        }
        
        .about-text p {
            margin-bottom: 15px;
        }
        
        .skills {
            flex: 1;
        }
        
        .skill-item {
            margin-bottom: 25px;
        }
        
        .skill-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }
        
        .skill-bar {
            height: 10px;
            background: #e0e0e0;
            border-radius: 5px;
            overflow: hidden;
        }
        
        .skill-progress {
            height: 100%;
            background: var(--primary-color);
            border-radius: 5px;
            transition: width 1s ease;
        }
        
        /* Resume Questions Section */
        .resume-questions {
            background-color: var(--light-color);
        }
        
        .question-container {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .question-card {
            background: white;
            border-radius: 10px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }
        
        .question-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }
        
        .question-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            cursor: pointer;
        }
        
        .question-header h3 {
            color: var(--secondary-color);
        }
        
        .toggle-btn {
            width: 30px;
            height: 30px;
            background: var(--primary-color);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .toggle-btn:hover {
            background: var(--accent-color);
            transform: rotate(90deg);
        }
        
        .answer {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease;
        }
        
        .answer.show {
            max-height: 500px;
        }
        
        /* Contact Section */
        .contact-info {
            display: flex;
            justify-content: center;
            margin-top: 50px;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            margin: 0 20px;
            padding: 15px 25px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }
        
        .contact-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }
        
        .contact-icon {
            width: 50px;
            height: 50px;
            background: var(--primary-color);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            font-size: 20px;
        }
        
        .contact-text h4 {
            color: var(--secondary-color);
            margin-bottom: 5px;
        }
        
        /* Footer */
        footer {
            background: var(--secondary-color);
            color: white;
            padding: 30px 0;
            text-align: center;
        }
        
        .social-links {
            margin: 20px 0;
        }
        
        .social-links a {
            display: inline-block;
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border-radius: 50%;
            margin: 0 10px;
            line-height: 40px;
            transition: var(--transition);
        }
        
        .social-links a:hover {
            background: var(--primary-color);
            transform: translateY(-5px);
        }
        
        /* Responsive Design */
        @media (max-width: 992px) {
            .hero-content, .about-content {
                flex-direction: column;
            }
            
            .hero-text, .about-text {
                padding-right: 0;
                margin-bottom: 50px;
                text-align: center;
            }
            
            .hero-image {
                order: -1;
                margin-bottom: 50px;
            }
            
            .btn {
                display: block;
                margin: 15px auto;
                width: 200px;
            }
            
            .btn-outline {
                margin-left: auto;
            }
            
            .contact-info {
                flex-direction: column;
                align-items: center;
            }
            
            .contact-item {
                margin: 10px 0;
                width: 100%;
                max-width: 300px;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero-text h1 {
                font-size: 36px;
            }
            
            .section-title h2 {
                font-size: 30px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">Port<span>folio</span></div>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#resume">Resume Q&A</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Hi, I'm <span>Your Name</span></h1>
                    <p>Professional [Your Job Title] with [X] years of experience in [Your Industry]. Passionate about creating innovative solutions and delivering exceptional results.</p>
                    <div>
                        <a href="#contact" class="btn">Hire Me</a>
                        <a href="#resume" class="btn btn-outline">Resume Q&A</a>
                    </div>
                </div>
                <div class="hero-image">
                    <img src="https://via.placeholder.com/400x500" alt="Profile Image">
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="section" id="about">
        <div class="container">
            <div class="section-title">
                <h2>About Me</h2>
            </div>
            <div class="about-content">
                <div class="about-text">
                    <h3>Who Am I?</h3>
                    <p>I'm a passionate professional with expertise in [your field]. With a strong background in [specific skills or industries], I bring a unique perspective to every project I undertake.</p>
                    <p>My journey began at [education or early career experience], and since then I've had the privilege of working with [notable companies or clients].</p>
                    <p>What sets me apart is my ability to [unique value proposition]. I thrive in environments that challenge me to think creatively and push boundaries.</p>
                </div>
                <div class="skills">
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>Web Development</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>UI/UX Design</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>Project Management</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>Data Analysis</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 75%;"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Resume Questions Section -->
    <section class="section resume-questions" id="resume">
        <div class="container">
            <div class="section-title">
                <h2>Resume Questions</h2>
            </div>
            <div class="question-container">
                <div class="question-card">
                    <div class="question-header" onclick="toggleAnswer(1)">
                        <h3>Can you walk me through your resume?</h3>
                        <div class="toggle-btn">+</div>
                    </div>
                    <div class="answer" id="answer1">
                        <p>Certainly! I began my career at [Company Name] where I [brief description of role and accomplishments]. This experience helped me develop strong skills in [relevant skills].</p>
                        <p>After that, I moved to [Next Company] where I [key achievements]. This role allowed me to grow in [specific areas].</p>
                        <p>Most recently at [Current/Most Recent Company], I've been focused on [current responsibilities and achievements]. This has been particularly rewarding because [reason why].</p>
                    </div>
                </div>
                
                <div class="question-card">
                    <div class="question-header" onclick="toggleAnswer(2)">
                        <h3>What's your greatest professional achievement?</h3>
                        <div class="toggle-btn">+</div>
                    </div>
                    <div class="answer" id="answer2">
                        <p>My greatest achievement was [specific accomplishment] at [Company]. I was responsible for [your role], which resulted in [quantifiable results].</p>
                        <p>This was particularly meaningful because [why it matters]. It demonstrated my ability to [relevant skills or qualities].</p>
                    </div>
                </div>
                
                <div class="question-card">
                    <div class="question-header" onclick="toggleAnswer(3)">
                        <h3>Why are you looking for a new opportunity?</h3>
                        <div class="toggle-btn">+</div>
                    </div>
                    <div class="answer" id="answer3">
                        <p>I've really enjoyed my time at [Current Company] and have learned a great deal. However, I'm looking for [what you're seeking - growth, new challenges, specific type of work] which aligns well with this opportunity.</p>
                        <p>I'm particularly excited about [aspect of new role/company] because [reason].</p>
                    </div>
                </div>
                
                <div class="question-card">
                    <div class="question-header" onclick="toggleAnswer(4)">
                        <h3>What are your greatest strengths?</h3>
                        <div class="toggle-btn">+</div>
                    </div>
                    <div class="answer" id="answer4">
                        <p>My top strengths are:</p>
                        <ul>
                            <li><strong>[Strength 1]:</strong> [Explanation with example]</li>
                            <li><strong>[Strength 2]:</strong> [Explanation with example]</li>
                            <li><strong>[Strength 3]:</strong> [Explanation with example]</li>
                        </ul>
                        <p>These have consistently helped me [positive outcome] in my previous roles.</p>
                    </div>
                </div>
                
                <div class="question-card">
                    <div class="question-header" onclick="toggleAnswer(5)">
                        <h3>What's your approach to [relevant job responsibility]?</h3>
                        <div class="toggle-btn">+</div>
                    </div>
                    <div class="answer" id="answer5">
                        <p>My approach to [responsibility] involves [your methodology]. At [Company], I implemented this by [specific example], which resulted in [outcome].</p>
                        <p>I believe this approach works well because [reasoning]. However, I'm always looking to refine my methods by [how you stay current].</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Get In Touch</h2>
            </div>
            <div class="contact-info">
                <div class="contact-item">
                    <div class="contact-icon">
                        ✉
                    </div>
                    <div class="contact-text">
                        <h4>Email</h4>
                        <a href="mailto:your.email@example.com">your.email@example.com</a>
                    </div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">
                        🔗
                    </div>
                    <div class="contact-text">
                        <h4>LinkedIn</h4>
                        <a href="https://linkedin.com/in/yourprofile" target="_blank">linkedin.com/in/yourprofile</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2023 Your Name. All Rights Reserved.</p>
            <div class="social-links">
                <a href="#"><i class="fab fa-linkedin"></i></a>
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
            </div>
        </div>
    </footer>

    <script>
        // Toggle answers for resume questions
        function toggleAnswer(id) {
            const answer = document.getElementById(answer${id});
            const btn = document.querySelector(#answer${id}).previousElementSibling.querySelector('.toggle-btn');
            
            answer.classList.toggle('show');
            
            if (answer.classList.contains('show')) {
                btn.textContent = '-';
            } else {
                btn.textContent = '+';
            }
        }
        
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
