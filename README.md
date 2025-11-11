<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Samuel Bitencourt | Cyberpunk Dev</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;500;600;700&display=swap');
        
        :root {
            --neon-blue: #00f3ff;
            --neon-pink: #ff00ff;
            --neon-purple: #9d00ff;
            --dark-bg: #0a0a0a;
            --darker-bg: #050505;
            --grid-color: rgba(0, 243, 255, 0.1);
            --text-glow: 0 0 10px currentColor;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background-color: var(--dark-bg);
            color: #e0e0e0;
            font-family: 'Rajdhani', sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }
        
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                linear-gradient(90deg, var(--grid-color) 1px, transparent 1px) 0 0 / 20px 20px,
                linear-gradient(var(--grid-color) 1px, transparent 1px) 0 0 / 20px 20px;
            pointer-events: none;
            z-index: -1;
        }
        
        .cyber-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
        }
        
        .glitch-container {
            position: relative;
            margin-bottom: 3rem;
        }
        
        .cyber-header {
            text-align: center;
            padding: 3rem 0;
            position: relative;
            border-bottom: 2px solid var(--neon-blue);
            margin-bottom: 3rem;
        }
        
        .cyber-header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent 30%, rgba(0, 243, 255, 0.1) 50%, transparent 70%);
            animation: scan 3s linear infinite;
        }
        
        h1 {
            font-family: 'Orbitron', monospace;
            font-size: 3.5rem;
            font-weight: 900;
            color: var(--neon-blue);
            text-transform: uppercase;
            letter-spacing: 4px;
            margin-bottom: 1rem;
            text-shadow: var(--text-glow);
            position: relative;
        }
        
        h2 {
            font-family: 'Orbitron', monospace;
            font-size: 2rem;
            color: var(--neon-pink);
            margin-bottom: 1.5rem;
            text-shadow: var(--text-glow);
            position: relative;
        }
        
        h3 {
            font-family: 'Orbitron', monospace;
            font-size: 1.5rem;
            color: var(--neon-purple);
            margin-bottom: 1rem;
            text-shadow: var(--text-glow);
        }
        
        .neon-text {
            color: var(--neon-blue);
            text-shadow: var(--text-glow);
        }
        
        .pink-text {
            color: var(--neon-pink);
            text-shadow: var(--text-glow);
        }
        
        .cyber-section {
            background: rgba(10, 10, 10, 0.8);
            border: 1px solid var(--neon-blue);
            padding: 2rem;
            margin-bottom: 2rem;
            position: relative;
            box-shadow: 0 0 15px rgba(0, 243, 255, 0.2);
            transition: all 0.3s ease;
        }
        
        .cyber-section:hover {
            box-shadow: 0 0 25px rgba(0, 243, 255, 0.4);
            transform: translateY(-5px);
        }
        
        .cyber-section::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, var(--neon-blue), var(--neon-pink), var(--neon-purple), var(--neon-blue));
            z-index: -1;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .cyber-section:hover::before {
            opacity: 1;
        }
        
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }
        
        .tech-item {
            text-align: center;
            padding: 1rem;
            background: rgba(20, 20, 20, 0.8);
            border: 1px solid rgba(0, 243, 255, 0.3);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .tech-item:hover {
            transform: translateY(-5px);
            border-color: var(--neon-blue);
            box-shadow: 0 5px 15px rgba(0, 243, 255, 0.3);
        }
        
        .tech-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 243, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }
        
        .tech-item:hover::before {
            left: 100%;
        }
        
        .tech-icon {
            width: 40px;
            height: 40px;
            margin: 0 auto 0.5rem;
            filter: brightness(0) invert(1);
        }
        
        .tech-item:hover .tech-icon {
            filter: none;
        }
        
        .timeline {
            position: relative;
            padding-left: 2rem;
        }
        
        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 3px;
            background: linear-gradient(to bottom, var(--neon-blue), var(--neon-pink));
        }
        
        .timeline-item {
            position: relative;
            margin-bottom: 2rem;
            padding-left: 1.5rem;
        }
        
        .timeline-item::before {
            content: '';
            position: absolute;
            left: -2.5rem;
            top: 0.5rem;
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: var(--neon-blue);
            box-shadow: 0 0 10px var(--neon-blue);
        }
        
        .contact-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
            margin-top: 2rem;
        }
        
        .cyber-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.8rem 1.5rem;
            background: rgba(20, 20, 20, 0.8);
            border: 1px solid var(--neon-blue);
            color: var(--neon-blue);
            text-decoration: none;
            font-family: 'Rajdhani', sans-serif;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .cyber-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 243, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }
        
        .cyber-btn:hover::before {
            left: 100%;
        }
        
        .cyber-btn:hover {
            background: rgba(0, 243, 255, 0.1);
            box-shadow: 0 0 15px rgba(0, 243, 255, 0.4);
            transform: translateY(-3px);
        }
        
        .terminal {
            background: rgba(0, 0, 0, 0.9);
            border: 1px solid var(--neon-blue);
            padding: 1.5rem;
            margin-top: 1rem;
            font-family: 'Courier New', monospace;
            position: relative;
        }
        
        .terminal::before {
            content: '>>>';
            color: var(--neon-pink);
            margin-right: 0.5rem;
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        @keyframes scan {
            0% {
                transform: translateY(-100%);
            }
            100% {
                transform: translateY(100%);
            }
        }
        
        @keyframes pulse {
            0% {
                opacity: 1;
            }
            50% {
                opacity: 0.5;
            }
            100% {
                opacity: 1;
            }
        }
        
        .glitch {
            position: relative;
        }
        
        .glitch::before,
        .glitch::after {
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
        
        .glitch::before {
            left: 2px;
            text-shadow: -2px 0 var(--neon-pink);
            clip: rect(44px, 450px, 56px, 0);
            animation: glitch-anim 5s infinite linear alternate-reverse;
        }
        
        .glitch::after {
            left: -2px;
            text-shadow: -2px 0 var(--neon-blue);
            clip: rect(44px, 450px, 56px, 0);
            animation: glitch-anim2 5s infinite linear alternate-reverse;
        }
        
        @keyframes glitch-anim {
            0% {
                clip: rect(42px, 9999px, 44px, 0);
            }
            5% {
                clip: rect(12px, 9999px, 59px, 0);
            }
            10% {
                clip: rect(48px, 9999px, 29px, 0);
            }
            15% {
                clip: rect(42px, 9999px, 73px, 0);
            }
            20% {
                clip: rect(63px, 9999px, 27px, 0);
            }
            25% {
                clip: rect(34px, 9999px, 55px, 0);
            }
            30% {
                clip: rect(86px, 9999px, 73px, 0);
            }
            35% {
                clip: rect(20px, 9999px, 20px, 0);
            }
            40% {
                clip: rect(26px, 9999px, 60px, 0);
            }
            45% {
                clip: rect(25px, 9999px, 66px, 0);
            }
            50% {
                clip: rect(57px, 9999px, 98px, 0);
            }
            55% {
                clip: rect(5px, 9999px, 46px, 0);
            }
            60% {
                clip: rect(82px, 9999px, 31px, 0);
            }
            65% {
                clip: rect(54px, 9999px, 27px, 0);
            }
            70% {
                clip: rect(28px, 9999px, 99px, 0);
            }
            75% {
                clip: rect(45px, 9999px, 69px, 0);
            }
            80% {
                clip: rect(23px, 9999px, 85px, 0);
            }
            85% {
                clip: rect(54px, 9999px, 84px, 0);
            }
            90% {
                clip: rect(45px, 9999px, 47px, 0);
            }
            95% {
                clip: rect(37px, 9999px, 20px, 0);
            }
            100% {
                clip: rect(4px, 9999px, 91px, 0);
            }
        }
        
        @keyframes glitch-anim2 {
            0% {
                clip: rect(65px, 9999px, 100px, 0);
            }
            5% {
                clip: rect(52px, 9999px, 74px, 0);
            }
            10% {
                clip: rect(79px, 9999px, 85px, 0);
            }
            15% {
                clip: rect(75px, 9999px, 5px, 0);
            }
            20% {
                clip: rect(67px, 9999px, 61px, 0);
            }
            25% {
                clip: rect(14px, 9999px, 79px, 0);
            }
            30% {
                clip: rect(1px, 9999px, 66px, 0);
            }
            35% {
                clip: rect(86px, 9999px, 30px, 0);
            }
            40% {
                clip: rect(23px, 9999px, 98px, 0);
            }
            45% {
                clip: rect(85px, 9999px, 72px, 0);
            }
            50% {
                clip: rect(71px, 9999px, 75px, 0);
            }
            55% {
                clip: rect(2px, 9999px, 48px, 0);
            }
            60% {
                clip: rect(30px, 9999px, 16px, 0);
            }
            65% {
                clip: rect(59px, 9999px, 50px, 0);
            }
            70% {
                clip: rect(41px, 9999px, 62px, 0);
            }
            75% {
                clip: rect(2px, 9999px, 82px, 0);
            }
            80% {
                clip: rect(47px, 9999px, 73px, 0);
            }
            85% {
                clip: rect(3px, 9999px, 27px, 0);
            }
            90% {
                clip: rect(26px, 9999px, 55px, 0);
            }
            95% {
                clip: rect(42px, 9999px, 97px, 0);
            }
            100% {
                clip: rect(38px, 9999px, 49px, 0);
            }
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            h2 {
                font-size: 1.5rem;
            }
            
            .tech-grid {
                grid-template-columns: repeat(auto-fill, minmax(70px, 1fr));
            }
            
            .cyber-container {
                padding: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="cyber-container">
        <div class="cyber-header">
            <div class="glitch-container">
                <h1 class="glitch" data-text="SAMUEL BITENCOURT">SAMUEL BITENCOURT</h1>
            </div>
            <h2>JAVA DEVELOPER | TRAINEE | BACKEND</h2>
            <div class="terminal">
                <span class="neon-text">System.init()</span> - <span class="pink-text">CyberDev Profile v2.0</span> - <span class="pulse">ONLINE</span>
            </div>
        </div>

        <div class="cyber-section">
            <h3>SYSTEM PROFILE</h3>
            <p>🎓 <span class="neon-text">Formado em Análise e Desenvolvimento de Sistemas</span> - Faculdade Flamingo (2024)</p>
            <p>💼 <span class="neon-text">Atualmente atuando como Desenvolvedor Java Trainee</span></p>
            <p>📚 <span class="neon-text">Java COMPLETO Programação Orientada a Objetos</span> - Udemy</p>
            <p>🏢 <span class="neon-text">Experiência anterior como Analista de Monitoração Pleno</span> - NAVA</p>
            <p>🔭 <span class="neon-text">Estudando Spring Boot, Docker e AWS</span> para desenvolvimento backend</p>
            <p>📫 <span class="neon-text">Contato:</span> samuelb2f@outlook.com | (11) 95773-3587</p>
        </div>

        <div class="cyber-section">
            <h3>TECHNOLOGY MATRIX</h3>
            
            <h4 class="pink-text">Backend & Languages</h4>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" class="tech-icon" alt="Java">
                    <span>Java</span>
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg" class="tech-icon" alt="Spring">
                    <span>Spring</span>
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" class="tech-icon" alt="Node.js">
                    <span>Node.js</span>
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" class="tech-icon" alt="Python">
                    <span>Python</span>
                </div>
            </div>

            <h4 class="pink-text">DevOps & Cloud</h4>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" class="tech-icon" alt="Docker">
                    <span>Docker</span>
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kubernetes/kubernetes-plain.svg" class="tech-icon" alt="Kubernetes">
                    <span>K8s</span>
                </div>
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" class="tech-icon" alt="AWS">
                    <span>AWS</span>
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" class="tech-icon" alt="Linux">
                    <span>Linux</span>
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" class="tech-icon" alt="Git">
                    <span>Git</span>
                </div>
            </div>

            <h4 class="pink-text">Database & Frontend</h4>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" class="tech-icon" alt="MongoDB">
                    <span>MongoDB</span>
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" class="tech-icon" alt="MySQL">
                    <span>MySQL</span>
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" class="tech-icon" alt="React">
                    <span>React</span>
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" class="tech-icon" alt="JavaScript">
                    <span>JavaScript</span>
                </div>
            </div>
        </div>

        <div class="cyber-section">
            <h3>EDUCATION & CERTIFICATIONS</h3>
            <div class="timeline">
                <div class="timeline-item">
                    <p><span class="neon-text">Tecnólogo em Análise e Desenvolvimento de Sistemas</span> - Faculdade Flamingo</p>
                </div>
                <div class="timeline-item">
                    <p><span class="neon-text">Java COMPLETO Programação Orientada a Objetos</span> - Udemy</p>
                </div>
                <div class="timeline-item">
                    <p><span class="neon-text">Linux Fundamentals</span> - DIO</p>
                </div>
                <div class="timeline-item">
                    <p><span class="neon-text">Docker Fundamentals</span> - DIO</p>
                </div>
                <div class="timeline-item">
                    <p><span class="neon-text">Kubernetes Fundamentals</span> - DIO</p>
                </div>
                <div class="timeline-item">
                    <p><span class="neon-text">AWS Certified Cloud Practitioner</span> - Udemy</p>
                </div>
            </div>
        </div>

        <div class="cyber-section">
            <h3>PROFESSIONAL EXPERIENCE</h3>
            <div class="timeline">
                <div class="timeline-item">
                    <p><span class="neon-text">Desenvolvedor Java Trainee</span> - Atualmente</p>
                </div>
                <div class="timeline-item">
                    <p><span class="neon-text">Analista de Monitoração Pleno</span> - NAVA Technology</p>
                    <p><span class="pink-text">Fevereiro 2023 - Agosto 2025</span></p>
                    <ul style="margin-left: 1.5rem; margin-top: 0.5rem;">
                        <li>Monitoramento de sistemas corporativos e ambientes em nuvem</li>
                        <li>Identificação e escalonamento de incidentes</li>
                        <li>Automação de processos com ATM e ServiceNow</li>
                        <li>Ferramentas: Zabbix, Dynatrace, Grafana</li>
                    </ul>
                </div>
            </div>
        </div>

        <div class="cyber-section">
            <h3>CONNECTION PROTOCOLS</h3>
            <div class="contact-links">
                <a href="https://www.linkedin.com/in/samuelb2f/" target="_blank" class="cyber-btn">
                    <span>LinkedIn</span>
                </a>
                <a href="mailto:samuelb2f@outlook.com" target="_blank" class="cyber-btn">
                    <span>Email</span>
                </a>
                <a href="https://wa.me/5511957733587" target="_blank" class="cyber-btn">
                    <span>WhatsApp</span>
                </a>
            </div>
        </div>

        <div class="terminal" style="margin-top: 3rem; text-align: center;">
            <span class="neon-text">>> DESENVOLVEDOR JAVA EM FORMAÇÃO <<</span> | 
            <span class="pink-text">COMBINANDO EXPERIÊNCIA EM MONITORAMENTO COM DESENVOLVIMENTO BACKEND E CLOUD</span>
        </div>
    </div>

    <script>
        // Efeito de digitação para o terminal
        document.addEventListener('DOMContentLoaded', function() {
            const terminals = document.querySelectorAll('.terminal');
            
            terminals.forEach(terminal => {
                const originalText = terminal.textContent;
                terminal.textContent = '';
                let i = 0;
                
                function typeWriter() {
                    if (i < originalText.length) {
                        terminal.textContent += originalText.charAt(i);
                        i++;
                        setTimeout(typeWriter, 50);
                    }
                }
                
                // Inicia o efeito de digitação após um pequeno delay
                setTimeout(typeWriter, 1000);
            });
            
            // Efeito de glitch aleatório nos títulos
            setInterval(() => {
                const glitchElements = document.querySelectorAll('.glitch');
                glitchElements.forEach(el => {
                    if (Math.random() > 0.7) {
                        el.style.animation = 'none';
                        setTimeout(() => {
                            el.style.animation = '';
                        }, 100);
                    }
                });
            }, 3000);
        });
    </script>
</body>
</html>
