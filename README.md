<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Minecraft World | Ortiqjon Xasanov</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', 'Minecraft', 'Courier New', monospace;
            background: #0d1f0a;
            background-image: 
                linear-gradient(45deg, #1a3a12 1px, transparent 1px),
                linear-gradient(-45deg, #1a3a12 1px, transparent 1px);
            background-size: 40px 40px;
            color: #e8f0e0;
            line-height: 1.5;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 15px 20px;
        }

        header {
            background: #2b2b2b;
            border-bottom: 6px solid #6b8c42;
            box-shadow: 0 8px 0 #1a2a0f;
            margin-bottom: 20px;
        }

        .header-flex {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
        }

        .logo h1 {
            font-size: 2rem;
            color: #a0e060;
            text-shadow: 3px 3px 0 #2d5a1a;
            letter-spacing: 2px;
        }

        .logo p {
            color: #b8d9a6;
            font-size: 0.85rem;
        }

        .user-card {
            background: #1f2a1a;
            padding: 10px 25px;
            border-radius: 0;
            border-left: 5px solid #f5b042;
            border-right: 5px solid #f5b042;
            border-top: 2px solid #8aac6b;
            border-bottom: 2px solid #8aac6b;
            font-weight: bold;
            font-size: 1.2rem;
            font-family: monospace;
            box-shadow: 0 3px 0 #3a4a2a;
        }

        .user-card span {
            color: #ffcc66;
        }

        nav {
            background: #1f2a18;
            margin-top: 15px;
            padding: 10px 0;
            border-top: 3px solid #6b8c42;
            border-bottom: 3px solid #6b8c42;
        }

        nav ul {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            list-style: none;
            gap: 8px;
        }

        nav ul li a {
            display: inline-block;
            background: #2c3e23;
            color: #f0f0d0;
            text-decoration: none;
            padding: 8px 20px;
            font-weight: bold;
            font-family: monospace;
            border: 2px solid #6e944d;
            transition: 0.1s linear;
            box-shadow: 0 3px 0 #1a2a0f;
            cursor: pointer;
        }

        nav ul li a:hover {
            background: #4a7040;
            transform: translateY(-2px);
            box-shadow: 0 5px 0 #1a2a0f;
        }

        .nav-active {
            background: #5a8540 !important;
            border-color: #ffcc66 !important;
        }

        .section {
            background: #1f2a1aa0;
            backdrop-filter: blur(2px);
            margin: 40px 0;
            padding: 10px 0;
            display: none;
        }

        .section.active-section {
            display: block;
        }

        .section-title {
            font-size: 1.8rem;
            background: #2a3a20;
            display: inline-block;
            padding: 8px 25px;
            margin-bottom: 25px;
            border-left: 12px solid #f5b042;
            border-right: 4px solid #6b8c42;
            font-family: monospace;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
        }

        .minecraft-card {
            background: #262f1f;
            border: 3px solid #5f7e42;
            box-shadow: 5px 5px 0 #0f1a0a;
            transition: all 0.2s;
        }

        .minecraft-card:hover {
            transform: translate(-2px, -2px);
            box-shadow: 8px 8px 0 #0f1a0a;
            border-color: #e5b83c;
        }

        .card-img {
            height: 140px;
            background-color: #3a552a;
            background-size: cover;
            background-position: center;
            border-bottom: 3px solid #7faa5a;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
        }

        .card-content {
            padding: 18px;
        }

        .card-content h3 {
            color: #ffdd99;
            margin-bottom: 8px;
            font-size: 1.3rem;
        }

        .card-content p {
            color: #cce0bb;
            font-size: 0.9rem;
        }

        .tag {
            display: inline-block;
            background: #4a3920;
            padding: 3px 10px;
            margin-top: 12px;
            font-size: 0.7rem;
            font-family: monospace;
            border-left: 3px solid #ffaa33;
        }

        .seed-box {
            background: #1e2a16;
            border: 3px solid #5a7940;
            padding: 20px;
        }

        .seed-list {
            list-style: none;
        }

        .seed-list li {
            background: #2c3b22;
            margin: 12px 0;
            padding: 12px 15px;
            font-family: 'Courier New', monospace;
            border-left: 8px solid #ffaa44;
            word-break: break-all;
        }

        .seed-code {
            font-weight: bold;
            color: #ffcc88;
            background: #0f1a0c;
            padding: 3px 8px;
            display: inline-block;
        }

        .info-box {
            background: #1e2e16;
            padding: 15px;
            margin-top: 20px;
            border-left: 6px solid gold;
        }

        footer {
            background: #111d0e;
            text-align: center;
            padding: 20px;
            margin-top: 50px;
            border-top: 6px solid #5f7e42;
            font-size: 0.8rem;
        }

        .loading {
            text-align: center;
            padding: 50px;
            font-size: 1.5rem;
            color: #a0e060;
        }

        @media (max-width: 650px) {
            .header-flex {
                flex-direction: column;
                text-align: center;
            }
            .section-title {
                font-size: 1.4rem;
            }
            .card-img {
                height: 100px;
            }
        }
    </style>
</head>
<body>

<header>
    <div class="container header-flex">
        <div class="logo">
            <h1>⛏️ MC.UZ | CRAFT WORLD</h1>
            <p>Bloklar saltanati — o‘zbek tilidagi eng to‘liq portal</p>
        </div>
        <div class="user-card">
            🧑‍💻 <span>Ortiqjon Xasanov</span>
        </div>
    </div>
    <div class="container">
        <nav>
            <ul>
                <li><a data-section="skins">🎨 SKINLAR</a></li>
                <li><a data-section="mods">🧩 MODLAR</a></li>
                <li><a data-section="seeds">🌾 SEEDLAR</a></li>
                <li><a data-section="tips">📘 MASLAHATLAR</a></li>
                <li><a data-section="updates">🆕 1.21 YANGILIK</a></li>
            </ul>
        </nav>
    </div>
</header>

<main class="container">
    <div id="app">
        <div class="loading">⛏️ Minecraft ma'lumotlari yuklanmoqda...</div>
    </div>
</main>

<footer>
    <p>© 2025 Minecraft World | Ortiqjon Xasanov tomonidan yaratilgan. Minecraft rasmiy Mojang brendi.</p>
    <p>Sayt faqat ma'lumot olish uchun. Barcha skinlar, modlar mualliflik huquqiga ega.</p>
</footer>

<script>
    // ======================= JSON MA'LUMOTLAR =======================
    const minecraftData = {
        "skins": [
            { "id": 1, "emoji": "⚔️🧑", "name": "Qora qilichboz", "description": "Qora zirh + qip-qizil ko'zlar. PvP serverlar uchun ajoyib tanlov.", "tag": "📥 15k+ yuklangan" },
            { "id": 2, "emoji": "🧝‍♀️🍃", "name": "O‘rmon elfi", "description": "Yashil va oltin tuslardagi nozik skin. Builderlar orasida mashhur.", "tag": "✨ Yangi" },
            { "id": 3, "emoji": "🐉🔥", "name": "Ajdar qo'riqchisi", "description": "Qanotli dubulg'a, olmos naqshlari. Epic skin!", "tag": "Legendary" },
            { "id": 4, "emoji": "🤖⚡", "name": "Kiber-2025", "description": "Futuristik neon skin, tungi serverlarda porlaydi.", "tag": "Premium" }
        ],
        "mods": [
            { "id": 1, "name": "🔧 Create Mod", "description": "Mexanizmlar, konveyerlar, aylanuvchi qismlar — avtomatika olami.", "tag": "Forge 1.20.1" },
            { "id": 2, "name": "🧙 Ars Nouveau", "description": "Sehrgarlik, o'z sehrlaringizni yozish va murakkab spellar.", "tag": "Mana tizimi" },
            { "id": 3, "name": "🗺️ JourneyMap", "description": "Real vaqtda xarita, bo'limlarni belgilash va kuzatish.", "tag": "Majburiy" },
            { "id": 4, "name": "🐉 Ice and Fire", "description": "Haqiqiy ajdarlar, gifonlar va mifologik maxluqlar.", "tag": "Epik janglar" }
        ],
        "seeds": [
            { "code": "🌲 -8400280189225650786", "description": "Keng qayin o'rmoni, yonida katta qishloq va omborxona." },
            { "code": "🏰 808080808", "description": "Spawn nuqtasidan 150 blok uzoqlikda qal'a (stronghold) va portal." },
            { "code": "💎 9876543210", "description": "Y=-54 da katta olmas tomirlari, ulanishli g'orlar tarmog'i." },
            { "code": "🏝️ -672410349", "description": "8 ta orol, markazda mangrov biomi va yashirin sandiqlar." },
            { "code": "❄️ 1.21_trial", "description": "Trial Chambers spawn ostida, Breeze mavjudoti yaqin." }
        ],
        "tips": [
            { "name": "💎 Olmos qazish sirlari", "description": "Y=-59 eng optimal qavat. Strip mining (2x1 yo'lak) usuli eng samarali. Fortune 3 bilan 2-3 barobar ko'p olmos olasiz." },
            { "name": "⚡ Nether transport", "description": "Netherda 1 blok = Overworldda 8 blok. Portallarni to'g'ri hisoblab, tez sayohat qiling." },
            { "name": "🛡️ Villager savdolari", "description": "Zombie - villagerni davolab, 1 zumradga mending kitob olish mumkin. Eng kuchli buyumlar shunday olinadi." },
            { "name": "🐉 Ender Dragon uchun tayyorgarlik", "description": "Olmos zirh + Feather Falling etik, slow falling iksiri, o'q va qum bloklari (kristallarni buzish uchun)." },
            { "name": "🔮 Enchanting maksimal", "description": "15 ta kitob javonini 2 blok masofada joylashtiring. Eng yaxshi sehrlar 30 lvl ochiladi." }
        ],
        "updates": [
            { "name": "🏛️ Trial Chambers", "description": "Yangi yer osti inshootlari. Trial Spawner orqali to'lqinli janglar. Mukofot: mace quroli va breeze tuxumlari.", "tag": "Yangi struktura" },
            { "name": "💨 Breeze mavjudoti", "description": "Uchuvchi, shamol hujumlari bilan otadi. Undan breeze rod tushadi — mace yasash uchun kerak.", "tag": "Hostile mob" },
            { "name": "🔨 Mace quroli", "description": "Balandlikdan tushganda qancha baland bo'lsa, shuncha katta zarar. Yiqilishdan o'zingiz himoyalanmagan bo'lsangiz ishlaydi.", "tag": "Yangi qurol" },
            { "name": "🎨 Armor trim + yangi naqshlar", "description": "7 xil yangi bezak (Flow, Bolt, Guster). Netherite yangilash crafting stolida o'zgartirildi.", "tag": "1.21" }
        ],
        "updateInfo": "⭐ 1.21 versiyasida 'Trial Chambers' Y= -40 dan -20 gacha paydo bo'ladi. Yangi 'crafter' bloki sizga avtomatik craft qilish imkonini beradi."
    };

    // ======================= DINAMIK RENDER FUNKSIYALARI =======================
    function renderSkins() {
        return `
            <div class="section active-section" id="skins-section">
                <h2 class="section-title">🎨 MASHHUR SKINLAR</h2>
                <div class="grid">
                    ${minecraftData.skins.map(skin => `
                        <div class="minecraft-card">
                            <div class="card-img">${skin.emoji}</div>
                            <div class="card-content">
                                <h3>${skin.name}</h3>
                                <p>${skin.description}</p>
                                <span class="tag">${skin.tag}</span>
                            </div>
                        </div>
                    `).join('')}
                </div>
            </div>
        `;
    }

    function renderMods() {
        return `
            <div class="section" id="mods-section">
                <h2 class="section-title">🧩 ENG YAXSHI MODLAR</h2>
                <div class="grid">
                    ${minecraftData.mods.map(mod => `
                        <div class="minecraft-card">
                            <div class="card-content">
                                <h3>${mod.name}</h3>
                                <p>${mod.description}</p>
                                <span class="tag">${mod.tag}</span>
                            </div>
                        </div>
                    `).join('')}
                </div>
            </div>
        `;
    }

    function renderSeeds() {
        return `
            <div class="section" id="seeds-section">
                <h2 class="section-title">🌱 NOYOB SEEDLAR (Java 1.20+ / 1.21)</h2>
                <div class="seed-box">
                    <ul class="seed-list">
                        ${minecraftData.seeds.map(seed => `
                            <li><span class="seed-code">${seed.code}</span> — ${seed.description}</li>
                        `).join('')}
                    </ul>
                </div>
            </div>
        `;
    }

    function renderTips() {
        return `
            <div class="section" id="tips-section">
                <h2 class="section-title">📘 MINECRAFT FOYDALI MASLAHATLAR</h2>
                <div class="grid">
                    ${minecraftData.tips.map(tip => `
                        <div class="minecraft-card">
                            <div class="card-content">
                                <h3>${tip.name}</h3>
                                <p>${tip.description}</p>
                            </div>
                        </div>
                    `).join('')}
                </div>
            </div>
        `;
    }

    function renderUpdates() {
        return `
            <div class="section" id="updates-section">
                <h2 class="section-title">🆕 MINECRAFT 1.21 YANGILIKLARI</h2>
                <div class="grid">
                    ${minecraftData.updates.map(update => `
                        <div class="minecraft-card">
                            <div class="card-content">
                                <h3>${update.name}</h3>
                                <p>${update.description}</p>
                                <span class="tag">${update.tag}</span>
                            </div>
                        </div>
                    `).join('')}
                </div>
                <div class="info-box">
                    <p>${minecraftData.updateInfo}</p>
                </div>
            </div>
        `;
    }

    function renderAllSections() {
        return renderSkins() + renderMods() + renderSeeds() + renderTips() + renderUpdates();
    }

    // ======================= SEKSIYALARNI BOSHQARISH =======================
    let currentSection = "skins";

    function showSection(sectionId) {
        // Barcha sectionlarni yashirish
        const sections = document.querySelectorAll('.section');
        sections.forEach(section => {
            section.classList.remove('active-section');
        });
        
        // Tanlangan sectionni ko'rsatish
        const activeSection = document.getElementById(`${sectionId}-section`);
        if (activeSection) {
            activeSection.classList.add('active-section');
        }
        
        // Navigatsiya tugmalarini yangilash
        const navLinks = document.querySelectorAll('nav ul li a');
        navLinks.forEach(link => {
            link.classList.remove('nav-active');
            if (link.getAttribute('data-section') === sectionId) {
                link.classList.add('nav-active');
            }
        });
        
        currentSection = sectionId;
    }

    // ======================= SAHIFANI ISHGA TUSHIRISH =======================
    function init() {
        const app = document.getElementById('app');
        // Barcha bo'limlarni render qilish
        app.innerHTML = renderAllSections();
        
        // Navigatsiya hodisalarini ulash
        const navLinks = document.querySelectorAll('nav ul li a');
        navLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                const section = link.getAttribute('data-section');
                showSection(section);
            });
        });
        
        // Boshlang'ich seksiyani ko'rsatish (skinlar)
        showSection('skins');
    }
    
    // Sahifa to'liq yuklanganda ishga tushirish
    document.addEventListener('DOMContentLoaded', init);

</script>

</body>
</html>
