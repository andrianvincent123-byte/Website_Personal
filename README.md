<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bahasa Gaul - Kamus Multibahasa</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
        }

        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #FFD700;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: #FFD700;
        }

        main {
            margin-top: 80px;
        }

        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            padding: 8rem 2rem 6rem;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 20% 50%, rgba(255, 255, 255, 0.1) 0%, transparent 50%);
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3.8rem;
            margin-bottom: 1.5rem;
            font-weight: 800;
        }

        .hero p {
            font-size: 1.4rem;
            margin-bottom: 2.5rem;
            opacity: 0.95;
        }

        .cta-button {
            background: white;
            color: #667eea;
            padding: 1.3rem 3.8rem;
            border: none;
            border-radius: 50px;
            font-size: 1.15rem;
            cursor: pointer;
            font-weight: 700;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transition: all 0.4s ease;
        }

        .cta-button:hover {
            transform: translateY(-5px);
            background: linear-gradient(135deg, #FFD700 0%, #FFA500 100%);
            color: white;
        }

        .hero-features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 2rem;
            margin-top: 5rem;
        }

        .feature-card {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(20px);
            padding: 2.5rem 2rem;
            border-radius: 25px;
            border: 2px solid rgba(255, 255, 255, 0.2);
            transition: all 0.4s ease;
        }

        .feature-card:hover {
            transform: translateY(-15px);
            background: rgba(255, 255, 255, 0.25);
        }

        .feature-icon {
            font-size: 3.5rem;
            margin-bottom: 1.2rem;
        }

        .feature-card h3 {
            font-size: 1.4rem;
            margin-bottom: 0.7rem;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        .content-section {
            background: white;
            border-radius: 20px;
            padding: 3rem;
            margin-bottom: 2rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .content-section h2 {
            color: #667eea;
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
        }

        .content-section p {
            line-height: 1.8;
            color: #555;
            margin-bottom: 1rem;
        }

        .language-tabs {
            display: flex;
            gap: 1rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .language-tab {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .language-tab:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .language-tab.active {
            background: linear-gradient(135deg, #FFD700 0%, #FFA500 100%);
        }

        .language-content {
            display: none;
        }

        .language-content.active {
            display: block;
        }

        .language-content h3 {
            color: #667eea;
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
        }

        .table-container {
            overflow-x: auto;
            margin-top: 2rem;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            min-width: 600px;
        }

        thead {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        th, td {
            padding: 1rem;
            text-align: left;
        }

        tbody tr:nth-child(even) {
            background: #f8f9fa;
        }

        tbody tr:hover {
            background: #ffe6cc;
            transition: background 0.3s ease;
        }

        .video-section {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 4rem 2rem;
            color: white;
            text-align: center;
        }

        .video-container {
            max-width: 900px;
            margin: 0 auto;
        }

        .video-section h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: #FFD700;
        }

        .video-section p {
            font-size: 1.2rem;
            margin-bottom: 3rem;
            opacity: 0.9;
        }

        .video-wrapper {
            position: relative;
            width: 100%;
            padding-bottom: 56.25%;
            height: 0;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            margin-bottom: 3rem;
        }

        .video-wrapper iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }

        .video-features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .video-feature {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .video-feature:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-5px);
        }

        .video-feature h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: #FFD700;
        }

        footer {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
            padding: 2rem;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero-features {
                grid-template-columns: 1fr;
            }

            .video-section h2 {
                font-size: 2rem;
            }

            .video-features {
                grid-template-columns: 1fr;
            }

            .nav-links {
                gap: 1rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">🌏</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#language">Language</a></li>
                <li><a href="#video">Video</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home" class="hero">
            <div class="hero-content">
                <h1>Selamat Datang di Kamus Bahasa Gaul</h1>
                <p>Belajar Bahasa Gaul Seru dari Indonesia – Inggris – Sunda – Mandarin!</p>
                <button class="cta-button" onclick="document.getElementById('language').scrollIntoView({behavior: 'smooth'})">Mulai Belajar Sekarang</button>
                
                <div class="hero-features">
                    <div class="feature-card">
                        <div class="feature-icon">🇮🇩</div>
                        <h3>4 Bahasa</h3>
                        <p>Indonesia, Inggris, Sunda, Mandarin</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">🤖</div>
                        <h3>Responsif</h3>
                        <p>Bisa digunakan pada semua device</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">✨</div>
                        <h3>Mudah</h3>
                        <p>Interface user-friendly</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">🎯</div>
                        <h3>Gratis</h3>
                        <p>Akses tanpa batas</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="about" class="container">
            <div class="content-section">
                <h2>About Us</h2>
                <p>Bahasa gaul itu dinamis banget — berubah secepat tren di TikTok! Dari "bro", "baper", "mantul", sampai "Zhuāng shú", semua jadi bagian dari cara kita ngobrol sehari-hari. Kadang campur aduk antara Indonesia, Sunda, Inggris, dan Mandarin… dan itu seru banget!</p>
                
                <p>Kami bikin website ini karena percaya bahwa bahasa itu bukan cuma alat komunikasi, tapi juga cermin budaya dan gaya hidup. Lewat situs ini, kamu bisa kenalan sama istilah-istilah gaul terbaru, artinya dalam berbagai bahasa, dan ngerti kapan serta gimana cara pakainya biar nggak salah konteks.</p>
                
                <p><strong>Di sini kamu bakal nemuin:</strong></p>
                <p>• Arti kata-kata gaul dalam berbagai bahasa (Indo, Sunda, Inggris, Mandarin)</p>
                <p>• Contoh penggunaannya dalam percakapan nyata</p>
                <p>• Penjelasan singkat tentang konteks budaya di balik kata tersebut</p>
                
                <p>Punya kata gaul baru dari tongkrongan, TikTok, atau kampusmu? Kirim ke kami! Siapa tahu kata itu jadi tren berikutnya 😉</p>
            </div>
        </section>

        <section id="language" class="container">
            <div class="content-section">
                <h2>Language – Bahasa Gaul Indonesia | Inggris | Sunda | Mandarin</h2>
                
                <div class="language-tabs">
                    <button class="language-tab active" onclick="showLanguage('indonesia')">Bahasa Indonesia</button>
                    <button class="language-tab" onclick="showLanguage('english')">Bahasa Inggris</button>
                    <button class="language-tab" onclick="showLanguage('sunda')">Bahasa Sunda</button>
                    <button class="language-tab" onclick="showLanguage('mandarin')">Bahasa Mandarin</button>
                </div>

                <div class="language-content active" id="indonesia">
                    <h3>Bahasa Indonesia</h3>
                    <div class="table-container">
                        <table>
                            <thead>
                                <tr>
                                    <th>Bahasa Gaul</th>
                                    <th>Arti / Makna</th>
                                    <th>Bahasa Baku</th>
                                    <th>Contoh Kalimat</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td><strong>Baper</strong></td>
                                    <td>(Sunda) Gampang karasa haté / (Indo) Mudah terbawa perasaan / (Eng) Sensitive / (中文) 敏感的 (mǐn gǎn de)</td>
                                    <td>Sensitif / emosional</td>
                                    <td>Jangan baper karena kalah bermain.</td>
                                </tr>
                                <tr>
                                    <td><strong>Bat</strong></td>
                                    <td>(Sunda) Pisan / (Indo) Sangat / (Eng) Very / (中文) 非常 (fēi cháng)</td>
                                    <td>Sangat</td>
                                    <td>Makanannya enak bat, pengen nambah terus!</td>
                                </tr>
                                <tr>
                                    <td><strong>Bucin</strong></td>
                                    <td>(Sunda) Budak cinta / (Indo) Terlalu cinta buta / (Eng) Love-blind / (中文) 爱得盲目 (ài de máng mù)</td>
                                    <td>Terlalu cinta buta</td>
                                    <td>Dia bucin banget, disuruh pacarnya aja langsung nurut.</td>
                                </tr>
                                <tr>
                                    <td><strong>Cabut</strong></td>
                                    <td>(Sunda) Indit / (Indo) Pergi / (Eng) Go / (中文) 走了 (zǒu le)</td>
                                    <td>Pergi</td>
                                    <td>Udah malam nih, aku cabut dulu ya!</td>
                                </tr>
                                <tr>
                                    <td><strong>Caper</strong></td>
                                    <td>(Sunda) Néangan perhatian / (Indo) Cari perhatian / (Eng) Seeking attention / (中文) 吸引注意 (xī yǐn zhù yì)</td>
                                    <td>Menarik perhatian</td>
                                    <td>Dia upload story terus, caper banget sih!</td>
                                </tr>
                                <tr>
                                    <td><strong>Gas</strong></td>
                                    <td>(Sunda) Hayu / (Indo) Ayo / Jalan / (Eng) Let's go / (中文) 走吧 (zǒu ba)</td>
                                    <td>Ajakan</td>
                                    <td>Gas aja bro, kapan lagi jalan bareng?</td>
                                </tr>
                                <tr>
                                    <td><strong>Kepo</strong></td>
                                    <td>(Sunda) Rék nyaho pisan / (Indo) Penasaran banget / (Eng) Curious / (中文) 好奇 (hào qí)</td>
                                    <td>Ingin tahu</td>
                                    <td>Kepo banget sih, pengen tahu semuanya!</td>
                                </tr>
                                <tr>
                                    <td><strong>Mager</strong></td>
                                    <td>(Sunda) Males pindah / (Indo) Malas bergerak / (Eng) Lazy to move / (中文) 懒得动 (Lǎndé dòng)</td>
                                    <td>Malas</td>
                                    <td>Aku lagi mager banget hari ini.</td>
                                </tr>
                                <tr>
                                    <td><strong>Mantul</strong></td>
                                    <td>(Sunda) Sae pisan / (Indo) Sangat bagus / (Eng) Awesome / (中文) 太棒了 (tài bàng le)</td>
                                    <td>Sangat bagus</td>
                                    <td>Presentasi kamu tadi mantul banget, keren parah!</td>
                                </tr>
                                <tr>
                                    <td><strong>Santuy</strong></td>
                                    <td>(Sunda) Santai / (Indo) Santai / Tenang / (Eng) Chill / Relaxed / (中文) 放松 (fàng sōng)</td>
                                    <td>Rileks / tenang</td>
                                    <td>Udah santuy aja, nanti juga beres sendiri.</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

                <div class="language-content" id="english">
                    <h3>Bahasa Inggris</h3>
                    <div class="table-container">
                        <table>
                            <thead>
                                <tr>
                                    <th>Slang</th>
                                    <th>Arti / Makna</th>
                                    <th>Bahasa Baku</th>
                                    <th>Contoh Kalimat</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td><strong>ASAP</strong></td>
                                    <td>(Sunda) Geura-giru / (Indo) Secepatnya / (Eng) As soon as possible / (中文) 尽快 (jǐn kuài)</td>
                                    <td>As Soon As Possible</td>
                                    <td>Send the assignment ASAP!</td>
                                </tr>
                                <tr>
                                    <td><strong>Bro</strong></td>
                                    <td>(Sunda) Dulur / Sobat / (Indo) Teman dekat (cowok) / (Eng) Brother / friend / (中文) 兄弟 (xiōng dì)</td>
                                    <td>Brother / friend</td>
                                    <td>How are you doing bro?</td>
                                </tr>
                                <tr>
                                    <td><strong>Chill</strong></td>
                                    <td>(Sunda) Santai waé / (Indo) Santai / relax / (Eng) Relax / calm / (中文) 放松 (fàng sōng)</td>
                                    <td>Relax / calm</td>
                                    <td>Chill dude, it's not a big problem.</td>
                                </tr>
                                <tr>
                                    <td><strong>Cringe</strong></td>
                                    <td>(Sunda) Isin / Kagok / (Indo) Malu / gak enak dilihat / (Eng) Embarrassing / awkward / (中文) 尴尬 (gān gà)</td>
                                    <td>Embarrassing / awkward</td>
                                    <td>That video is so cringe</td>
                                </tr>
                                <tr>
                                    <td><strong>Flex</strong></td>
                                    <td>(Sunda) Moyok / Pamer / (Indo) Pamer / (Eng) Show off / (中文) 炫耀 (xuàn yào)</td>
                                    <td>Show off</td>
                                    <td>He loves to flex his new car</td>
                                </tr>
                                <tr>
                                    <td><strong>FYI</strong></td>
                                    <td>(Sunda) Ngan ngabéjaan / (Indo) Mau kasih info / (Eng) For your information / (中文) 仅供参考 (jǐn gōng cān kǎo)</td>
                                    <td>For Your Information</td>
                                    <td>FYI, tomorrow is a holiday</td>
                                </tr>
                                <tr>
                                    <td><strong>Ghosting</strong></td>
                                    <td>(Sunda) Ngaleungit / Teu ngahéréan / (Indo) Menghilang tiba-tiba / (Eng) Disappear / ignore suddenly / (中文) 突然消失 (tū rán xiāo shī)</td>
                                    <td>Disappear / ignore</td>
                                    <td>He's ghosting me after the break-up.</td>
                                </tr>
                                <tr>
                                    <td><strong>Lit</strong></td>
                                    <td>(Sunda) Sae pisan / Mantap / (Indo) Keren banget / (Eng) Cool / awesome / (中文) 超棒 (chāo bàng)</td>
                                    <td>Cool / awesome</td>
                                    <td>Yesterday's party was lit!</td>
                                </tr>
                                <tr>
                                    <td><strong>LOL</strong></td>
                                    <td>(Sunda) Seuri ngakak / (Indo) Tertawa keras / (Eng) Laughing out loud / (中文) 哈哈大笑 (hā hā dà xiào)</td>
                                    <td>Laughing out loud</td>
                                    <td>LOL, that meme is hilarious</td>
                                </tr>
                                <tr>
                                    <td><strong>Simp</strong></td>
                                    <td>(Sunda) Budak asmara / (Indo) Budak cinta / (Eng) Overly devoted to someone / (中文) 舔狗 (tiǎn gǒu)</td>
                                    <td>Overly devoted to someone</td>
                                    <td>He's such a simp for everyone</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

                <div class="language-content" id="sunda">
                    <h3>Bahasa Sunda</h3>
                    <div class="table-container">
                        <table>
                            <thead>
                                <tr>
                                    <th>Bahasa Gaul</th>
                                    <th>Arti / Makna</th>
                                    <th>Bahasa Baku</th>
                                    <th>Contoh Kalimat</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td><strong>Aing</strong></td>
                                    <td>(Sunda) Abdi / (Indo) Aku / Saya / (Eng) I / me / (中文) 我 (wǒ)</td>
                                    <td>Abdi</td>
                                    <td>Aing rek balik ayeuna.</td>
                                </tr>
                                <tr>
                                    <td><strong>Aslina</strong></td>
                                    <td>(Sunda) Saleresna? / (Indo) Seriusan? / Beneran? / (Eng) Seriously? / Really? / (中文) 真的吗？ (zhēn de ma?)</td>
                                    <td>Sakedahna / Saleresna</td>
                                    <td>Aslina manéhna datang?</td>
                                </tr>
                                <tr>
                                    <td><strong>Atuh</strong></td>
                                    <td>(Sunda) Atuh / (Indo) Dong / lah / (Eng) Come on / please (emphasizer) / (中文) 嘛 / 啦 (ma / la)</td>
                                    <td>Penegas kalimat</td>
                                    <td>Sok atuh dahar heula.</td>
                                </tr>
                                <tr>
                                    <td><strong>Bray</strong></td>
                                    <td>(Sunda) Dulur / (Indo) Bro / (Eng) Bro / Brother / (中文) 兄弟 (xiōng dì)</td>
                                    <td>Sadulur / Réréncangan</td>
                                    <td>Bray, ka mana wé?</td>
                                </tr>
                                <tr>
                                    <td><strong>Cing</strong></td>
                                    <td>(Sunda) Cing / (Indo) Ayo dong / tolong / (Eng) Please / (中文) 拜托 (bài tuō)</td>
                                    <td>Punten / Mangga</td>
                                    <td>Cing atuh tulung aing!</td>
                                </tr>
                                <tr>
                                    <td><strong>Eta pisan</strong></td>
                                    <td>(Sunda) Eta pisan / (Indo) Benar banget / (Eng) Exactly / (中文) 完全正确 (wán quán zhèng què)</td>
                                    <td>Éta leres pisan</td>
                                    <td>Eta pisan nu dicarioskeun ku manéhna</td>
                                </tr>
                                <tr>
                                    <td><strong>Euy</strong></td>
                                    <td>(Sunda) Euy / Aduh / (Indo) Wah / (Eng) Wow / (中文) 哇 (wa)</td>
                                    <td>Aduh / Wah</td>
                                    <td>Euy, geulis pisan!</td>
                                </tr>
                                <tr>
                                    <td><strong>Harkos</strong></td>
                                    <td>(Sunda) Gampil / (Indo) Banyak omong / (Eng) Talkative / (中文) 话多 (huà duō)</td>
                                    <td>Loba omongan</td>
                                    <td>Manéhna téh harkos pisan</td>
                                </tr>
                                <tr>
                                    <td><strong>Heueuh</strong></td>
                                    <td>(Sunda) Heueuh / Muhun / (Indo) Iya / benar / (Eng) Yes / (中文) 是的 (shì de)</td>
                                    <td>Muhun / Leres</td>
                                    <td>Heueuh, geus dahar.</td>
                                </tr>
                                <tr>
                                    <td><strong>Jangar</strong></td>
                                    <td>(Sunda) Lieur / (Indo) Pusing / (Eng) Dizzy / confused / (中文) 头晕 (tóu yūn)</td>
                                    <td>Lieur / Kapala nyeri</td>
                                    <td>Jangar sirah mikiran tugas</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

                <div class="language-content" id="mandarin">
                    <h3>Bahasa Mandarin</h3>
                    <div class="table-container">
                        <table>
                            <thead>
                                <tr>
                                    <th>Slang</th>
                                    <th>Pinyin</th>
                                    <th>Arti / Makna</th>
                                    <th>Contoh Kalimat</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td><strong>八卦</strong></td>
                                    <td>Bā guà</td>
                                    <td>(Sunda) Nyarungkeun batur / (Indo) Julid / Ngomongin orang di belakang / (Eng) Gossiping / talking behind someone's back / (中文) 八卦</td>
                                    <td>她最喜欢八卦别人了。(Tā zuì xǐ huān bā guà bié rén le.)</td>
                                </tr>
                                <tr>
                                    <td><strong>补刀</strong></td>
                                    <td>Bǔ dāo</td>
                                    <td>(Sunda) Nambahan nyeri / (Indo) Menambah sakit hati / Menyinggung lebih dalam / (Eng) Adding insult to injury / delivering the final blow / (中文) 补刀</td>
                                    <td>他刚被批评，你还补刀，太狠了！(Tā gāng bèi pī píng, nǐ hái bǔ dāo, tài hěn le!)</td>
                                </tr>
                                <tr>
                                    <td><strong>很凶</strong></td>
                                    <td>Hěn xiōng</td>
                                    <td>(Sunda) Galak pisan / (Indo) Galak / judes banget / (Eng) Being harsh / fierce / mean / (中文) 很凶</td>
                                    <td>你干嘛对我那么凶啊？(Nǐ gàn má duì wǒ nà me xiōng a?)</td>
                                </tr>
                                <tr>
                                    <td><strong>鸡婆</strong></td>
                                    <td>Jī pó</td>
                                    <td>(Sunda) Hayang terang urusan batur / (Indo) Kepo / Suka tahu urusan orang / (Eng) Nosy / busybody / (中文) 鸡婆</td>
                                    <td>你不要那么鸡婆啦！(Nǐ bù yào nà me jī pó la!)</td>
                                </tr>
                                <tr>
                                    <td><strong>夸张</strong></td>
                                    <td>kuā zhāng</td>
                                    <td>(Sunda) Kaleuleuwihi / (Indo) Lebay / Berlebihan / (Eng) Over the top / exaggerated / (中文) 夸张</td>
                                    <td>你也太夸张了吧!(Nǐ yě tài kuā zhāng le ba!)</td>
                                </tr>
                                <tr>
                                    <td><strong>奥利给</strong></td>
                                    <td>Ào lì gěi</td>
                                    <td>(Sunda) Mantap / Sumanget! / (Indo) Mantap / Semangat terus! / (Eng) Awesome / Keep it up! / Let's go! / (中文) 奥利给</td>
                                    <td>今天我们一定能成功，奥利给!(Jīn tiān wǒ men yī dìng néng chéng gōng, ào lì gěi!)</td>
                                </tr>
                                <tr>
                                    <td><strong>傻眼</strong></td>
                                    <td>Shǎ yǎn</td>
                                    <td>(Sunda) Reuwas / Kagét / (Indo) Pangling / Terkejut / Tercengang / (Eng) Stunned / shocked / dumbfounded / (中文) 傻眼</td>
                                    <td>听到那个消息我都傻眼了!(Tīng dào nà gè xiāo xi wǒ dōu shǎ yǎn le!)</td>
                                </tr>
                                <tr>
                                    <td><strong>吐槽</strong></td>
                                    <td>Tù cáo</td>
                                    <td>(Sunda) Ngritik / Nyarioskeun kalemahan / (Indo) Komplain / Ngomongin kelemahan / Nyindir / (Eng) Roasting / criticizing / complaining / (中文) 吐槽</td>
                                    <td>我想吐槽一下这部电影太无聊了！(Wǒ xiǎng tù cáo yī xià zhè bù diàn yǐng tài wú liáo le!)</td>
                                </tr>
                                <tr>
                                    <td><strong>心塞</strong></td>
                                    <td>Xīn sāi</td>
                                    <td>(Sunda) Nyeri haté / Sedih / (Indo) Sakit hati / Sedih / Tidak berdaya / (Eng) Heartbroken / feeling down / helpless / (中文) 心塞</td>
                                    <td>想到那件事我就心塞。(Xiǎng dào nà jiàn shì wǒ jiù xīn sāi.)</td>
                                </tr>
                                <tr>
                                    <td><strong>装熟</strong></td>
                                    <td>Zhuāng shú</td>
                                    <td>(Sunda) Sok akrab / (Indo) Sok kenal sok dekat / (Eng) Acting overly familiar / pretending to be close / (中文) 装熟</td>
                                    <td>他刚认识我就一直装熟，真的有点尴尬。(Tā gāng rèn shi wǒ jiù yī zhí zhuāng shú, zhēn de yǒu diǎn gān gà.)</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </section>

        <section id="video" class="video-section">
            <div class="video-container">
                <h2>Video Belajar Bahasa Gaul</h2>
                <p>Tonton video pembelajaran interaktif untuk menguasai bahasa gaul dengan lebih mudah dan menyenangkan</p>

                <div class="video-wrapper" style="padding-bottom: 0; height: auto; background: rgba(255,255,255,0.1); backdrop-filter: blur(10px); display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 4rem 2rem; border: 2px solid rgba(255,255,255,0.3);">
                    <div style="font-size: 4rem; margin-bottom: 1.5rem;">🎥</div>
                    <h3 style="color: #FFD700; font-size: 1.5rem; margin-bottom: 1rem;">Video Pembelajaran Bahasa Gaul</h3>
                    <p style="margin-bottom: 2rem; opacity: 0.9;">Klik tombol di bawah untuk menonton video pembelajaran bahasa gaul di YouTube</p>
                    <a href="https://youtu.be/Xjqf-8AKesk" target="_blank" rel="noopener noreferrer" style="background: linear-gradient(135deg, #FFD700 0%, #FFA500 100%); color: white; padding: 1.2rem 3rem; border-radius: 50px; text-decoration: none; font-weight: 700; font-size: 1.1rem; box-shadow: 0 10px 30px rgba(0,0,0,0.3); transition: all 0.3s ease; display: inline-block;">
                        ▶ Tonton di YouTube
                    </a>
                </div>

                <div class="video-features">
                    <div class="video-feature">
                        <h3>🎥 Video Interaktif</h3>
                        <p>Belajar melalui video yang menarik dan mudah dipahami dengan contoh penggunaan sehari-hari</p>
                    </div>
                    <div class="video-feature">
                        <h3>🎧 Audio Jernih</h3>
                        <p>Dengarkan pelafalan yang jelas dari penutur asli untuk pengucapan yang tepat</p>
                    </div>
                    <div class="video-feature">
                        <h3>📝 Subtitle Lengkap</h3>
                        <p>Dilengkapi dengan subtitle bahasa Indonesia dan bahasa asli untuk memudahkan pembelajaran</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Bahasa Gaul Lengkap. Platform Edukasi Bahasa untuk Generasi Digital.</p>
    </footer>

    <script>
        function showLanguage(lang) {
            const contents = document.querySelectorAll('.language-content');
            const tabs = document.querySelectorAll('.language-tab');
            
            contents.forEach(c => c.classList.remove('active'));
            tabs.forEach(t => t.classList.remove('active'));
            
            document.getElementById(lang).classList.add('active');
            event.target.classList.add('active');
        }

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
