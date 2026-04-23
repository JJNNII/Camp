<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rocket League Championship</title>

<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background: #000;
    color: #fff;
    font-family: 'Orbitron', sans-serif;
    overflow-x: hidden;
}

/* HEADER */
header {
    position: fixed;
    width: 100%;
    top: 0;
    background: rgba(0,0,0,0.8);
    backdrop-filter: blur(10px);
    display: flex;
    justify-content: space-between;
    padding: 20px 40px;
    border-bottom: 1px solid #00ff88;
    z-index: 1000;
}

header h1 {
    color: #00ff88;
    text-shadow: 0 0 10px #00ff88;
}

nav a {
    margin-left: 25px;
    text-decoration: none;
    color: #fff;
    transition: 0.3s;
}

nav a:hover {
    color: #ffdd00;
}

/* HERO */
.hero {
    height: 100vh;
    background: radial-gradient(circle at center, #003300, #000);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;

    animation: fadeIn 2s ease;
}

.hero h2 {
    font-size: 5rem;
    color: #00ff88;
    text-shadow: 0 0 20px #00ff88, 0 0 40px #00ff88;
}

.hero p {
    margin-top: 15px;
    color: #ffdd00;
    font-size: 1.5rem;
}

/* BUTTON */
.btn {
    margin-top: 30px;
    padding: 12px 30px;
    border: 2px solid #00ff88;
    color: #00ff88;
    text-decoration: none;
    transition: 0.3s;
}

.btn:hover {
    background: #00ff88;
    color: #000;
}

/* SECTIONS */
section {
    padding: 100px 40px;
    text-align: center;
}

/* CARDS */
.cards {
    display: flex;
    justify-content: center;
    gap: 30px;
    flex-wrap: wrap;
}

.card {
    background: rgba(255,255,255,0.05);
    border: 1px solid #00ff88;
    padding: 30px;
    width: 220px;
    border-radius: 15px;
    backdrop-filter: blur(10px);
    transition: 0.3s;
}

.card:hover {
    transform: translateY(-10px) scale(1.05);
    border-color: #ffdd00;
}

/* RANKING */
.ranking li {
    font-size: 1.5rem;
    margin: 10px 0;
}

/* FOOTER */
footer {
    padding: 30px;
    background: #050505;
    border-top: 1px solid #00ff88;
}

/* ANIMAÇÕES */
@keyframes fadeIn {
    from {opacity: 0; transform: translateY(30px);}
    to {opacity: 1; transform: translateY(0);}
}

/* SCROLL EFFECT */
.reveal {
    opacity: 0;
    transform: translateY(50px);
    transition: 1s;
}

.reveal.active {
    opacity: 1;
    transform: translateY(0);
}

/* RESPONSIVO */
@media(max-width: 768px){
    .hero h2 { font-size: 2.5rem; }
}
</style>
</head>

<body>

<header>
    <h1>🏆 RL Championship</h1>
    <nav>
        <a href="#sobre">Sobre</a>
        <a href="#times">Times</a>
        <a href="#ranking">Ranking</a>
    </nav>
</header>

<section class="hero">
    <h2>IMBR CAMPEÕES</h2>
    <p>Domínio absoluto no cenário competitivo</p>
    <a href="#times" class="btn">Ver Times</a>
</section>

<section id="sobre" class="reveal">
    <h2>Sobre o Campeonato</h2>
    <p>
        O principal torneio de Rocket League do Brasil,
        reunindo os melhores jogadores e equipes do cenário.
    </p>
</section>

<section id="times" class="reveal">
    <h2>Times Participantes</h2>
    <div class="cards">
        <div class="card">
            <h3>IMBR</h3>
            <p>🏆 Campeão</p>
        </div>
        <div class="card">
            <h3>FURIA</h3>
            <p>Vice</p>
        </div>
        <div class="card">
            <h3>Team Liquid</h3>
            <p>Top 3</p>
        </div>
    </div>
</section>

<section id="ranking" class="reveal">
    <h2>Ranking Final</h2>
    <ol class="ranking">
        <li>🥇 IMBR</li>
        <li>🥈 FURIA</li>
        <li>🥉 Team Liquid</li>
    </ol>
</section>

<footer>
    <p>© 2026 Rocket League Championship</p>
</footer>

<script>
/* ANIMAÇÃO AO SCROLL */
window.addEventListener("scroll", () => {
    const reveals = document.querySelectorAll(".reveal");
    reveals.forEach(el => {
        const windowHeight = window.innerHeight;
        const elementTop = el.getBoundingClientRect().top;
        if (elementTop < windowHeight - 100) {
            el.classList.add("active");
        }
    });
});
</script>

</body>
</html>
