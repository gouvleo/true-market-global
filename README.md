<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TrueMarketGlobal</title>
<style>
    /* Reset e básico */
    * { margin:0; padding:0; box-sizing:border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
    body { line-height: 1.6; background-color: #f4f4f4; color: #333; scroll-behavior: smooth; }
    a { text-decoration: none; color: inherit; }

    /* Navbar */
    nav {
        position: fixed; top:0; left:0; width:100%;
        display: flex; justify-content: center; background-color: rgba(0,0,0,0.7);
        padding: 12px 0; z-index: 1000; transition: background 0.3s;
    }
    nav a {
        margin: 0 20px; color: #fff; font-weight: bold; transition: color 0.3s;
    }
    nav a:hover { color: #f0a500; }

    /* Hero / Parallax */
    header {
        height: 100vh;
        background: url('https://i.imgur.com/8XG6ZsM.jpg') no-repeat center center/cover;
        display: flex; justify-content: center; align-items: center; text-align: center; color: #fff;
        position: relative; overflow: hidden;
        perspective: 1000px;
    }
    header::before {
        content: ""; position: absolute; top:0; left:0; width:100%; height:100%;
        background: rgba(0,0,0,0.5);
    }
    .hero-content {
        position: relative; z-index: 2; animation: fadeInUp 2s ease-out;
        transform-style: preserve-3d;
    }
    header h1 { font-size: 3rem; margin-bottom: 20px; }
    header p { font-size: 1.5rem; }

    @keyframes fadeInUp { from {opacity:0; transform: translateY(50px);} to {opacity:1; transform: translateY(0);} }

    /* Sections */
    section {
        padding: 80px 20px; max-width: 1000px; margin: auto; opacity: 0; transform: translateY(50px); transition: all 1s ease;
    }
    section.visible { opacity:1; transform: translateY(0); }
    section h2 { text-align: center; margin-bottom: 40px; font-size: 2.2rem; color: #333; }
    section p { text-align: center; font-size: 1.1rem; color: #555; }

    /* Team */
    .team-container {
        display: flex; flex-wrap: wrap; justify-content: center; gap: 40px;
    }
    .team-member {
        text-align: center; width: 200px; transform: translateY(50px) rotateY(15deg); opacity:0; transition: all 0.8s ease;
    }
    .team-member.visible { transform: translateY(0) rotateY(0deg); opacity:1; }
    .team-member img {
        width: 200px; height: 200px; object-fit: cover; border-radius: 50%; margin-bottom: 15px;
        box-shadow: 0 6px 15px rgba(0,0,0,0.3); transition: transform 0.3s;
    }
    .team-member img:hover { transform: scale(1.05) rotateY(5deg); }
    .team-member h3 { font-size: 1.2rem; margin-bottom: 5px; }
    .team-member p { font-size: 1rem; color: #777; }

    /* Services */
    .services-container {
        display: flex; flex-wrap: wrap; justify-content: center; gap: 30px;
    }
    .service {
        background-color: #fff; padding: 25px; width: 260px; border-radius: 10px;
        box-shadow: 0 6px 15px rgba(0,0,0,0.1); text-align: center; transform: rotateX(15deg); opacity:0;
        transition: transform 0.6s, box-shadow 0.6s, opacity 0.6s;
    }
    .service.visible { transform: rotateX(0deg); opacity:1; }
    .service:hover { transform: translateY(-10px) rotateX(0deg); box-shadow: 0 10px 25px rgba(0,0,0,0.2); }
    .service h3 { margin-bottom: 10px; color: #333; }
    .service p { color: #666; font-size: 0.95rem; }

    /* Contact */
    form {
        display: flex; flex-direction: column; max-width: 500px; margin: auto; gap: 15px;
    }
    input, textarea {
        padding: 12px; border-radius: 5px; border: 1px solid #ccc; font-size: 1rem; transition: border 0.3s;
    }
    input:focus, textarea:focus { border-color: #f0a500; outline: none; }
    button {
        padding: 12px; border: none; background-color: #f0a500; color: #fff; font-size: 1rem; border-radius: 5px; cursor: pointer;
        transition: background-color 0.3s;
    }
    button:hover { background-color: #d18e00; }

    /* Floating Contact Button */
    .contact-button {
        position: fixed; bottom: 30px; right: 30px;
        background-color: #f0a500; color: #fff; padding: 15px 20px; border-radius: 50px;
        box-shadow: 0 6px 15px rgba(0,0,0,0.3); cursor: pointer; font-weight: bold; transition: transform 0.3s;
        z-index: 1000;
    }
    .contact-button:hover { transform: scale(1.1); }

    /* Footer */
    footer { text-align: center; padding: 20px; background-color: #222; color: #fff; }

    /* Responsive */
    @media(max-width:768px){
        .team-container, .services-container { flex-direction: column; align-items: center; }
        header h1 { font-size: 2.2rem; }
        header p { font-size: 1.2rem; }
    }
</style>
</head>
<body>

<!-- Navbar -->
<nav>
    <a href="#home">Home</a>
    <a href="#about">Sobre</a>
    <a href="#team">Equipe</a>
    <a href="#services">Serviços</a>
    <a href="#contact">Contato</a>
</nav>

<!-- Hero -->
<header id="home">
    <div class="hero-content">
        <h1>TrueMarketGlobal</h1>
        <p>Transformando conexões em oportunidades globais</p>
    </div>
</header>

<!-- About -->
<section id="about">
    <h2>Sobre a TrueMarketGlobal</h2>
    <p>A TrueMarketGlobal é uma empresa líder em intermediação de commodities, conectando fornecedores e compradores em escala internacional com confiança, transparência e excelência operacional.</p>
</section>

<!-- Team -->
<section id="team">
    <h2>Equipe</h2>
    <div class="team-container">
        <div class="team-member">
            <img src="https://i.imgur.com/3G7h6fX.jpg" alt="Leandro Gouveia">
            <h3>Leandro Gouveia</h3>
            <p>Co-fundador & Diretor Regional LATAM</p>
        </div>
        <div class="team-member">
            <img src="https://i.imgur.com/qIuF2gk.jpg" alt="Alexander Topolnytskyy">
            <h3>Alexander Topolnytskyy</h3>
            <p>Fundador & Diretor Geral</p>
        </div>
    </div>
</section>

<!-- Services -->
<section id="services">
    <h2>Serviços</h2>
    <div class="services-container">
        <div class="service">
            <h3>Intermediação Global</h3>
            <p>Conectamos compradores e fornecedores internacionais de forma segura e eficiente.</p>
        </div>
        <div class="service">
            <h3>Consultoria de Mercado</h3>
            <p>Oferecemos insights estratégicos para otimizar operações comerciais globais.</p>
        </div>
        <div class="service">
            <h3>Gestão de Logística</h3>
            <p>Planejamos toda a cadeia logística para garantir entrega e qualidade.</p>
        </div>
    </div>
</section>

<!-- Contact -->
<section id="contact">
    <h2>Contato</h2>
    <form id="contactForm">
        <input type="text" name="name" placeholder="Seu nome" required>
        <input type="email" name="email" placeholder="Seu email" required>
        <textarea name="message" rows="5" placeholder="Sua mensagem" required></textarea>
        <button type="submit">Enviar</button>
    </form>
</section>

<!-- Floating Contact Button -->
<div class="contact-button" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'});">
    Contato
</div>

<!-- Footer -->
<footer>
    <p>&copy; 2025 TrueMarketGlobal. Todos os direitos reservados.</p>
</footer>

<script>
    // Formulário simples
    document.getElementById('contactForm').addEventListener('submit', function(e){
        e.preventDefault();
        alert('Obrigado pelo contato! Entraremos em contato em breve.');
        this.reset();
    });

    // Scroll animations
    const sections = document.querySelectorAll('section');
    const teamMembers = document.querySelectorAll('.team-member');
    const services = document.querySelectorAll('.service');

    const observer = new IntersectionObserver(entries => {
        entries.forEach(entry => {
            if(entry.isIntersecting){
                entry.target.classList.add('visible');
            }
        });
    }, { threshold: 0.2 });

    sections.forEach(section => observer.observe(section));
    teamMembers.forEach(member => observer.observe(member));
    services.forEach(service => observer.observe(service));

    // Parallax effect on scroll for hero
    window.addEventListener('scroll', () => {
        const scrolled = window.scrollY;
        const header = document.querySelector('header');
        header.style.backgroundPositionY = `${scrolled * 0.5}px`;
    });
</script>

</body>
</html>
