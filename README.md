<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>E-Portfolio • Mohamed Junior Diaby</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=JetBrains+Mono:wght@400;700&display=swap');

        /* --- STYLES GÉNÉRAUX --- */
        body {
            margin: 0;
            font-family: 'Poppins', sans-serif;
            background: #0b0f19;
            color: #f1f5f9;
            overflow-x: hidden;
        }
        main {
            max-width: 1200px;
            margin: 30px auto;
            padding: 20px;
        }
        .page { display: none; }
        .active { display: block; }
        
        /* --- EFFET NÉON & CYBERPUNK --- */
        h1, h2, h3 {
            text-transform: uppercase;
            letter-spacing: 1.5px;
            font-family: 'JetBrains Mono', monospace;
        }
        h1 {
            color: #00f0ff;
            text-shadow: 0 0 10px rgba(0, 240, 255, 0.6), 0 0 20px rgba(0, 240, 255, 0.3);
        }
        h2 {
            color: #ff007b;
            text-shadow: 0 0 10px rgba(255, 0, 123, 0.6);
            margin-bottom: 25px;
            border-bottom: 2px solid rgba(255, 0, 123, 0.3);
            padding-bottom: 10px;
        }
        h3 {
            color: #00f0ff;
            font-size: 1.1rem;
        }

        /* --- BACKGROUND & HEADER --- */
        .anime-bg {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            z-index: -1;
            background: linear-gradient(135deg, #0b0f19 0%, #1a102f 100%);
            opacity: 0.95;
        }

        header {
            background: rgba(13, 17, 28, 0.85);
            backdrop-filter: blur(12px);
            padding: 15px 30px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            box-shadow: 0 4px 20px rgba(0, 240, 255, 0.15);
            border-bottom: 1px solid rgba(0, 240, 255, 0.3);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        .header-left {
            display: flex;
            align-items: center;
            gap: 20px;
        }
        .social-link {
            text-decoration: none;
            color: #00f0ff;
            font-size: 1.3rem;
            transition: 0.3s;
        }
        .social-link:hover {
            color: #ff007b;
            text-shadow: 0 0 10px #ff007b;
        }

        nav {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }
        nav a {
            text-decoration: none;
            color: #94a3b8;
            font-weight: 600;
            font-size: 0.9rem;
            transition: 0.3s;
            padding: 6px 12px;
            border-radius: 6px;
        }
        nav a:hover, nav a.active-link {
            color: #fff;
            background: rgba(0, 240, 255, 0.1);
            color: #00f0ff;
            box-shadow: 0 0 10px rgba(0, 240, 255, 0.2);
        }

        /* --- CARTES --- */
        .card {
            background: rgba(17, 24, 39, 0.75);
            border-radius: 14px;
            padding: 30px;
            margin-bottom: 25px;
            border: 1px solid rgba(0, 240, 255, 0.2);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
            backdrop-filter: blur(8px);
            transition: 0.4s;
        }
        .card:hover {
            border-color: rgba(0, 240, 255, 0.5);
            box-shadow: 0 8px 32px rgba(0, 240, 255, 0.15);
        }
        
        .profile {
            display: flex;
            align-items: center;
            gap: 30px;
            flex-wrap: wrap;
        }
        .anime-illustration {
            width: 180px;
            height: auto;
            border-radius: 12px;
            box-shadow: 0 0 20px rgba(255, 0, 170, 0.4);
            border: 2px solid rgba(255, 0, 170, 0.6);
            animation: float 4s ease-in-out infinite;
        }
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-8px); }
            100% { transform: translateY(0px); }
        }

        .btn {
            display: inline-block;
            background: linear-gradient(90deg, #00f0ff, #ff007b);
            padding: 12px 24px;
            border-radius: 8px;
            color: #fff;
            text-decoration: none;
            margin-top: 15px;
            font-weight: 600;
            transition: 0.3s;
            border: none;
            cursor: pointer;
            box-shadow: 0 0 15px rgba(0, 240, 255, 0.3);
        }
        .btn:hover { 
            opacity: 0.9;
            transform: translateY(-2px);
            box-shadow: 0 0 25px rgba(255, 0, 123, 0.5);
        }

        /* --- SYSTÈMES DE COMPÉTENCES HACKI --- */
        .hacker-skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        .skill-module {
            background: rgba(13, 17, 28, 0.9);
            border: 1px solid rgba(0, 240, 255, 0.25);
            border-radius: 10px;
            padding: 20px;
            position: relative;
            overflow: hidden;
            transition: 0.3s;
        }
        .skill-module::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 4px; height: 100%;
            background: linear-gradient(to bottom, #00f0ff, #ff007b);
        }
        .skill-module:hover {
            transform: translateY(-3px);
            border-color: #00f0ff;
            box-shadow: 0 0 15px rgba(0, 240, 255, 0.2);
        }
        .skill-code {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.75rem;
            color: #ff007b;
            margin-bottom: 5px;
            text-transform: uppercase;
        }
        .skill-title {
            font-size: 1rem;
            font-weight: 600;
            color: #fff;
            margin-bottom: 10px;
        }
        .skill-desc {
            font-size: 0.85rem;
            color: #94a3b8;
            line-height: 1.5;
        }

        /* --- GRILLE CERTIFICATIONS & PROJETS --- */
        .grid-2 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        .cert-card, .project-card {
            background: rgba(13, 17, 28, 0.8);
            border-radius: 10px;
            padding: 20px;
            border: 1px solid rgba(0, 240, 255, 0.2);
            transition: 0.3s;
        }
        .cert-card:hover, .project-card:hover {
            transform: translateY(-3px);
            border-color: #ff007b;
            box-shadow: 0 0 15px rgba(255, 0, 123, 0.2);
        }
        .cert-card a, .project-card a {
            color: #00f0ff;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
        }
        .cert-card a:hover { color: #ff007b; }

        /* --- RESPONSIVE --- */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                align-items: flex-start;
                gap: 15px;
            }
            nav { width: 100%; justify-content: space-between; }
            .profile { flex-direction: column; text-align: center; }
            .anime-illustration { margin: 0 auto; }
        }
    </style>
</head>
<body>

<div class="anime-bg"></div>

<header>
    <div class="header-left">
        <h3 style="color:#00f0ff; margin:0; font-family:'JetBrains Mono';">root@diaby:~#</h3>
        <div class="social-links-container">
            <a href="https://github.com/mohamedjuniordiaby111-web/eportfolio" target="_blank" class="social-link" title="GitHub">💻</a>
            <a href="https://www.linkedin.com/in/mohamed-junior-diaby-64a016370/" target="_blank" class="social-link" title="LinkedIn">🔗</a>
        </div>
    </div>
    <nav id="nav-links">
        <a href="#" onclick="showPage('home', this)" class="active-link">Accueil</a>
        <a href="#" onclick="showPage('competences', this)">Compétences Hacki</a>
        <a href="#" onclick="showPage('certifications', this)">Certifications</a>
        <a href="#" onclick="showPage('projets', this)">Projets</a>
        <a href="#" onclick="showPage('veille', this)">Veille</a>
        <a href="#" onclick="showPage('contact', this)">Contact</a>
        <a href="#" onclick="showPage('synt', this)">Synthèse</a>
    </nav>
</header>

<main>
    <!-- ACCUEIL -->
    <section id="home" class="page active card">
        <div class="profile">
            <img class="anime-illustration" src="https://www.univers-otaku.com/wp-content/uploads/2018/04/products-mug-mug-hunter-x-hunter-hisoka-2-scaled.jpg" alt="Avatar">
            <div>
                <h1>Mohamed Junior Diaby Takoue</h1>
                <p style="color: #00f0ff; font-family: 'JetBrains Mono'; font-weight: 600;">BTS SIO 1ère année — Option Systèmes et Réseaux (SISR)</p>
                <p style="color: #94a3b8;">Ancienne filière : STMG Gestion Finance</p>
                <p style="margin-top: 15px;">Bienvenue sur mon e-portfolio sécurisé. Navigation sous architecture de pointe et administration système avancée.</p>
            </div>
        </div>
    </section>

    <!-- COMPÉTENCES HACKI -->
    <section id="competences" class="page card">
        <h2>⚡ Matrice des Compétences (Hacki Edition)</h2>
        <p style="color: #94a3b8; margin-bottom: 25px;">Référentiel complet des compétences techniques acquises et maîtrisées dans le cadre de la formation SISR :</p>
        
        <div class="hacker-skills-container">
            <div class="skill-module">
                <div class="skill-code">MODULE #01 - ARCHITECTURE & DESIGN</div>
                <div class="skill-title">Architecture & Cahier des Charges</div>
                <div class="skill-desc">Maîtrise des schémas d'architecture fonctionnelle, d'infrastructure/système (VM, OS) et des schémas logiques/physiques (adressage IP, rôles des serveurs).</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #02 - IDENTITÉ & SÉCURITÉ ACCÈS</div>
                <div class="skill-title">Authentification & Contrôle</div>
                <div class="skill-desc">Mise en place de services d'authentification (portail captif), gestion des comptes et déploiement d'annuaires sécurisés.</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #03 - DATA & DATABASES</div>
                <div class="skill-title">SGBD (MariaDB / SQL)</div>
                <div class="skill-desc">Installation, configuration et administration de bases de données relationnelles sécurisées pour les applications métiers.</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #04 - RÉSEAUX & INTERNET</div>
                <div class="skill-title">Accès Sécurisé & Périmètres</div>
                <div class="skill-desc">Sécurisation des accès Internet, cloisonnement par périmètres de sécurité, gestion du routage, pare-feux (UFW, PfSense) et analyse des flux.</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #05 - COLLABORATION & CLOUD</div>
                <div class="skill-title">Environnement Collaboratif & Mobilité</div>
                <div class="skill-desc">Déploiement de plateformes collaboratives (NextCloud) et connexion sécurisée de terminaux mobiles (Wi-Fi, profils).</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #06 - SYSTÈMES MIXTES</div>
                <div class="skill-title">Serveurs Linux & Windows AD / GPO</div>
                <div class="skill-desc">Administration croisée de serveurs Linux et Windows Server (Active Directory, Stratégies de Groupe - GPO).</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #07 - PROTECTION & RESILIENCE</div>
                <div class="skill-title">Sauvegarde & Continuité de Service</div>
                <div class="skill-desc">Stratégies de backup multi-niveaux (Proxmox VM, BackupManager, Barracuda Cloud), haute disponibilité (Proxmox HA) et tolérance de panne.</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #08 - GESTION DES DROITS</div>
                <div class="skill-title">Habilitations & Droits Systèmes</div>
                <div class="skill-desc">Contrôle granulaire des ressources sécurisées via les lignes de commande avancées (chmod, chown) et gestion des privilèges.</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #09 - ITSM & PATRIMOINE</div>
                <div class="skill-title">Gestion des Incidents & Patrimoine (GLPI)</div>
                <div class="skill-desc">Suivi des incidents, gestion automatisée du parc informatique, inventaire et exploitation des modules GLPI.</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #10 - CYBERDÉFENSE & TRACE</div>
                <div class="skill-title">IDS/IPS, Analyse de Trafic & Trames</div>
                <div class="skill-desc">Détection d'intrusions (Snort, Suricata), analyse de trafic réseau (ntopNG), capture et filtrage de trames (Wireshark).</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #11 - CRYPTOGRAPHIE & SÉCURITÉ</div>
                <div class="skill-title">(Dé)Chiffrement & Robustesse</div>
                <div class="skill-desc">Chiffrement de chaînes, fichiers, répertoires, disques et flux (SSL/SSH) avec GPG, gocryptfs, et tests de robustesse des mots de passe (/etc/passwd).</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #12 - ADMINISTRATION & CONFIG</div>
                <div class="skill-title">Gestion des Configurations & Scripting</div>
                <div class="skill-desc">Automatisation et gestion des configurations (Puppet), administration distante sécurisée (SSH, RDP Remmina) et scripts d'administration (Bash/Python/PowerShell).</div>
            </div>

            <div class="skill-module">
                <div class="skill-code">MODULE #13 - SUPERVISION & DÉPLOIEMENT</div>
                <div class="skill-title">Supervision & Déploiement de Masse</div>
                <div class="skill-desc">Surveillance de la qualité, de la sécurité et alertes proactives (Nagios, Zabbix), déploiement d'images système (WDS, Clonezilla) et répartition de charges.</div>
            </div>
        </div>
    </section>

    <!-- CERTIFICATIONS -->
    <section id="certifications" class="page card">
        <h2>🏆 Certifications</h2>
        <div class="grid-2">
            <div class="cert-card"><a href="Cisco_Packet_Tracer.pdf.pdf" target="_blank">Cisco Packet Tracer</a></div>
            <div class="cert-card"><a href="EBIOS.pdf.pdf" target="_blank">EBIOS (Sécurité)</a></div>
            <div class="cert-card"><a href="Exploring.pdf.pdf" target="_blank">Exploring Networking</a></div>
            <div class="cert-card"><a href="Introduction_to_Packet_Tracer.pdf.pdf" target="_blank">Intro to Packet Tracer</a></div>
        </div>
    </section>

    <!-- PROJETS -->
    <section id="projets" class="page card">
        <h2>🚀 Réalisations Techniques</h2>
        <div class="grid-2">
            <div class="project-card">
                <h3>🌐 Projet Billys 140</h3>
                <p>Création d'un site web responsive avec intégration avancée, design néon et interactivité front-end.</p>
                <a href="#" class="btn" style="margin-top:10px; padding:8px 15px; font-size:0.85rem;">Voir le projet</a>
            </div>
            <div class="project-card">
                <h3>💻 Labo Infrastructure SISR</h3>
                <p>Mise en place d'un réseau virtualisé (Proxmox, Debian, Windows Server, DHCP, DNS, filtrage).</p>
                <a href="#" class="btn" style="margin-top:10px; padding:8px 15px; font-size:0.85rem;">Rapport Technique</a>
            </div>
        </div>
    </section>

    <!-- VEILLE -->
    <section id="veille" class="page card">
        <h2>💡 Veille Technologique</h2>
        <div style="background:rgba(13,17,28,0.9); padding:20px; border-left: 4px solid #ff007b; border-radius:8px;">
            <h3>Focus du moment : La démocratisation des attaques par Deepfake audio/vidéo et l'IAM (Identity and Access Management) Zero Trust</h3>
            <p style="font-size: 0.95em; margin-top: 10px; color: #94a3b8; line-height: 1.6;">
                Les technologies de synthèse vocale et d'hypermise en scène par IA (Deepfakes) progressent à un rythme fulgurant, devenant l'arme privilégiée pour le "Spear Phishing" et le contournement de l'authentification biométrique/vocale en entreprise. Face à cette menace, la veille met en lumière l'obligation pour les administrateurs systèmes et réseaux d'adopter des architectures de type <strong>Zero Trust</strong> ("Ne jamais faire confiance, toujours vérifier") combinées à des protocoles d'authentification multifacteur (MFA) durcis, résistant aux attaques par rebond de session et aux usurpations d'identité en temps réel.
            </p>
            <p style="font-size: 0.85em; margin-top: 15px; color: #00f0ff; font-family:'JetBrains Mono';">*Dernière analyse et mise à jour de la veille : Mai 2026*</p>
        </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" class="page card">
        <h2>📧 Contact Professionnel</h2>
        <p>Ouvert aux opportunités de stage, d'alternance et d'échanges techniques.</p>
        <button class="btn" onclick="showContact()">Afficher mes coordonnées</button>
        <div id="contact-info" style="display:none; margin-top:20px; border-left: 3px solid #00f0ff; padding-left:15px; font-family:'JetBrains Mono';">
            <p><strong>Téléphone :</strong> 06-05-92-13-70</p>
            <p><strong>Email :</strong> mohamedjuniordiaby111@gmail.com</p>
        </div>
    </section>

    <!-- SYNTHESE -->
    <section id="synt" class="page card">
        <h2>📊 Tableau de Synthèse E4</h2>
        <p>Téléchargez ci-dessous le fichier officiel du tableau de synthèse des réalisations professionnelles pour l'épreuve E4 du BTS SIO :</p>
        <a href="tableaudesynthese.xlsx" download>
            <button class="btn">📥 Télécharger mon tableau de synthèse (.xlsx)</button>
        </a>
    </section>
</main>

<script>
    function showPage(id, element) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        document.getElementById(id).classList.add('active');

        document.querySelectorAll('#nav-links a').forEach(a => a.classList.remove('active-link'));
        if (element) {
            element.classList.add('active-link');
        }
    }

    function showContact() {
        const box = document.getElementById('contact-info');
        const button = document.querySelector('#contact .btn');
        if (box.style.display === 'none' || box.style.display === '') {
            box.style.display = 'block';
            button.textContent = 'Masquer mes coordonnées';
        } else {
            box.style.display = 'none';
            button.textContent = 'Afficher mes coordonnées';
        }
    }
</script>

</body>
</html>
