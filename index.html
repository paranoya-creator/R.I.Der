<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>R.I.D — Legion Control</title>
    <link href="https://googleapis.com" rel="stylesheet">
    <script src="https://unpkg.com"></script>
    <style>
        :root {
            --bg: #06030a;
            --panel: #0f0a1a;
            --accent: #9d00ff;
            --accent-glow: rgba(157, 0, 255, 0.4);
            --text: #ffffff;
        }

        body { background: var(--bg); color: var(--text); font-family: 'Inter', sans-serif; margin: 0; }
        
        /* Навигация */
        nav {
            display: flex; justify-content: space-between; align-items: center;
            padding: 15px 30px; background: rgba(6, 3, 10, 0.95);
            border-bottom: 1px solid var(--accent); box-shadow: 0 4px 20px var(--accent-glow);
            position: sticky; top: 0; z-index: 1000;
        }

        .logo-box { cursor: pointer; transition: 0.2s; }
        .logo-box img { height: 45px; display: block; border-radius: 5px; }

        .btn-icon {
            background: var(--panel); border: 1px solid var(--accent); color: white;
            padding: 10px; border-radius: 12px; cursor: pointer; transition: 0.3s;
        }
        .btn-icon:hover { background: var(--accent); box-shadow: 0 0 15px var(--accent); }

        .container { max-width: 1200px; margin: 0 auto; padding: 20px; }
        .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 25px; }

        /* Карточки */
        .card { background: var(--panel); border: 1px solid #1e1533; border-radius: 20px; overflow: hidden; transition: 0.4s; }
        .card:hover { border-color: var(--accent); transform: translateY(-5px); }
        .card-info { padding: 20px; text-align: center; }

        .buy-btn {
            background: var(--accent); color: white; border: none; padding: 12px;
            width: 100%; border-radius: 10px; font-weight: bold; cursor: pointer;
            display: flex; align-items: center; justify-content: center; gap: 8px;
        }

        /* Модалки */
        .modal {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.9); backdrop-filter: blur(10px); z-index: 2000;
        }
        .modal-content {
            background: var(--panel); width: 90%; max-width: 450px;
            margin: 50px auto; padding: 30px; border-radius: 24px;
            border: 1px solid var(--accent); position: relative; max-height: 80vh; overflow-y: auto;
        }

        input, select {
            width: 100%; padding: 12px; margin: 8px 0;
            background: #06030a; border: 1px solid #332755;
            color: white; border-radius: 8px; box-sizing: border-box;
        }

        /* Консультанты в настройках */
        .staff-item {
            background: #150f25; padding: 15px; border-radius: 15px;
            margin-bottom: 15px; display: flex; align-items: center; gap: 15px;
            border: 1px solid transparent; transition: 0.3s;
        }
        .staff-item:hover { border-color: var(--accent); }
        .staff-avatar { width: 50px; height: 50px; border-radius: 50%; object-fit: cover; background: var(--accent); display: flex; align-items: center; justify-content: center; }
        .staff-info b { color: var(--accent); font-size: 0.7rem; text-transform: uppercase; }
        .tg-link { color: #0088cc; text-decoration: none; font-size: 0.8rem; display: flex; align-items: center; gap: 5px; }

        .admin-section { border-top: 1px solid #333; margin-top: 20px; padding-top: 20px; }
        .close-btn { float: right; cursor: pointer; color: #555; }
    </style>
</head>
<body>

<nav>
    <div class="logo-box" onclick="adminClick()" title="Нажми 5 раз для входа в админку">
        <img src="logo.png" alt="R.I.D" onerror="this.src='https://placeholder.com'">
    </div>
    <div style="display: flex; gap: 10px;">
        <button class="btn-icon" onclick="toggleM('profile-modal')"><i data-lucide="user"></i></button>
        <button class="btn-icon" onclick="toggleM('settings-modal')"><i data-lucide="settings"></i></button>
    </div>
</nav>

<div class="container">
    <h2 style="font-family: 'Orbitron'; margin-bottom: 30px;">КАТАЛОГ LEGION</h2>
    <div class="grid" id="catalog"></div>
</div>

<!-- Модалка: Настройки (Консультанты) -->
<div id="settings-modal" class="modal">
    <div class="modal-content">
        <span class="close-btn" onclick="toggleM('settings-modal')"><i data-lucide="x"></i></span>
        <h2 style="font-family: 'Orbitron'">Команда</h2>
        <div id="staff-list-display"></div>
    </div>
</div>

<!-- Модалка: Профиль -->
<div id="profile-modal" class="modal">
    <div class="modal-content">
        <span class="close-btn" onclick="toggleM('profile-modal')"><i data-lucide="x"></i></span>
        <div id="auth-ui">
            <h3>Вход в Легион</h3>
            <input type="text" id="u-name" placeholder="Твое Имя">
            <input type="email" id="u-mail" placeholder="Твоя Почта">
            <button class="buy-btn" onclick="login()">ВОЙТИ</button>
        </div>
        <div id="user-ui" style="display:none;">
            <h2 id="hello" style="font-family: 'Orbitron'"></h2>
            <p style="color:var(--accent)">Статус: Активен</p>
            <button class="buy-btn" onclick="logout()" style="background:#222">ВЫЙТИ</button>
        </div>
    </div>
</div>

<!-- Скрытая Админка -->
<div id="admin-modal" class="modal">
    <div class="modal-content" style="max-width: 500px;">
        <span class="close-btn" onclick="toggleM('admin-modal')"><i data-lucide="x"></i></span>
        <h2 style="font-family: 'Orbitron'">Система</h2>
        
        <div id="admin-auth">
            <input type="password" id="a-pass" placeholder="Пароль">
            <button class="buy-btn" onclick="checkAdmin()">ВХОД</button>
        </div>

        <div id="admin-main" style="display:none;">
            <div class="admin-section">
                <h4>📦 Добавить товар</h4>
                <input type="text" id="p-name" placeholder="Название">
                <input type="text" id="p-price" placeholder="Цена">
                <button class="buy-btn" onclick="addItem()">ОПУБЛИКОВАТЬ</button>
            </div>

            <div class="admin-section">
                <h4>👥 Управление персоналом</h4>
                <select id="staff-select">
                    <option value="0">Консультант #1 (Владелец)</option>
                    <option value="1">Консультант #2 (Зам)</option>
                    <option value="2">Консультант #3 (Админ)</option>
                </select>
                <input type="text" id="st-name" placeholder="Новый Ник">
                <input type="text" id="st-img" placeholder="Ссылка на аватар (URL)">
                <input type="text" id="st-tg" placeholder="Ссылка на Telegram (t.me/...)">
                <button class="buy-btn" style="background:#00b140" onclick="updateStaff()">ОБНОВИТЬ ДАННЫЕ</button>
            </div>
        </div>
    </div>
</div>

<script>
    // Начальные данные (если память пуста)
    let products = JSON.parse(localStorage.getItem('rid_v3_prod')) || [
        {name: "Legion Hoodie", price: "5500 ₽"},
        {name: "R.I.D Accessory", price: "1200 ₽"}
    ];
    let staff = JSON.parse(localStorage.getItem('rid_v3_staff')) || [
        {role: "Владелец", name: "R.I.D Main", img: "", tg: "#"},
        {role: "Зам. Владельца", name: "Legion Support", img: "", tg: "#"},
        {role: "Администратор", name: "Staff Manager", img: "", tg: "#"}
    ];
    let user = JSON.parse(localStorage.getItem('rid_v3_user')) || null;
    let clicks = 0;

    function render() {
        // Рендер товаров
        const catalog = document.getElementById('catalog');
        catalog.innerHTML = products.map(p => `
            <div class="card">
                <div style="height:200px; display:flex; align-items:center; justify-content:center; background:#110a20; font-size:3rem;">📦</div>
                <div class="card-info">
                    <h3 style="font-family:'Orbitron'">${p.name}</h3>
                    <div style="color:var(--accent); font-weight:bold; font-size:1.4rem; margin:10px 0;">${p.price}</div>
                    <button class="buy-btn" onclick="alert('Заказ создан!')"><i data-lucide="shopping-cart" size="18"></i> КУПИТЬ</button>
                </div>
            </div>
        `).join('');

        // Рендер консультантов в настройках
        const staffList = document.getElementById('staff-list-display');
        staffList.innerHTML = staff.map(s => `
            <div class="staff-item">
                <div class="staff-avatar">
                    ${s.img ? `<img src="${s.img}" style="width:100%; height:100%; border-radius:50%; object-fit:cover;">` : `<i data-lucide="user"></i>`}
                </div>
                <div class="staff-info">
                    <b>${s.role}</b><br>
                    <span>${s.name}</span><br>
                    <a href="${s.tg}" target="_blank" class="tg-link"><i data-lucide="send" size="12"></i> Telegram</a>
                </div>
            </div>
        `).join('');

        lucide.createIcons();
        updateProfileUI();
    }

    // Админка
    function adminClick() {
        clicks++;
        if(clicks >= 5) { toggleM('admin-modal'); clicks = 0; }
        setTimeout(() => clicks = 0, 2000);
    }

    function checkAdmin() {
        if(document.getElementById('a-pass').value === 'rid') {
            document.getElementById('admin-auth').style.display = 'none';
            document.getElementById('admin-main').style.display = 'block';
        }
    }

    function updateStaff() {
        const id = document.getElementById('staff-select').value;
        const newName = document.getElementById('st-name').value;
        const newImg = document.getElementById('st-img').value;
        const newTg = document.getElementById('st-tg').value;

        if(newName) staff[id].name = newName;
        if(newImg) staff[id].img = newImg;
        if(newTg) staff[id].tg = newTg;

        localStorage.setItem('rid_v3_staff', JSON.stringify(staff));
        render();
        alert("Данные персонала обновлены!");
    }

    function addItem() {
        const name = document.getElementById('p-name').value;
        const price = document.getElementById('p-price').value;
        if(name && price) {
            products.push({name, price});
            localStorage.setItem('rid_v3_prod', JSON.stringify(products));
            render();
        }
    }

    // Профиль
    function login() {
        const n = document.getElementById('u-name').value;
        const m = document.getElementById('u-mail').value;
        if(n && m) {
            user = {name: n, email: m};
            localStorage.setItem('rid_v3_user', JSON.stringify(user));
            render();
        }
    }
    function logout() { localStorage.removeItem('rid_v3_user'); user = null; render(); }

    function updateProfileUI() {
        if(user) {
            document.getElementById('auth-ui').style.display = 'none';
            document.getElementById('user-ui').style.display = 'block';
            document.getElementById('hello').innerText = user.name;
        } else {
            document.getElementById('auth-ui').style.display = 'block';
            document.getElementById('user-ui').style.display = 'none';
        }
    }

    function toggleM(id) {
        const m = document.getElementById(id);
        m.style.display = m.style.display === 'block' ? 'none' : 'block';
    }

    render();
</script>
</body>
</html>
