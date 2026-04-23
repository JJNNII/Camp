/* ============================================
   VARIABLES & THEME
   ============================================ */
:root {
    /* Colors */
    --primary-color: #a855f7;
    --secondary-color: #06b6d4;
    --accent-color: #0ea5e9;
    --dark-bg: #0a0e27;
    --darker-bg: #050812;
    --light-text: #ffffff;
    --muted-text: #9ca3af;
    --border-color: #1e293b;
    --success-color: #10b981;
    --warning-color: #f59e0b;
    --danger-color: #ef4444;
    
    /* Spacing */
    --spacing-xs: 0.5rem;
    --spacing-sm: 1rem;
    --spacing-md: 1.5rem;
    --spacing-lg: 2rem;
    --spacing-xl: 3rem;
    
    /* Transitions */
    --transition: all 0.3s ease;
    
    /* Font */
    --font-primary: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    --font-heading: 'Courier New', monospace;
}

[data-theme="light"] {
    --dark-bg: #f5f5f5;
    --darker-bg: #ffffff;
    --light-text: #0a0e27;
    --muted-text: #666666;
    --border-color: #e0e0e0;
}

/* ============================================
   GLOBAL STYLES
   ============================================ */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: var(--font-primary);
    background-color: var(--dark-bg);
    color: var(--light-text);
    line-height: 1.6;
    overflow-x: hidden;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 var(--spacing-lg);
}

/* ============================================
   TYPOGRAPHY
   ============================================ */
h1, h2, h3, h4, h5, h6 {
    font-family: var(--font-heading);
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 2px;
}

h1 {
    font-size: 3.5rem;
    margin-bottom: var(--spacing-lg);
}

h2 {
    font-size: 2.5rem;
    margin-bottom: var(--spacing-md);
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

h3 {
    font-size: 1.5rem;
    margin-bottom: var(--spacing-sm);
}

p {
    font-size: 1rem;
    margin-bottom: var(--spacing-md);
    color: var(--muted-text);
}

a {
    color: var(--secondary-color);
    text-decoration: none;
    transition: var(--transition);
}

a:hover {
    color: var(--primary-color);
}

/* ============================================
   BUTTONS
   ============================================ */
.btn {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    border: 2px solid transparent;
    border-radius: 0.5rem;
    font-size: 1rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1px;
    cursor: pointer;
    transition: var(--transition);
    text-decoration: none;
    text-align: center;
}

.btn-primary {
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: white;
    box-shadow: 0 0 20px rgba(168, 85, 247, 0.3);
}

.btn-primary:hover {
    box-shadow: 0 0 40px rgba(168, 85, 247, 0.6);
    transform: translateY(-2px);
}

.btn-secondary {
    border: 2px solid var(--secondary-color);
    color: var(--secondary-color);
    background: transparent;
}

.btn-secondary:hover {
    background: var(--secondary-color);
    color: var(--dark-bg);
    box-shadow: 0 0 30px rgba(6, 182, 212, 0.4);
}

.btn-link {
    color: var(--secondary-color);
    border-bottom: 2px solid var(--secondary-color);
    padding: 0;
    margin-top: var(--spacing-lg);
}

.btn-link:hover {
    color: var(--primary-color);
    border-bottom-color: var(--primary-color);
}

/* ============================================
   NAVIGATION
   ============================================ */
.navbar {
    position: fixed;
    top: 0;
    width: 100%;
    background: rgba(10, 14, 39, 0.95);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid var(--border-color);
    z-index: 1000;
    padding: var(--spacing-sm) 0;
}

.navbar .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.nav-brand {
    display: flex;
    align-items: center;
    gap: var(--spacing-sm);
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--light-text);
    text-transform: uppercase;
    letter-spacing: 2px;
}

.nav-brand i {
    color: var(--primary-color);
    animation: float 3s ease-in-out infinite;
}

@keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
}

.nav-menu {
    display: flex;
    list-style: none;
    gap: var(--spacing-lg);
    align-items: center;
}

.nav-menu a {
    font-size: 0.9rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1px;
    position: relative;
    transition: var(--transition);
}

.nav-menu a::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
    transition: var(--transition);
}

.nav-menu a:hover::after,
.nav-menu a.active::after {
    width: 100%;
}

.theme-toggle {
    background: none;
    border: none;
    color: var(--secondary-color);
    font-size: 1.2rem;
    cursor: pointer;
    transition: var(--transition);
}

.theme-toggle:hover {
    color: var(--primary-color);
    transform: rotate(20deg);
}

.hamburger {
    display: none;
    flex-direction: column;
    gap: 5px;
    cursor: pointer;
}

.hamburger span {
    width: 25px;
    height: 3px;
    background: var(--light-text);
    border-radius: 2px;
    transition: var(--transition);
}

/* ============================================
   HERO SECTION
   ============================================ */
.hero {
    position: relative;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    margin-top: 60px;
}

.hero-background {
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, rgba(168, 85, 247, 0.1), rgba(6, 182, 212, 0.1));
    z-index: -1;
}

.hero-background::before {
    content: '';
    position: absolute;
    width: 800px;
    height: 800px;
    background: radial-gradient(circle, rgba(168, 85, 247, 0.2), transparent);
    border-radius: 50%;
    top: -200px;
    right: -200px;
    animation: pulse 15s ease-in-out infinite;
}

.hero-background::after {
    content: '';
    position: absolute;
    width: 600px;
    height: 600px;
    background: radial-gradient(circle, rgba(6, 182, 212, 0.2), transparent);
    border-radius: 50%;
    bottom: -100px;
    left: -100px;
    animation: pulse 20s ease-in-out infinite 5s;
}

@keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.1); }
}

.neon-glow {
    position: absolute;
    width: 300px;
    height: 300px;
    background: radial-gradient(circle, var(--primary-color), transparent);
    filter: blur(80px);
    opacity: 0.3;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    animation: moveGlow 20s ease-in-out infinite;
}

@keyframes moveGlow {
    0%, 100% { transform: translate(-50%, -50%) translateX(-50px); }
    50% { transform: translate(-50%, -50%) translateX(50px); }
}

.hero-content {
    text-align: center;
    z-index: 1;
    position: relative;
}

.hero-title {
    font-size: 5rem;
    font-family: var(--font-heading);
    text-transform: uppercase;
    letter-spacing: 4px;
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color), var(--accent-color));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: var(--spacing-md);
    animation: slideUp 1s ease;
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

.hero-subtitle {
    font-size: 1.5rem;
    color: var(--muted-text);
    margin-bottom: var(--spacing-lg);
    animation: slideUp 1s ease 0.2s both;
}

.hero-buttons {
    display: flex;
    gap: var(--spacing-lg);
    justify-content: center;
    animation: slideUp 1s ease 0.4s both;
}

/* ============================================
   SECTIONS
   ============================================ */
.section-title {
    text-align: center;
    margin-bottom: var(--spacing-xl);
    position: relative;
    padding-bottom: var(--spacing-lg);
}

.section-title::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 100px;
    height: 3px;
    background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
}

.page-header {
    background: linear-gradient(135deg, rgba(168, 85, 247, 0.1), rgba(6, 182, 212, 0.1));
    padding: var(--spacing-xl) 0;
    text-align: center;
    margin-top: 60px;
    border-bottom: 1px solid var(--border-color);
}

.page-header h1 {
    margin-bottom: var(--spacing-sm);
}

.page-header p {
    font-size: 1.1rem;
    color: var(--secondary-color);
}

/* ============================================
   UPCOMING MATCHES
   ============================================ */
.upcoming-matches {
    padding: var(--spacing-xl) 0;
    background: linear-gradient(180deg, transparent, rgba(168, 85, 247, 0.05));
}

.matches-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: var(--spacing-lg);
}

.match-card {
    background: rgba(30, 41, 59, 0.5);
    border: 1px solid var(--border-color);
    border-radius: 0.75rem;
    padding: var(--spacing-lg);
    backdrop-filter: blur(10px);
    transition: var(--transition);
    position: relative;
    overflow: hidden;
}

.match-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 3px;
    background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
    opacity: 0;
    transition: var(--transition);
}

.match-card:hover {
    border-color: var(--secondary-color);
    box-shadow: 0 0 30px rgba(6, 182, 212, 0.2);
    transform: translateY(-5px);
}

.match-card:hover::before {
    opacity: 1;
}

.match-date {
    font-size: 0.85rem;
    color: var(--secondary-color);
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: var(--spacing-sm);
}

.match-teams {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin: var(--spacing-md) 0;
}

.team-name {
    font-size: 1.1rem;
    font-weight: 600;
    text-align: center;
    flex: 1;
}

.match-vs {
    color: var(--primary-color);
    font-weight: 700;
    margin: 0 var(--spacing-md);
}

.match-time {
    text-align: center;
    font-size: 0.9rem;
    color: var(--muted-text);
}

.live-badge {
    display: inline-block;
    background: var(--danger-color);
    color: white;
    padding: 0.25rem 0.75rem;
    border-radius: 20px;
    font-size: 0.75rem;
    font-weight: 700;
    text-transform: uppercase;
    margin-top: var(--spacing-sm);
    animation: pulse-badge 1s ease-in-out infinite;
}

@keyframes pulse-badge {
    0%, 100% { box-shadow: 0 0 0 0 rgba(239, 68, 68, 0.7); }
    70% { box-shadow: 0 0 0 10px rgba(239, 68, 68, 0); }
}

/* ============================================
   RANKING
   ============================================ */
.mini-ranking {
    padding: var(--spacing-xl) 0;
}

.ranking-preview {
    background: rgba(30, 41, 59, 0.5);
    border: 1px solid var(--border-color);
    border-radius: 0.75rem;
    padding: var(--spacing-lg);
    backdrop-filter: blur(10px);
    overflow-x: auto;
}

.ranking-table,
.ranking-table-full {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: var(--spacing-lg);
}

.ranking-table thead,
.ranking-table-full thead {
    background: rgba(168, 85, 247, 0.1);
    border-bottom: 2px solid var(--border-color);
}

.ranking-table th,
.ranking-table-full th {
    padding: var(--spacing-md);
    text-align: left;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-size: 0.9rem;
}

.ranking-table td,
.ranking-table-full td {
    padding: var(--spacing-md);
    border-bottom: 1px solid var(--border-color);
}

.ranking-table tbody tr,
.ranking-table-full tbody tr {
    transition: var(--transition);
}

.ranking-table tbody tr:hover,
.ranking-table-full tbody tr:hover {
    background: rgba(168, 85, 247, 0.1);
}

.ranking-position {
    font-weight: 700;
    color: var(--primary-color);
    font-size: 1.2rem;
}

.ranking-position.first {
    color: #fbbf24;
    font-size: 1.3rem;
}

.ranking-position.second {
    color: #a78bfa;
}

.ranking-position.third {
    color: #f97316;
}

.ranking-section {
    padding: var(--spacing-xl) 0;
}

.ranking-wrapper {
    background: rgba(30, 41, 59, 0.5);
    border: 1px solid var(--border-color);
    border-radius: 0.75rem;
    padding: var(--spacing-lg);
    backdrop-filter: blur(10px);
    overflow-x: auto;
}

/* ============================================
   TEAMS & PLAYERS
   ============================================ */
.teams-section,
.players-section {
    padding: var(--spacing-xl) 0;
}

.teams-grid,
.players-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: var(--spacing-lg);
}

.team-card,
.player-card {
    background: rgba(30, 41, 59, 0.5);
    border: 1px solid var(--border-color);
    border-radius: 0.75rem;
    overflow: hidden;
    transition: var(--transition);
    backdrop-filter: blur(10px);
}

.team-card:hover,
.player-card:hover {
    border-color: var(--secondary-color);
    box-shadow: 0 0 30px rgba(6, 182, 212, 0.2);
    transform: translateY(-10px);
}

.team-logo,
.player-avatar {
    width: 100%;
    height: 200px;
    background: linear-gradient(135deg, rgba(168, 85, 247, 0.2), rgba(6, 182, 212, 0.2));
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 4rem;
    border-bottom: 1px solid var(--border-color);
}

.team-info,
.player-info {
    padding: var(--spacing-lg);
}

.team-name,
.player-name {
    font-size: 1.3rem;
    font-weight: 700;
    margin-bottom: var(--spacing-sm);
    text-transform: uppercase;
    letter-spacing: 1px;
}

.team-description,
.player-team {
    font-size: 0.9rem;
    color: var(--muted-text);
    margin-bottom: var(--spacing-md);
}

.team-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: var(--spacing-sm);
    margin-top: var(--spacing-md);
}

.player-stats {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: var(--spacing-sm);
    margin-top: var(--spacing-md);
}

.stat-item {
    background: rgba(168, 85, 247, 0.1);
    padding: var(--spacing-sm);
    border-radius: 0.5rem;
    border-left: 3px solid var(--primary-color);
    text-align: center;
}

.stat-value {
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--secondary-color);
}

.stat-label {
    font-size: 0.8rem;
    color: var(--muted-text);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-top: 0.25rem;
}

.players-list {
    list-style: none;
    margin-top: var(--spacing-md);
}

.players-list li {
    padding: var(--spacing-sm) 0;
    border-bottom: 1px solid var(--border-color);
    color: var(--muted-text);
    display: flex;
    align-items: center;
}

.players-list li::before {
    content: '▸';
    color: var(--primary-color);
    margin-right: var(--spacing-sm);
}

.players-list li:last-child {
    border-bottom: none;
}

/* ============================================
   FILTER & SEARCH
   ============================================ */
.filter-bar {
    margin-bottom: var(--spacing-lg);
}

.search-input {
    width: 100%;
    max-width: 400px;
    padding: 0.75rem 1rem;
    background: rgba(30, 41, 59, 0.5);
    border: 1px solid var(--border-color);
    border-radius: 0.5rem;
    color: var(--light-text);
    font-size: 1rem;
    transition: var(--transition);
}

.search-input:focus {
    outline: none;
    border-color: var(--secondary-color);
    box-shadow: 0 0 20px rgba(6, 182, 212, 0.2);
}

.search-input::placeholder {
    color: var(--muted-text);
}

/* ============================================
   MATCHES SECTION
   ============================================ */
.matches-section {
    padding: var(--spacing-xl) 0;
}

.matches-tabs {
    display: flex;
    gap: var(--spacing-md);
    margin-bottom: var(--spacing-lg);
    border-bottom: 1px solid var(--border-color);
}

.tab-btn {
    background: none;
    border: none;
    color: var(--muted-text);
    font-size: 1rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1px;
    padding: var(--spacing-md) 0;
    cursor: pointer;
    transition: var(--transition);
    position: relative;
}

.tab-btn::after {
    content: '';
    position: absolute;
    bottom: -1px;
    left: 0;
    width: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
    transition: var(--transition);
}

.tab-btn:hover {
    color: var(--light-text);
}

.tab-btn.active {
    color: var(--secondary-color);
}

.tab-btn.active::after {
    width: 100%;
}

.tab-content {
    display: none;
    animation: fadeIn 0.3s ease;
}

.tab-content.active {
    display: block;
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

.matches-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: var(--spacing-lg);
}

.match-detail-card {
    background: rgba(30, 41, 59, 0.5);
    border: 1px solid var(--border-color);
    border-radius: 0.75rem;
    padding: var(--spacing-lg);
    backdrop-filter: blur(10px);
    transition: var(--transition);
}

.match-detail-card:hover {
    border-color: var(--secondary-color);
    box-shadow: 0 0 30px rgba(6, 182, 212, 0.2);
}

.match-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: var(--spacing-lg);
}

.match-status {
    font-size: 0.85rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.match-status.completed {
    color: var(--muted-text);
}

.match-status.upcoming {
    color: var(--secondary-color);
}

.match-teams-detail {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: var(--spacing-lg);
}

.team-side {
    flex: 1;
    text-align: center;
}

.team-side-name {
    font-size: 1.1rem;
    font-weight: 600;
    margin-bottom: var(--spacing-sm);
    text-transform: uppercase;
    letter-spacing: 1px;
}

.team-side-score {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--primary-color);
}

.match-divider {
    flex: 0 0 auto;
    margin: 0 var(--spacing-md);
    color: var(--border-color);
    font-size: 1.5rem;
}

.match-time-detail {
    text-align: center;
    font-size: 0.9rem;
    color: var(--muted-text);
    padding-top: var(--spacing-lg);
    border-top: 1px solid var(--border-color);
}

/* ============================================
   PLAYER OF THE WEEK
   ============================================ */
.player-week {
    padding: var(--spacing-xl) 0;
    background: linear-gradient(180deg, transparent, rgba(6, 182, 212, 0.05));
}

.player-week .player-card {
    max-width: 400px;
    margin: 0 auto;
}

.player-week .player-avatar {
    height: 250px;
}

.badge-player-week {
    display: inline-block;
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: white;
    padding: 0.5rem 1rem;
    border-radius: 20px;
    font-size: 0.85rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: var(--spacing-md);
}

/* ============================================
   ABOUT SECTION
   ============================================ */
.about-section {
    padding: var(--spacing-xl) 0;
}

.about-content {
    max-width: 900px;
    margin: 0 auto;
}

.content-block {
    margin-bottom: var(--spacing-xl);
    padding: var(--spacing-lg);
    background: rgba(30, 41, 59, 0.3);
    border-left: 4px solid var(--primary-color);
    border-radius: 0.5rem;
}

.content-block h2 {
    margin-bottom: var(--spacing-md);
}

.content-block p {
    color: var(--muted-text);
    line-height: 1.8;
}

.content-block p + p {
    margin-top: var(--spacing-md);
}

.rules-list {
    list-style: none;
    margin-top: var(--spacing-md);
}

.rules-list li {
    padding: var(--spacing-sm) 0;
    color: var(--muted-text);
    border-bottom: 1px solid var(--border-color);
    display: flex;
    align-items: center;
    line-height: 1.8;
}

.rules-list li:last-child {
    border-bottom: none;
}

.rules-list li::before {
    content: '✓';
    color: var(--success-color);
    margin-right: var(--spacing-md);
    font-weight: 700;
    font-size: 1.2rem;
}

.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: var(--spacing-lg);
    margin-top: var(--spacing-xl);
}

.stat-card {
    background: linear-gradient(135deg, rgba(168, 85, 247, 0.1), rgba(6, 182, 212, 0.1));
    border: 1px solid var(--border-color);
    padding: var(--spacing-lg);
    border-radius: 0.75rem;
    text-align: center;
    transition: var(--transition);
}

.stat-card:hover {
    border-color: var(--secondary-color);
    box-shadow: 0 0 30px rgba(6, 182, 212, 0.2);
}

.stat-card h3 {
    font-size: 3rem;
    color: var(--primary-color);
    margin-bottom: var(--spacing-sm);
}

.stat-card p {
    color: var(--muted-text);
    font-size: 0.95rem;
}

/* ============================================
   CONTACT SECTION
   ============================================ */
.contact-section {
    padding: var(--spacing-xl) 0;
}

.contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: var(--spacing-xl);
}

.contact-form-wrapper {
    background: rgba(30, 41, 59, 0.5);
    padding: var(--spacing-lg);
    border: 1px solid var(--border-color);
    border-radius: 0.75rem;
    backdrop-filter: blur(10px);
}

.contact-form-wrapper h2 {
    background: none;
    -webkit-text-fill-color: unset;
    background-clip: unset;
    color: var(--light-text);
    margin-bottom: var(--spacing-lg);
}

.contact-form {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-md);
}

.form-group {
    display: flex;
    flex-direction: column;
}

.form-group label {
    margin-bottom: var(--spacing-sm);
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--light-text);
}

.form-group input,
.form-group textarea {
    padding: 0.75rem 1rem;
    background: rgba(10, 14, 39, 0.5);
    border: 1px solid var(--border-color);
    border-radius: 0.5rem;
    color: var(--light-text);
    font-family: var(--font-primary);
    font-size: 1rem;
    transition: var(--transition);
    resize: vertical;
}

.form-group input:focus,
.form-group textarea:focus {
    outline: none;
    border-color: var(--secondary-color);
    box-shadow: 0 0 20px rgba(6, 182, 212, 0.2);
}

.form-group input::placeholder,
.form-group textarea::placeholder {
    color: var(--muted-text);
}

.form-message {
    padding: var(--spacing-md);
    border-radius: 0.5rem;
    text-align: center;
    font-weight: 600;
    display: none;
}

.form-message.success {
    background: rgba(16, 185, 129, 0.2);
    color: var(--success-color);
    border: 1px solid var(--success-color);
    display: block;
}

.form-message.error {
    background: rgba(239, 68, 68, 0.2);
    color: var(--danger-color);
    border: 1px solid var(--danger-color);
    display: block;
}

.contact-info {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-lg);
}

.contact-info h2 {
    background: none;
    -webkit-text-fill-color: unset;
    background-clip: unset;
    color: var(--light-text);
}

.info-block {
    background: rgba(30, 41, 59, 0.5);
    padding: var(--spacing-lg);
    border: 1px solid var(--border-color);
    border-radius: 0.75rem;
    backdrop-filter: blur(10px);
}

.info-block h3 {
    margin-bottom: var(--spacing-sm);
    display: flex;
    align-items: center;
    gap: var(--spacing-sm);
}

.info-block h3 i {
    color: var(--primary-color);
}

.info-block p {
    color: var(--muted-text);
    margin-bottom: 0;
}

.info-block a {
    color: var(--secondary-color);
}

.info-block a:hover {
    color: var(--primary-color);
}

.social-section {
    background: rgba(30, 41, 59, 0.5);
    padding: var(--spacing-lg);
    border: 1px solid var(--border-color);
    border-radius: 0.75rem;
    backdrop-filter: blur(10px);
}

.social-section h3 {
    margin-bottom: var(--spacing-md);
}

.social-links-large {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-sm);
}

.social-links-large a {
    display: flex;
    align-items: center;
    gap: var(--spacing-sm);
    padding: var(--spacing-sm);
    background: rgba(10, 14, 39, 0.5);
    border-radius: 0.5rem;
    transition: var(--transition);
    color: var(--secondary-color);
}

.social-links-large a:hover {
    background: rgba(168, 85, 247, 0.1);
    color: var(--primary-color);
}

/* ============================================
   FOOTER
   ============================================ */
.footer {
    background: rgba(10, 14, 39, 0.95);
    border-top: 1px solid var(--border-color);
    padding: var(--spacing-xl) 0 var(--spacing-lg);
    margin-top: var(--spacing-xl);
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: var(--spacing-xl);
    margin-bottom: var(--spacing-xl);
}

.footer-section h3 {
    margin-bottom: var(--spacing-md);
    color: var(--light-text);
}

.footer-section p {
    color: var(--muted-text);
    margin-bottom: 0;
}

.footer-section ul {
    list-style: none;
}

.footer-section ul li {
    padding: 0.5rem 0;
}

.footer-section a {
    color: var(--muted-text);
    transition: var(--transition);
}

.footer-section a:hover {
    color: var(--secondary-color);
}

.social-links {
    display: flex;
    gap: var(--spacing-md);
}

.social-links a {
    width: 40px;
    height: 40px;
    background: rgba(168, 85, 247, 0.1);
    border: 1px solid var(--border-color);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: var(--transition);
}

.social-links a:hover {
    background: rgba(168, 85, 247, 0.3);
    border-color: var(--primary-color);
    transform: translateY(-3px);
}

.footer-bottom {
    text-align: center;
    padding-top: var(--spacing-lg);
    border-top: 1px solid var(--border-color);
    color: var(--muted-text);
}

/* ============================================
   RESPONSIVE DESIGN
   ============================================ */
@media (max-width: 768px) {
    .container {
        padding: 0 var(--spacing-md);
    }

    .hero {
        height: 70vh;
        margin-top: 60px;
    }

    .hero-title {
        font-size: 3rem;
    }

    .hero-subtitle {
        font-size: 1.2rem;
    }

    .hero-buttons {
        flex-direction: column;
    }

    h1 {
        font-size: 2.5rem;
    }

    h2 {
        font-size: 1.75rem;
    }

    .nav-menu {
        display: none;
        position: absolute;
        top: 60px;
        left: 0;
        width: 100%;
        background: rgba(10, 14, 39, 0.98);
        flex-direction: column;
        gap: 0;
        padding: var(--spacing-md) 0;
        border-bottom: 1px solid var(--border-color);
    }

    .nav-menu.active {
        display: flex;
    }

    .nav-menu li {
        border-bottom: 1px solid var(--border-color);
        padding: var(--spacing-md) var(--spacing-lg);
    }

    .hamburger {
        display: flex;
    }

    .hamburger.active span:nth-child(1) {
        transform: rotate(45deg) translate(8px, 8px);
    }

    .hamburger.active span:nth-child(2) {
        opacity: 0;
    }

    .hamburger.active span:nth-child(3) {
        transform: rotate(-45deg) translate(7px, -7px);
    }

    .matches-grid,
    .teams-grid,
    .players-grid {
        grid-template-columns: 1fr;
    }

    .contact-grid {
        grid-template-columns: 1fr;
    }

    .team-side-score {
        font-size: 2rem;
    }

    .search-input {
        max-width: 100%;
    }

    .matches-tabs {
        flex-wrap: wrap;
    }
}

@media (max-width: 480px) {
    .hero-title {
        font-size: 2rem;
    }

    .hero-subtitle {
        font-size: 1rem;
    }

    h1 {
        font-size: 2rem;
    }

    h2 {
        font-size: 1.5rem;
    }

    h3 {
        font-size: 1.2rem;
    }

    .btn {
        padding: 0.6rem 1.2rem;
        font-size: 0.9rem;
    }

    .team-stats,
    .player-stats {
        grid-template-columns: 1fr;
    }

    .stats-grid {
        grid-template-columns: 1fr 1fr;
    }

    .stat-card h3 {
        font-size: 2rem;
    }

    .match-teams-detail {
        flex-direction: column;
        gap: var(--spacing-lg);
    }

    .match-divider {
        transform: rotate(90deg);
    }
}

/* ============================================
   COUNTDOWN TIMER
   ============================================ */
.countdown {
    display: flex;
    gap: var(--spacing-sm);
    justify-content: center;
    margin-top: var(--spacing-md);
    font-size: 0.9rem;
}

.countdown-item {
    background: rgba(168, 85, 247, 0.1);
    padding: 0.5rem 0.75rem;
    border-radius: 0.5rem;
    border: 1px solid var(--border-color);
    min-width: 60px;
    text-align: center;
}

.countdown-value {
    font-weight: 700;
    color: var(--primary-color);
    font-size: 1.2rem;
}

.countdown-label {
    font-size: 0.7rem;
    text-transform: uppercase;
    color: var(--muted-text);
}
