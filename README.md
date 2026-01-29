<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Boshquduq MFY Portali</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.1/font/bootstrap-icons.css">
    <style>
        :root { --primary: #0d6efd; --bg: #f1f5f9; }
        body { background: var(--bg); font-family: 'Inter', sans-serif; margin: 0; padding-bottom: 90px; overflow-x: hidden; }
        
        /* 1. INTRO EKRAN */
        #gerb-screen {
            position: fixed; top: 0; left: 0; height: 100vh; width: 100vw;
            display: flex; flex-direction: column; justify-content: center; align-items: center;
            background: radial-gradient(circle at center, #1e3c72 0%, #061122 100%);
            z-index: 2000; transition: transform 0.8s cubic-bezier(0.85, 0, 0.15, 1);
        }
        .gerb-inner { width: 55vw; max-width: 220px; animation: spin 4s ease-in-out forwards; }
        @keyframes spin { from { transform: rotateY(0deg); } to { transform: rotateY(360deg); } }
        .slide-up { transform: translateY(-100vh); }

        /* 2. PAGE SECTIONS */
        .page-section { display: none; padding: 20px 0; animation: fadeIn 0.4s ease; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        /* 3. YETTILIK DIZAYNI */
        .yettilik-scroll { display: flex; overflow-x: auto; padding: 15px; gap: 12px; scrollbar-width: none; -webkit-overflow-scrolling: touch; }
        .yettilik-scroll::-webkit-scrollbar { display: none; }
        .staff-card { flex: 0 0 160px; background: white; border-radius: 22px; padding: 20px 10px; text-align: center; box-shadow: 0 4px 12px rgba(0,0,0,0.03); border: 1px solid rgba(0,0,0,0.02); }
        .icon-circle { width: 55px; height: 55px; border-radius: 18px; display: flex; align-items: center; justify-content: center; margin: 0 auto 12px; font-size: 1.5rem; }
        
        .c-1 { background: #e7f1ff; color: #0d6efd; } .c-2 { background: #e6fffa; color: #00b5ad; }
        .c-3 { background: #fff5f5; color: #e53e3e; } .c-4 { background: #fffaf0; color: #dd6b20; }
        .c-5 { background: #ebf4ff; color: #3182ce; } .c-6 { background: #faf5ff; color: #805ad5; }
        .c-7 { background: #f0fff4; color: #38a169; }

        .role-label { font-size: 0.8rem; font-weight: 700; height: 40px; margin-bottom: 12px; color: #334155; display: flex; align-items: center; justify-content: center; line-height: 1.1; }

        /* 4. STATISTIKA */
        .stats-card { background: white; margin: 15px; padding: 22px; border-radius: 28px; box-shadow: 0 5px 25px rgba(0,0,0,0.04); }
        .stat-box { background: #f8fafc; padding: 15px 10px; border-radius: 18px; text-align: center; border: 1px solid #f1f5f9; height: 100%; }
        .stat-box i { font-size: 1.3rem; display: block; margin-bottom: 5px; }
        .stat-box b { font-size: 1.1rem; color: #1e293b; display: block; }

        /* 5. KO'CHALAR VA XIZMATLAR */
        .service-item {
            background: white; border-radius: 18px; padding: 15px 20px;
            display: flex; align-items: center; justify-content: space-between;
            margin: 0 15px 10px; border: 1px solid rgba(0,0,0,0.02);
            text-decoration: none; color: #334155; box-shadow: 0 2px 8px rgba(0,0,0,0.02);
            transition: 0.2s;
        }
        .service-item:active { background: #f1f5f9; transform: scale(0.98); }

        /* 6. NAVBAR */
        .bottom-nav {
            position: fixed; bottom: 0; left: 0; right: 0; height: 75px;
            background: rgba(255, 255, 255, 0.95); backdrop-filter: blur(10px);
            display: none; justify-content: space-around; align-items: center;
            box-shadow: 0 -5px 20px rgba(0,0,0,0.05); border-top-left-radius: 25px; border-top-right-radius: 25px; z-index: 1000;
        }
        .nav-item { text-align: center; color: #64748b; text-decoration: none; font-size: 0.65rem; font-weight: 600; }
        .nav-item i { font-size: 1.5rem; display: block; margin-bottom: 2px; }
        .nav-item.active { color: var(--primary); }

        /* HOUSE PAGE HEADER */
        .house-header { background: white; padding: 15px 20px; display: flex; align-items: center; position: sticky; top: 0; z-index: 100; box-shadow: 0 2px 10px rgba(0,0,0,0.05); }
    </style>
</head>
<body>

<div id="gerb-screen">
    <div class="gerb-inner" id="gerbAnim">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/77/Emblem_of_Uzbekistan.svg/800px-Emblem_of_Uzbekistan.svg.png" width="100%">
    </div>
    <div class="mt-4 text-center text-white">
        <h1 class="h6 fw-bold animate__animated animate__fadeInUp">O'ZBEKISTON RESPUBLIKASI</h1>
        <p class="small opacity-50">Boshquduq MFY Portali</p>
    </div>
</div>

<div id="home-page" class="page-section">
    <h6 class="fw-bold px-4 mb-1">Mahalla yettiligi</h6>
    <div class="yettilik-scroll">
        <div class="staff-card" onclick="openM('Mahalla raisi', 'Sultonov Ahmed', '+998 90 111 01 01', 'c-1', 'bi-person-badge')">
            <div class="icon-circle c-1"><i class="bi bi-person-badge"></i></div>
            <div class="role-label">Mahalla raisi</div>
            <button class="btn btn-sm btn-primary w-100 rounded-pill">Ko'rish</button>
        </div>
        <div class="staff-card" onclick="openM('Hokim yordamchisi', 'Karimov Jalol', '+998 90 222 02 02', 'c-2', 'bi-briefcase')">
            <div class="icon-circle c-2"><i class="bi bi-briefcase"></i></div>
            <div class="role-label">Hokim yordamchisi</div>
            <button class="btn btn-sm btn-success w-100 rounded-pill">Ko'rish</button>
        </div>
        <div class="staff-card" onclick="openM('Yoshlar yetakchisi', 'Azimov Aziz', '+998 90 333 03 03', 'c-3', 'bi-rocket-takeoff')">
            <div class="icon-circle c-3"><i class="bi bi-rocket-takeoff"></i></div>
            <div class="role-label">Yoshlar yetakchisi</div>
            <button class="btn btn-sm btn-danger w-100 rounded-pill">Ko'rish</button>
        </div>
        <div class="staff-card" onclick="openM('Xotin-qizlar faoli', 'Umurova Nilufar', '+998 90 444 04 04', 'c-4', 'bi-person-heart')">
            <div class="icon-circle c-4"><i class="bi bi-person-heart"></i></div>
            <div class="role-label">Xotin-qizlar faoli</div>
            <button class="btn btn-sm btn-warning text-white w-100 rounded-pill">Ko'rish</button>
        </div>
        <div class="staff-card" onclick="openM('Profilaktika inspektori', 'Jumanov Botir', '+998 90 555 05 05', 'c-5', 'bi-shield-check')">
            <div class="icon-circle c-5"><i class="bi bi-shield-check"></i></div>
            <div class="role-label">Profilaktika inspektori</div>
            <button class="btn btn-sm btn-info text-white w-100 rounded-pill">Ko'rish</button>
        </div>
        <div class="staff-card" onclick="openM('Soliq inspektori', 'Hasanov Erkin', '+998 90 666 06 06', 'c-6', 'bi-graph-up-arrow')">
            <div class="icon-circle c-6"><i class="bi bi-graph-up-arrow"></i></div>
            <div class="role-label">Soliq inspektori</div>
            <button class="btn btn-sm btn-secondary w-100 rounded-pill">Ko'rish</button>
        </div>
        <div class="staff-card" onclick="openM('Ijtimoiy xodim', 'Bakirova Dilfuza', '+998 90 777 07 07', 'c-7', 'bi-house-heart')">
            <div class="icon-circle c-7"><i class="bi bi-house-heart"></i></div>
            <div class="role-label">Ijtimoiy xodim</div>
            <button class="btn btn-sm btn-dark w-100 rounded-pill">Ko'rish</button>
        </div>
    </div>

    <div class="stats-card">
        <h6 class="fw-bold mb-3"><i class="bi bi-bar-chart-fill me-2 text-primary"></i>Statistika</h6>
        <div class="row g-2">
            <div class="col-6"><div class="stat-box"><i class="bi bi-people text-primary"></i><small>Jami</small><b>3,450</b></div></div>
            <div class="col-6"><div class="stat-box"><i class="bi bi-gender-male text-info"></i><small>Erkaklar</small><b>1,740</b></div></div>
            <div class="col-6"><div class="stat-box"><i class="bi bi-gender-female text-danger"></i><small>Ayollar</small><b>1,710</b></div></div>
            <div class="col-6"><div class="stat-box"><i class="bi bi-mortarboard text-warning"></i><small>Yoshlar</small><b>1,120</b></div></div>
        </div>
    </div>
</div>

<div id="services-page" class="page-section">
    <h5 class="fw-bold px-4 mb-3">Ma'lumotnomalar</h5>
    <a href="https://my.gov.uz/oz/service/313" class="service-item">
        <div class="d-flex align-items-center">
            <div class="icon-circle c-1 me-3" style="width:40px;height:40px;"><i class="bi bi-file-earmark-text small"></i></div>
            <div><h6 class="mb-0 fw-bold">Yashash joyidan</h6><small class="text-muted">Elektron olish</small></div>
        </div>
        <i class="bi bi-chevron-right"></i>
    </a>

    <h5 class="fw-bold px-4 mt-4 mb-3">Boshquduq MFY Ko'chalari</h5>
    <div id="street-list"></div>
</div>

<div id="houses-page" class="page-section">
    <div class="house-header">
        <i class="bi bi-arrow-left fs-4 me-3 text-primary" onclick="switchPage('services', document.querySelectorAll('.nav-item')[1])" style="cursor:pointer"></i>
        <h6 id="current-street-name" class="fw-bold mb-0"></h6>
    </div>
    <div id="houses-list" class="mt-3"></div>
</div>

<div class="modal fade" id="m" tabindex="-1"><div class="modal-dialog modal-dialog-centered mx-3"><div class="modal-content shadow-lg border-0 rounded-4"><div class="modal-body text-center p-4">
    <div id="mi" class="icon-circle mb-3 mx-auto" style="width:75px; height:75px; font-size:2rem;"><i></i></div>
    <h4 id="mn" class="fw-bold mb-4"></h4>
    <div class="bg-light p-3 rounded-3 text-start mb-4">
        <small class="text-muted d-block small">Aloqa uchun:</small>
        <a id="mt" href="#" class="fw-bold text-primary text-decoration-none h5"></a>
    </div>
    <button class="btn btn-dark w-100 rounded-pill" data-bs-dismiss="modal">YOPISH</button>
</div></div></div></div>

<div class="bottom-nav" id="b-nav">
    <a href="javascript:void(0)" class="nav-item active" onclick="switchPage('home', this)">
        <i class="bi bi-house-door-fill"></i><span>Asosiy</span>
    </a>
    <a href="javascript:void(0)" class="nav-item" onclick="switchPage('services', this)">
        <i class="bi bi-grid-fill"></i><span>Xizmatlar</span>
    </a>
    <a href="javascript:void(0)" class="nav-item" onclick="alert('Tez kunda...')">
        <i class="bi bi-chat-dots-fill"></i><span>Murojaat</span>
    </a>
    <a href="javascript:void(0)" class="nav-item" onclick="location.reload()">
        <i class="bi bi-arrow-clockwise"></i><span>Yangilash</span>
    </a>
</div>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
<script>
    // Intro handling
    document.getElementById('gerbAnim').addEventListener('animationend', () => {
        setTimeout(() => { 
            document.getElementById('gerb-screen').classList.add('slide-up'); 
            document.getElementById('home-page').style.display = 'block'; 
            document.getElementById('b-nav').style.display = 'flex';
        }, 500);
    });

    // Generate Streets
    const streetContainer = document.getElementById('street-list');
    for (let i = 1; i <= 10; i++) {
        streetContainer.innerHTML += `
            <div class="service-item" onclick="openHouses(${i})">
                <div class="d-flex align-items-center">
                    <div class="icon-circle bg-light text-dark mb-0 me-3" style="width:40px;height:40px;border-radius:10px;"><i class="bi bi-geo-alt small"></i></div>
                    <div><h6 class="mb-0 fw-bold">Boshquduq ${i}-ko'cha</h6><small class="text-muted">MFY ichki yo'li</small></div>
                </div>
                <i class="bi bi-chevron-right text-muted"></i>
            </div>`;
    }

    // Generate 80 Houses
    function openHouses(id) {
        switchPage('houses');
        document.getElementById('current-street-name').innerText = id + "-ko'cha xonadonlari";
        const hList = document.getElementById('houses-list');
        hList.innerHTML = '';
        for (let h = 1; h <= 80; h++) {
            hList.innerHTML += `
                <div class="service-item">
                    <div class="d-flex align-items-center">
                        <div class="icon-circle bg-white border mb-0 me-3" style="width:40px;height:40px;border-radius:10px; color:#e91e63;"><i class="bi bi-house-door small"></i></div>
                        <div><h6 class="mb-0 fw-bold">${h}-xonadon</h6><small class="text-muted">ID: BQ-${id}${h.toString().padStart(2, '0')}</small></div>
                    </div>
                    <i class="bi bi-info-circle text-muted"></i>
                </div>`;
        }
    }

    // Switch Pages
    function switchPage(page, el) {
        document.querySelectorAll('.page-section').forEach(p => p.style.display = 'none');
        document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
        document.getElementById(page + '-page').style.display = 'block';
        if(el) el.classList.add('active');
        window.scrollTo(0,0);
    }

    // Modal
    function openM(role, name, tel, color, icon) {
        document.getElementById('mn').innerText = name;
        document.getElementById('mt').innerText = tel;
        document.getElementById('mt').href = "tel:" + tel;
        document.getElementById('mi').className = "icon-circle mb-3 " + color;
        document.getElementById('mi').querySelector('i').className = "bi " + icon;
        new bootstrap.Modal(document.getElementById('m')).show();
    }
</script>
</body>
</html>
