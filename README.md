<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Dishut Umum dan Kepegawaian - Dashboard Kepegawaian</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

<style>

:root{
    --green:#123d2b;
    --green-dark:#09291d;
    --green2:#1c6848;
    --green3:#2d8a5c;
    --green-light:#eaf4ee;
    --gold:#d5ad52;
    --gold-light:#f3d98b;
    --white:#ffffff;
    --gray:#f4f7f5;
    --text:#1d2b25;
    --muted:#6d7b74;
    --danger:#d94b4b;
    --shadow:0 15px 45px rgba(0,0,0,.12);
}

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:'Inter',Arial,sans-serif;
    background:var(--gray);
    color:var(--text);
}

/* =========================================================
   LOGIN PAGE
========================================================= */

#loginPage{
    position:fixed;
    inset:0;
    z-index:99999;
    min-height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    overflow:hidden;

    background:
        radial-gradient(circle at 10% 20%,rgba(77,150,103,.28),transparent 28%),
        radial-gradient(circle at 90% 80%,rgba(213,173,82,.20),transparent 25%),
        linear-gradient(135deg,#061d14 0%,#0c3927 48%,#123d2b 100%);
}

/* dekorasi background */

.login-decoration{
    position:absolute;
    inset:0;
    pointer-events:none;
    overflow:hidden;
}

.login-decoration span{
    position:absolute;
    display:block;
    border-radius:50%;
    background:rgba(255,255,255,.035);
    border:1px solid rgba(255,255,255,.05);
}

.login-decoration span:nth-child(1){
    width:450px;
    height:450px;
    left:-180px;
    top:-160px;
}

.login-decoration span:nth-child(2){
    width:650px;
    height:650px;
    right:-300px;
    bottom:-320px;
}

.login-decoration span:nth-child(3){
    width:200px;
    height:200px;
    right:18%;
    top:8%;
}

.login-decoration span:nth-child(4){
    width:120px;
    height:120px;
    left:18%;
    bottom:12%;
}

/* garis emas */

.login-lines{
    position:absolute;
    inset:0;
    opacity:.35;
    background-image:
        linear-gradient(120deg,transparent 49.8%,rgba(213,173,82,.18) 50%,transparent 50.2%),
        linear-gradient(60deg,transparent 49.8%,rgba(213,173,82,.10) 50%,transparent 50.2%);
    background-size:350px 350px;
}

/* kartu login */

.login-card{
    position:relative;
    width:min(450px,92%);
    padding:42px 40px;
    border-radius:28px;

    background:rgba(255,255,255,.105);
    border:1px solid rgba(255,255,255,.20);
    box-shadow:
        0 30px 80px rgba(0,0,0,.38),
        inset 0 1px 0 rgba(255,255,255,.12);

    backdrop-filter:blur(22px);
    -webkit-backdrop-filter:blur(22px);

    animation:loginAppear .8s ease;
}

@keyframes loginAppear{
    from{
        opacity:0;
        transform:translateY(30px) scale(.97);
    }
    to{
        opacity:1;
        transform:translateY(0) scale(1);
    }
}

.login-top{
    text-align:center;
    margin-bottom:28px;
}

.login-logo{
    width:190px;
    max-width:75%;
    height:auto;
    margin:0 auto 18px;
    display:block;
    filter:drop-shadow(0 8px 18px rgba(0,0,0,.25));
}

.login-badge{
    display:inline-flex;
    align-items:center;
    gap:8px;
    padding:7px 14px;
    border:1px solid rgba(213,173,82,.45);
    background:rgba(213,173,82,.10);
    border-radius:50px;
    color:var(--gold-light);
    font-size:11px;
    font-weight:700;
    letter-spacing:1.4px;
    text-transform:uppercase;
    margin-bottom:14px;
}

.login-title{
    color:#fff;
    font-size:28px;
    font-weight:800;
    letter-spacing:-.7px;
}

.login-subtitle{
    color:rgba(255,255,255,.72);
    font-size:13px;
    margin-top:8px;
    line-height:1.6;
}

.login-form{
    margin-top:28px;
}

.input-group{
    margin-bottom:17px;
}

.input-group label{
    display:block;
    color:rgba(255,255,255,.88);
    font-size:12px;
    font-weight:600;
    margin-bottom:8px;
}

.input-wrapper{
    position:relative;
}

.input-wrapper .input-icon{
    position:absolute;
    left:16px;
    top:50%;
    transform:translateY(-50%);
    color:rgba(255,255,255,.55);
    font-size:17px;
}

.input-wrapper input{
    width:100%;
    height:52px;
    border-radius:14px;
    border:1px solid rgba(255,255,255,.17);
    background:rgba(0,0,0,.17);
    color:#fff;
    outline:none;
    padding:0 48px;
    font-size:14px;
    transition:.25s;
}

.input-wrapper input::placeholder{
    color:rgba(255,255,255,.38);
}

.input-wrapper input:focus{
    border-color:var(--gold);
    background:rgba(0,0,0,.23);
    box-shadow:0 0 0 3px rgba(213,173,82,.10);
}

.password-toggle{
    position:absolute;
    right:14px;
    top:50%;
    transform:translateY(-50%);
    border:none;
    background:none;
    color:rgba(255,255,255,.55);
    cursor:pointer;
    font-size:17px;
}

.login-button{
    width:100%;
    height:54px;
    border:none;
    border-radius:15px;
    cursor:pointer;

    background:linear-gradient(135deg,var(--gold-light),var(--gold));
    color:#173326;

    font-size:14px;
    font-weight:800;
    letter-spacing:.3px;

    box-shadow:0 12px 28px rgba(213,173,82,.20);
    transition:.25s;
}

.login-button:hover{
    transform:translateY(-2px);
    box-shadow:0 16px 32px rgba(213,173,82,.28);
}

.login-button:active{
    transform:translateY(0);
}

.login-error{
    display:none;
    margin-top:15px;
    padding:12px 14px;
    border-radius:12px;

    color:#ffd4d4;
    background:rgba(217,75,75,.13);
    border:1px solid rgba(255,120,120,.25);

    text-align:center;
    font-size:12px;
    font-weight:700;

    animation:errorShake .35s ease;
}

.login-error.show{
    display:block;
}

@keyframes errorShake{
    0%,100%{transform:translateX(0)}
    25%{transform:translateX(-5px)}
    75%{transform:translateX(5px)}
}

.login-footer{
    text-align:center;
    margin-top:25px;
    color:rgba(255,255,255,.48);
    font-size:10px;
    line-height:1.6;
}

.login-footer strong{
    color:rgba(255,255,255,.72);
}

/* =========================================================
   DASHBOARD
========================================================= */

#dashboard{
    display:none;
}

#dashboard.active{
    display:block;
}

/* SIDEBAR */

.sidebar{
    position:fixed;
    left:0;
    top:0;
    bottom:0;
    width:280px;

    background:
        linear-gradient(180deg,rgba(18,61,43,.98),rgba(9,41,29,.99));

    color:#fff;
    z-index:1000;

    box-shadow:10px 0 35px rgba(0,0,0,.12);
    overflow-y:auto;
}

.sidebar-brand{
    padding:28px 24px 22px;
    border-bottom:1px solid rgba(255,255,255,.08);
}

.brand-mark{
    width:48px;
    height:48px;
    border-radius:14px;
    background:linear-gradient(135deg,var(--gold-light),var(--gold));
    display:flex;
    align-items:center;
    justify-content:center;
    color:var(--green-dark);
    font-weight:900;
    font-size:18px;
    margin-bottom:14px;
    box-shadow:0 8px 22px rgba(213,173,82,.18);
}

.brand-title{
    font-size:19px;
    font-weight:800;
}

.brand-subtitle{
    margin-top:5px;
    color:rgba(255,255,255,.55);
    font-size:11px;
    line-height:1.5;
}

.nav-section{
    padding:20px 14px 8px;
}

.nav-label{
    color:rgba(255,255,255,.38);
    font-size:9px;
    font-weight:800;
    letter-spacing:1.5px;
    text-transform:uppercase;
    padding:0 12px 9px;
}

.nav-item{
    display:flex;
    align-items:center;
    gap:12px;
    color:rgba(255,255,255,.68);
    text-decoration:none;
    padding:12px 13px;
    margin:3px 0;
    border-radius:11px;
    font-size:12px;
    font-weight:600;
    transition:.2s;
}

.nav-item:hover,
.nav-item.active{
    color:#fff;
    background:rgba(255,255,255,.09);
}

.nav-item.active{
    box-shadow:inset 3px 0 0 var(--gold);
}

.nav-icon{
    width:20px;
    text-align:center;
    font-size:16px;
}

.sidebar-bottom{
    padding:20px 18px;
    margin-top:15px;
}

.logout-btn{
    width:100%;
    padding:11px;
    border-radius:11px;
    border:1px solid rgba(255,255,255,.10);
    background:rgba(255,255,255,.06);
    color:rgba(255,255,255,.75);
    cursor:pointer;
    font-size:11px;
    font-weight:700;
    transition:.2s;
}

.logout-btn:hover{
    background:rgba(217,75,75,.16);
    color:#fff;
}

/* MAIN */

.main{
    margin-left:280px;
    min-height:100vh;
}

.topbar{
    height:72px;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 32px;
    background:#fff;
    border-bottom:1px solid #e8eeeb;
    position:sticky;
    top:0;
    z-index:500;
}

.search-box{
    display:flex;
    align-items:center;
    gap:10px;
    width:360px;
    height:40px;
    padding:0 14px;
    border-radius:11px;
    background:#f5f8f6;
    border:1px solid #e7ece9;
}

.search-box span{
    color:#87948e;
}

.search-box input{
    border:none;
    outline:none;
    background:transparent;
    width:100%;
    font-size:12px;
}

.datetime{
    text-align:right;
}

.datetime .time{
    font-size:13px;
    font-weight:800;
    color:var(--green);
}

.datetime .date{
    font-size:10px;
    color:var(--muted);
    margin-top:3px;
}

.content{
    padding:30px;
}

/* HERO */

.hero{
    position:relative;
    overflow:hidden;

    min-height:260px;
    border-radius:24px;

    padding:35px;

    background:
        radial-gradient(circle at 85% 20%,rgba(213,173,82,.22),transparent 28%),
        radial-gradient(circle at 10% 90%,rgba(45,138,92,.30),transparent 30%),
        linear-gradient(135deg,#0b3021,#195c40);

    color:#fff;
    box-shadow:var(--shadow);
}

.hero:before{
    content:"";
    position:absolute;
    width:300px;
    height:300px;
    right:-120px;
    bottom:-150px;
    border:1px solid rgba(255,255,255,.10);
    border-radius:50%;
}

.hero:after{
    content:"";
    position:absolute;
    width:500px;
    height:500px;
    right:-260px;
    top:-300px;
    border:1px solid rgba(255,255,255,.08);
    border-radius:50%;
}

.hero-content{
    position:relative;
    z-index:2;
    max-width:680px;
}

.hero-badge{
    display:inline-flex;
    padding:7px 12px;
    border-radius:50px;
    background:rgba(213,173,82,.13);
    border:1px solid rgba(213,173,82,.30);
    color:var(--gold-light);
    font-size:10px;
    font-weight:800;
    letter-spacing:1px;
    text-transform:uppercase;
}

.hero h1{
    font-size:32px;
    line-height:1.2;
    margin-top:17px;
    letter-spacing:-1px;
}

.hero p{
    color:rgba(255,255,255,.70);
    max-width:620px;
    margin-top:12px;
    font-size:13px;
    line-height:1.8;
}

.hero-berakhlak{
    position:absolute;
    right:35px;
    bottom:30px;
    width:150px;
    opacity:.95;
    z-index:3;
}

/* SECTION */

.section{
    margin-top:32px;
}

.section-heading{
    display:flex;
    align-items:end;
    justify-content:space-between;
    margin-bottom:17px;
}

.section-heading h2{
    font-size:18px;
    color:var(--green);
}

.section-heading p{
    font-size:11px;
    color:var(--muted);
    margin-top:5px;
}

/* STATISTICS */

.stats{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:16px;
}

.stat-card{
    background:#fff;
    border:1px solid #e6ece9;
    border-radius:17px;
    padding:20px;
    box-shadow:0 8px 25px rgba(0,0,0,.04);
    transition:.25s;
}

.stat-card:hover{
    transform:translateY(-4px);
    box-shadow:0 14px 30px rgba(0,0,0,.08);
}

.stat-top{
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.stat-icon{
    width:40px;
    height:40px;
    border-radius:12px;
    display:flex;
    align-items:center;
    justify-content:center;
    background:var(--green-light);
    color:var(--green2);
    font-size:18px;
}

.stat-number{
    font-size:25px;
    font-weight:800;
    color:var(--green);
    margin-top:17px;
}

.stat-label{
    font-size:11px;
    color:var(--muted);
    margin-top:5px;
}

/* CARDS */

.card-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:17px;
}

.dashboard-card{
    position:relative;
    background:#fff;
    border:1px solid #e6ece9;
    border-radius:17px;
    padding:20px;
    text-decoration:none;
    color:inherit;
    transition:.25s;
    overflow:hidden;
}

.dashboard-card:after{
    content:"";
    position:absolute;
    left:0;
    bottom:0;
    height:3px;
    width:0;
    background:linear-gradient(90deg,var(--gold),var(--green3));
    transition:.3s;
}

.dashboard-card:hover{
    transform:translateY(-4px);
    box-shadow:0 15px 32px rgba(0,0,0,.08);
    border-color:#dce6e1;
}

.dashboard-card:hover:after{
    width:100%;
}

.card-icon{
    width:43px;
    height:43px;
    border-radius:13px;
    background:var(--green-light);
    color:var(--green2);
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:19px;
    margin-bottom:15px;
}

.dashboard-card h3{
    color:var(--green);
    font-size:13px;
    line-height:1.4;
}

.dashboard-card p{
    color:var(--muted);
    font-size:10px;
    line-height:1.6;
    margin-top:6px;
}

.card-arrow{
    position:absolute;
    right:18px;
    bottom:18px;
    color:var(--gold);
    font-weight:800;
}

/* INFO */

.info-panel{
    display:grid;
    grid-template-columns:1.4fr 1fr;
    gap:18px;
}

.info-box{
    background:#fff;
    border:1px solid #e6ece9;
    border-radius:18px;
    padding:23px;
}

.info-box h3{
    font-size:14px;
    color:var(--green);
    margin-bottom:10px;
}

.info-box p{
    color:var(--muted);
    font-size:11px;
    line-height:1.8;
}

.quick-list{
    display:grid;
    gap:9px;
}

.quick-link{
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:11px 13px;
    background:#f6f9f7;
    border-radius:10px;
    text-decoration:none;
    color:var(--green);
    font-size:11px;
    font-weight:700;
    transition:.2s;
}

.quick-link:hover{
    background:var(--green-light);
    transform:translateX(3px);
}

/* SOCIAL */

.social-row{
    display:flex;
    gap:10px;
    margin-top:15px;
}

.social-link{
    display:flex;
    align-items:center;
    gap:7px;
    padding:10px 13px;
    border-radius:10px;
    text-decoration:none;
    background:var(--green-light);
    color:var(--green);
    font-size:10px;
    font-weight:700;
}

/* FOOTER */

.footer{
    margin-top:35px;
    padding:25px 0 10px;
    border-top:1px solid #dde6e1;
    text-align:center;
    color:#87938d;
    font-size:10px;
    line-height:1.8;
}

/* FLOAT WA */

.floating-wa{
    position:fixed;
    right:25px;
    bottom:25px;
    width:53px;
    height:53px;
    border-radius:50%;
    background:#25d366;
    color:#fff;
    display:flex;
    align-items:center;
    justify-content:center;
    text-decoration:none;
    font-size:24px;
    box-shadow:0 12px 28px rgba(37,211,102,.28);
    z-index:900;
    transition:.25s;
}

.floating-wa:hover{
    transform:translateY(-4px) scale(1.04);
}

/* MOBILE */

.mobile-menu{
    display:none;
}

.mobile-overlay{
    display:none;
}

@media(max-width:1100px){

    .stats{
        grid-template-columns:repeat(2,1fr);
    }

    .card-grid{
        grid-template-columns:repeat(2,1fr);
    }

    .info-panel{
        grid-template-columns:1fr;
    }

}

@media(max-width:800px){

    .sidebar{
        transform:translateX(-100%);
        transition:.3s;
    }

    .sidebar.open{
        transform:translateX(0);
    }

    .main{
        margin-left:0;
    }

    .mobile-menu{
        display:flex;
        width:38px;
        height:38px;
        border:none;
        border-radius:10px;
        background:var(--green-light);
        color:var(--green);
        align-items:center;
        justify-content:center;
        cursor:pointer;
        font-size:18px;
    }

    .topbar{
        padding:0 18px;
        gap:10px;
    }

    .search-box{
        width:auto;
        flex:1;
        max-width:280px;
    }

    .datetime{
        display:none;
    }

    .mobile-overlay.show{
        display:block;
        position:fixed;
        inset:0;
        background:rgba(0,0,0,.4);
        z-index:900;
    }

    .content{
        padding:18px;
    }

    .hero{
        padding:25px;
    }

    .hero h1{
        font-size:25px;
    }

    .hero-berakhlak{
        position:relative;
        right:auto;
        bottom:auto;
        margin-top:25px;
        width:130px;
    }

}

@media(max-width:560px){

    .login-card{
        padding:32px 24px;
    }

    .login-title{
        font-size:24px;
    }

    .stats,
    .card-grid{
        grid-template-columns:1fr;
    }

    .search-box{
        max-width:none;
    }

    .topbar{
        height:62px;
    }

    .hero{
        min-height:auto;
    }

    .hero p{
        font-size:11px;
    }

}

/* SEARCH */

.hidden-search{
    display:none !important;
}

</style>
</head>

<body>


<!-- =========================================================
     LOGIN PAGE
========================================================= -->

<div id="loginPage">

    <div class="login-decoration">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>

    <div class="login-lines"></div>

    <div class="login-card">

        <div class="login-top">

            <!-- Logo BerAKHLAK resmi -->
            <img
                class="login-logo"
                src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Logo_BerAKHLAK.svg/960px-Logo_BerAKHLAK.svg.png"
                alt="Logo BerAKHLAK"
                onerror="this.style.display='none';"
            >

            <div class="login-badge">
                ✦ CORE VALUES ASN
            </div>

            <div class="login-title">
                Dishut Umum dan Kepegawaian
            </div>

            <div class="login-subtitle">
                Sistem Informasi dan Dashboard<br>
                Sub Bagian Umum & Kepegawaian
            </div>

        </div>


        <form class="login-form" id="loginForm">

            <div class="input-group">

                <label for="username">
                    Username
                </label>

                <div class="input-wrapper">

                    <span class="input-icon">👤</span>

                    <input
                        type="text"
                        id="username"
                        placeholder="Masukkan username"
                        autocomplete="username"
                    >

                </div>

            </div>


            <div class="input-group">

                <label for="password">
                    Password
                </label>

                <div class="input-wrapper">

                    <span class="input-icon">🔒</span>

                    <input
                        type="password"
                        id="password"
                        placeholder="Masukkan password"
                        autocomplete="current-password"
                    >

                    <button
                        type="button"
                        class="password-toggle"
                        onclick="togglePassword()"
                        id="passwordToggle"
                    >
                        👁
                    </button>

                </div>

            </div>


            <button
                type="submit"
                class="login-button"
            >
                MASUK KE DASHBOARD
            </button>


            <div
                id="loginError"
                class="login-error"
            >
                ⚠ Salah, username atau password tidak sesuai!
            </div>

        </form>


        <div class="login-footer">

            <strong>Dinas Kehutanan Provinsi Sulawesi Tenggara</strong><br>

            Sub Bagian Umum & Kepegawaian

            <br><br>

            Berorientasi Pelayanan • Akuntabel • Kompeten • Harmonis • Loyal • Adaptif • Kolaboratif

        </div>

    </div>

</div>


<!-- =========================================================
     DASHBOARD
========================================================= -->

<div id="dashboard">


    <!-- SIDEBAR -->

    <aside class="sidebar" id="sidebar">

        <div class="sidebar-brand">

            <div class="brand-mark">
                DU
            </div>

            <div class="brand-title">
                Dishut Umum dan Kepegawaian
            </div>

            <div class="brand-subtitle">
                Dinas Kehutanan Provinsi Sulawesi Tenggara
            </div>

        </div>


        <div class="nav-section">

            <div class="nav-label">
                Menu Utama
            </div>

            <a href="#dashboardHome" class="nav-item active">
                <span class="nav-icon">⌂</span>
                Dashboard
            </a>

            <a href="#dataKepegawaian" class="nav-item">
                <span class="nav-icon">👥</span>
                Data Kepegawaian
            </a>

            <a href="#administrasi" class="nav-item">
                <span class="nav-icon">📁</span>
                Administrasi ASN
            </a>

            <a href="#monitoring" class="nav-item">
                <span class="nav-icon">📊</span>
                Monitoring
            </a>

            <a href="#informasi" class="nav-item">
                <span class="nav-icon">ℹ</span>
                Informasi
            </a>

        </div>


        <div class="nav-section">

            <div class="nav-label">
                Layanan Cepat
            </div>

            <a
                class="nav-item"
                href="https://myasn.bkn.go.id/"
                target="_blank"
            >
                <span class="nav-icon">🪪</span>
                ASN Digital
            </a>

            <a
                class="nav-item"
                href="https://kepegawaianboby.blogspot.com/2023/02/kumpulan-peraturan.html"
                target="_blank"
            >
                <span class="nav-icon">⚖</span>
                Kumpulan Peraturan
            </a>

            <a
                class="nav-item"
                href="https://www.instagram.com/dishutumkep?igsh=MTYxNHIyYTdwZXN4bQ%3D%3D"
                target="_blank"
            >
                <span class="nav-icon">◎</span>
                Instagram
            </a>

            <a
                class="nav-item"
                href="https://api.whatsapp.com/send/?phone=08131153574&text&type=phone_number&app_absent=0"
                target="_blank"
            >
                <span class="nav-icon">◉</span>
                WhatsApp
            </a>

        </div>


        <div class="sidebar-bottom">

            <button
                class="logout-btn"
                onclick="logout()"
            >
                ⇥ &nbsp; Keluar dari Dashboard
            </button>

        </div>

    </aside>


    <div
        class="mobile-overlay"
        id="mobileOverlay"
        onclick="closeSidebar()"
    ></div>


    <!-- MAIN -->

    <main class="main">


        <!-- TOPBAR -->

        <div class="topbar">

            <button
                class="mobile-menu"
                onclick="openSidebar()"
            >
                ☰
            </button>

            <div class="search-box">

                <span>⌕</span>

                <input
                    type="text"
                    id="searchInput"
                    placeholder="Cari menu atau layanan..."
                >

            </div>


            <div class="datetime">

                <div
                    class="time"
                    id="liveTime"
                >
                    00:00:00
                </div>

                <div
                    class="date"
                    id="liveDate"
                >
                    -
                </div>

            </div>

        </div>


        <div class="content">


            <!-- HERO -->

            <section
                class="hero"
                id="dashboardHome"
            >

                <div class="hero-content">

                    <div class="hero-badge">
                        DASHBOARD KEPEGAWAIAN
                    </div>

                    <h1>
                        Selamat Datang di<br>
                        Dishut Umum dan Kepegawaian
                    </h1>

                    <p>
                        Pusat informasi, administrasi, monitoring,
                        dan pengelolaan data kepegawaian
                        Dinas Kehutanan Provinsi Sulawesi Tenggara.
                    </p>

                </div>


                <img
                    class="hero-berakhlak"
                    src="https://www.pn-balige.go.id/images/2022_kegiatan/2022_oktober/beraklak_editjpg.jpg"
                    alt="BerAKHLAK"
                >

            </section>


            <!-- STATISTIK -->

            <section class="section">

                <div class="section-heading">

                    <div>
                        <h2>Ringkasan Dashboard</h2>

                        <p>
                            Akses cepat menuju informasi kepegawaian.
                        </p>
                    </div>

                </div>


                <div class="stats">

                    <div class="stat-card">

                        <div class="stat-top">

                            <div class="stat-icon">
                                👥
                            </div>

                        </div>

                        <div class="stat-number">
                            ASN
                        </div>

                        <div class="stat-label">
                            Data Pegawai
                        </div>

                    </div>


                    <div class="stat-card">

                        <div class="stat-top">

                            <div class="stat-icon">
                                📅
                            </div>

                        </div>

                        <div class="stat-number">
                            CUTI
                        </div>

                        <div class="stat-label">
                            Monitoring Cuti ASN
                        </div>

                    </div>


                    <div class="stat-card">

                        <div class="stat-top">

                            <div class="stat-icon">
                                📋
                            </div>

                        </div>

                        <div class="stat-number">
                            SKP
                        </div>

                        <div class="stat-label">
                            Pengelolaan SKP
                        </div>

                    </div>


                    <div class="stat-card">

                        <div class="stat-top">

                            <div class="stat-icon">
                                📊
                            </div>

                        </div>

                        <div class="stat-number">
                            MONITOR
                        </div>

                        <div class="stat-label">
                            Monitoring Kepegawaian
                        </div>

                    </div>

                </div>

            </section>


            <!-- DATA KEPEGAWAIAN -->

            <section
                class="section"
                id="dataKepegawaian"
            >

                <div class="section-heading">

                    <div>

                        <h2>
                            Data Kepegawaian
                        </h2>

                        <p>
                            Informasi dan monitoring data pegawai.
                        </p>

                    </div>

                </div>


                <div class="card-grid">


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1AAcaDiRG3B7wXMEjC9g78a54uBTFsgxi/edit?usp=drive_link&ouid=116310223780229839202&rtpof=true&sd=true"
                        target="_blank"
                    >

                        <div class="card-icon">
                            👤
                        </div>

                        <h3>
                            Data Pegawai
                        </h3>

                        <p>
                            Database dan informasi pegawai
                            Dinas Kehutanan.
                        </p>

                        <span class="card-arrow">
                            →
                        </span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/10dtFF5p6NHvVmcSomkCqwq2CtBS7KmHG/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            🗺
                        </div>

                        <h3>
                            Kondisi & Sebaran Pegawai
                        </h3>

                        <p>
                            Informasi kondisi dan sebaran
                            pegawai.
                        </p>

                        <span class="card-arrow">
                            →
                        </span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1UrQsubue8WStD1U3MKrrpaT7HbGW_EtS/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            📅
                        </div>

                        <h3>
                            Cuti ASN
                        </h3>

                        <p>
                            Monitoring dan rekapitulasi
                            cuti ASN.
                        </p>

                        <span class="card-arrow">
                            →
                        </span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1IRQ_RLLylcVkunQu3HXhmQsnahYVhAVS/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            🧹
                        </div>

                        <h3>
                            Apel & Korve
                        </h3>

                        <p>
                            Data pelaksanaan apel dan
                            kegiatan korve.
                        </p>

                        <span class="card-arrow">
                            →
                        </span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1A_ETSxw2ioKYag-4GDSYd7Le4vYt9fYd/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            🕘
                        </div>

                        <h3>
                            Rekap Absensi
                        </h3>

                        <p>
                            Rekapitulasi kehadiran dan
                            absensi pegawai.
                        </p>

                        <span class="card-arrow">
                            →
                        </span>

                    </a>

                </div>

            </section>


            <!-- ADMINISTRASI ASN -->

            <section
                class="section"
                id="administrasi"
            >

                <div class="section-heading">

                    <div>

                        <h2>
                            Administrasi ASN
                        </h2>

                        <p>
                            Layanan dan administrasi kepegawaian.
                        </p>

                    </div>

                </div>


                <div class="card-grid">


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1VRY-CMaCrUWxQ8Aa7io6dWzszoeE0Xnt/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            📈
                        </div>

                        <h3>
                            Kenaikan Pangkat
                        </h3>

                        <p>
                            Data usulan dan monitoring
                            kenaikan pangkat ASN.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1RDE8mQpYCz_jmSZ9fmK_ehECezDJgc4c/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            💰
                        </div>

                        <h3>
                            Pajak Tahunan
                        </h3>

                        <p>
                            Monitoring administrasi pajak
                            tahunan pegawai.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1dslIky6EZvKq6K6Ue-sR6-OPyYrXvdL7/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            📝
                        </div>

                        <h3>
                            Pengumpulan SKP 2025
                        </h3>

                        <p>
                            Monitoring pengumpulan SKP
                            Tahun 2025.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1G-OhNMMkkYbX1Z-7_pqjfGN6uObcx4ag/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            👴
                        </div>

                        <h3>
                            Data Pensiun 2026
                        </h3>

                        <p>
                            Data dan monitoring pegawai
                            yang memasuki masa pensiun.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1ApZeoVANQRyBKV9sJQuJc2IkgF1ti464/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            💵
                        </div>

                        <h3>
                            Statistik KGB
                        </h3>

                        <p>
                            Statistik Kenaikan Gaji Berkala.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://drive.google.com/drive/folders/1GK6Ljt2Y63yaekmQwvD6wHUQBH3hvbxU"
                        target="_blank"
                    >

                        <div class="card-icon">
                            📂
                        </div>

                        <h3>
                            Folder SKP 2025
                        </h3>

                        <p>
                            Folder dokumen SKP Tahun 2025.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://skm.go.id/share/instansi/7182ea78-e689-4f51-80a7-b9bea7fe5174/1"
                        target="_blank"
                    >

                        <div class="card-icon">
                            ⭐
                        </div>

                        <h3>
                            Survei Kepuasan Masyarakat
                        </h3>

                        <p>
                            Akses Survei Kepuasan Masyarakat
                            Dinas Kehutanan.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>

                </div>

            </section>


            <!-- MONITORING -->

            <section
                class="section"
                id="monitoring"
            >

                <div class="section-heading">

                    <div>

                        <h2>
                            Monitoring
                        </h2>

                        <p>
                            Pemantauan kegiatan dan administrasi.
                        </p>

                    </div>

                </div>


                <div class="card-grid">


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1IRQ_RLLylcVkunQu3HXhmQsnahYVhAVS/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            📣
                        </div>

                        <h3>
                            Monitoring Apel & Korve
                        </h3>

                        <p>
                            Pantau kegiatan apel dan korve.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://docs.google.com/spreadsheets/d/1A_ETSxw2ioKYag-4GDSYd7Le4vYt9fYd/edit"
                        target="_blank"
                    >

                        <div class="card-icon">
                            ⏱
                        </div>

                        <h3>
                            Monitoring Absensi
                        </h3>

                        <p>
                            Pantau data kehadiran pegawai.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://skm.go.id/share/instansi/7182ea78-e689-4f51-80a7-b9bea7fe5174/1"
                        target="_blank"
                    >

                        <div class="card-icon">
                            ⭐
                        </div>

                        <h3>
                            Survei Kepuasan Masyarakat 2026
                        </h3>

                        <p>
                            Akses hasil dan informasi
                            Survei Kepuasan Masyarakat.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>


                    <a
                        class="dashboard-card searchable"
                        href="https://kepegawaianboby.blogspot.com/2023/02/kumpulan-peraturan.html"
                        target="_blank"
                    >

                        <div class="card-icon">
                            ⚖
                        </div>

                        <h3>
                            Kumpulan Peraturan
                        </h3>

                        <p>
                            Kumpulan peraturan dan regulasi
                            bidang kepegawaian.
                        </p>

                        <span class="card-arrow">→</span>

                    </a>

                </div>

            </section>


            <!-- INFORMASI -->

            <section
                class="section"
                id="informasi"
            >

                <div class="section-heading">

                    <div>

                        <h2>
                            Informasi & Akses Cepat
                        </h2>

                        <p>
                            Portal informasi pendukung.
                        </p>

                    </div>

                </div>


                <div class="info-panel">


                    <div class="info-box">

                        <h3>
                            Informasi Dashboard
                        </h3>

                        <p>
                            Dashboard ini digunakan sebagai
                            pusat akses informasi administrasi
                            dan kepegawaian pada Dinas Kehutanan
                            Provinsi Sulawesi Tenggara,
                            khususnya Sub Bagian Umum & Kepegawaian.
                        </p>


                        <div class="social-row">

                            <a
                                class="social-link"
                                href="https://www.instagram.com/dishutumkep?igsh=MTYxNHIyYTdwZXN4bQ%3D%3D"
                                target="_blank"
                            >
                                ◎ Instagram
                            </a>


                            <a
                                class="social-link"
                                href="https://api.whatsapp.com/send/?phone=08131153574&text&type=phone_number&app_absent=0"
                                target="_blank"
                            >
                                ◉ WhatsApp
                            </a>

                        </div>

                    </div>


                    <div class="info-box">

                        <h3>
                            Akses Cepat
                        </h3>

                        <div class="quick-list">


                            <a
                                class="quick-link searchable"
                                href="https://myasn.bkn.go.id/"
                                target="_blank"
                            >
                                <span>ASN Digital</span>
                                <span>→</span>
                            </a>


                            <a
                                class="quick-link searchable"
                                href="https://kepegawaianboby.blogspot.com/2023/02/kumpulan-peraturan.html"
                                target="_blank"
                            >
                                <span>Kumpulan Peraturan</span>
                                <span>→</span>
                            </a>


                            <a
                                class="quick-link searchable"
                                href="https://sites.google.com/view/dishutumkep/profil-dinas-kehutanan"
                                target="_blank"
                            >
                                <span>Profil Dinas</span>
                                <span>→</span>
                            </a>


                            <a
                                class="quick-link searchable"
                                href="https://sites.google.com/view/dishutumkep/tugas-dan-fungsi-dinas-kehutanan"
                                target="_blank"
                            >
                                <span>Tugas & Fungsi</span>
                                <span>→</span>
                            </a>


                            <a
                                class="quick-link searchable"
                                href="https://drive.google.com/drive/folders/1GK6Ljt2Y63yaekmQwvD6wHUQBH3hvbxU"
                                target="_blank"
                            >
                                <span>Folder SKP 2025</span>
                                <span>→</span>
                            </a>


                            <a
                                class="quick-link searchable"
                                href="https://skm.go.id/share/instansi/7182ea78-e689-4f51-80a7-b9bea7fe5174/1"
                                target="_blank"
                            >
                                <span>Survei Kepuasan Masyarakat</span>
                                <span>→</span>
                            </a>

                        </div>

                    </div>

                </div>

            </section>


            <!-- FOOTER -->

            <footer class="footer">

                <strong>
                    Dishut Umum dan Kepegawaian
                </strong>

                <br>

                Dinas Kehutanan Provinsi Sulawesi Tenggara

                <br>

                Sub Bagian Umum & Kepegawaian

                <br><br>

                <span id="year"></span>
                © Dashboard Kepegawaian

                <br>

                <em>
                    Bangga Melayani Bangsa
                </em>

            </footer>


        </div>

    </main>


    <!-- FLOATING WHATSAPP -->

    <a
        class="floating-wa"
        href="https://api.whatsapp.com/send/?phone=08131153574&text&type=phone_number&app_absent=0"
        target="_blank"
        title="Hubungi WhatsApp"
    >
        ◉
    </a>

</div>


<script>

/* =========================================================
   LOGIN
========================================================= */

const USERNAME_BENAR = "umkep";
const PASSWORD_BENAR = "umkepdishut";


const loginForm = document.getElementById("loginForm");

loginForm.addEventListener("submit", function(event){

    event.preventDefault();

    const username =
        document.getElementById("username").value.trim();

    const password =
        document.getElementById("password").value;

    const error =
        document.getElementById("loginError");

    if(
        username === USERNAME_BENAR &&
        password === PASSWORD_BENAR
    ){

        error.classList.remove("show");

        document.getElementById("loginPage").style.display = "none";

        document.getElementById("dashboard").classList.add("active");

        window.scrollTo(0,0);

    }else{

        error.classList.remove("show");

        void error.offsetWidth;

        error.classList.add("show");

        document.getElementById("password").value = "";

        document.getElementById("username").focus();

    }

});


/* =========================================================
   TOGGLE PASSWORD
========================================================= */

function togglePassword(){

    const password =
        document.getElementById("password");

    const toggle =
        document.getElementById("passwordToggle");

    if(password.type === "password"){

        password.type = "text";

        toggle.textContent = "🙈";

    }else{

        password.type = "password";

        toggle.textContent = "👁";

    }

}


/* =========================================================
   LOGOUT
========================================================= */

function logout(){

    document.getElementById("dashboard")
        .classList.remove("active");

    document.getElementById("loginPage")
        .style.display = "flex";

    document.getElementById("username").value = "";

    document.getElementById("password").value = "";

    document.getElementById("loginError")
        .classList.remove("show");

    window.scrollTo(0,0);

}


/* =========================================================
   DATE & TIME
========================================================= */

function updateDateTime(){

    const now = new Date();

    const time =
        now.toLocaleTimeString(
            "id-ID",
            {
                hour:"2-digit",
                minute:"2-digit",
                second:"2-digit"
            }
        );

    const date =
        now.toLocaleDateString(
            "id-ID",
            {
                weekday:"long",
                day:"numeric",
                month:"long",
                year:"numeric"
            }
        );

    document.getElementById("liveTime")
        .textContent = time;

    document.getElementById("liveDate")
        .textContent = date;

}

setInterval(updateDateTime,1000);

updateDateTime();


/* =========================================================
   YEAR
========================================================= */

document.getElementById("year")
    .textContent = new Date().getFullYear();


/* =========================================================
   MOBILE SIDEBAR
========================================================= */

function openSidebar(){

    document
        .getElementById("sidebar")
        .classList.add("open");

    document
        .getElementById("mobileOverlay")
        .classList.add("show");

}


function closeSidebar(){

    document
        .getElementById("sidebar")
        .classList.remove("open");

    document
        .getElementById("mobileOverlay")
        .classList.remove("show");

}


/* =========================================================
   ACTIVE MENU
========================================================= */

document
    .querySelectorAll(".nav-item")
    .forEach(function(item){

        item.addEventListener("click",function(){

            document
                .querySelectorAll(".nav-item")
                .forEach(function(nav){

                    nav.classList.remove("active");

                });

            this.classList.add("active");

            closeSidebar();

        });

    });


/* =========================================================
   SEARCH DASHBOARD
========================================================= */

const searchInput =
    document.getElementById("searchInput");

searchInput.addEventListener(
    "input",
    function(){

        const keyword =
            this.value.toLowerCase().trim();

        document
            .querySelectorAll(".searchable")
            .forEach(function(card){

                const text =
                    card.innerText.toLowerCase();

                if(
                    keyword === "" ||
                    text.includes(keyword)
                ){

                    card.classList.remove(
                        "hidden-search"
                    );

                }else{

                    card.classList.add(
                        "hidden-search"
                    );

                }

            });

    }
);


/* =========================================================
   ENTER LOGIN
========================================================= */

document
    .getElementById("password")
    .addEventListener(
        "keydown",
        function(event){

            if(event.key === "Enter"){

                loginForm.requestSubmit();

            }

        }
    );

</script>

</body>
</html>
