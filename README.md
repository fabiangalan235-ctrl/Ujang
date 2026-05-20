<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes, viewport-fit=cover">
  <title>Galan • Keuangan Jajan</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #1a1e2b 0%, #2a2f3f 100%);
      font-family: 'Segoe UI', Roboto, system-ui, -apple-system, sans-serif;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 1.25rem;
      margin: 0;
    }

    .app-container {
      width: 100%;
      max-width: 480px;
      background: rgba(255, 255, 255, 0.07);
      backdrop-filter: blur(24px);
      -webkit-backdrop-filter: blur(24px);
      border-radius: 2.5rem;
      padding: 1.75rem 1.5rem 2.2rem;
      box-shadow: 0 30px 50px rgba(0, 0, 0, 0.5), inset 0 1px 0 rgba(255, 255, 255, 0.1);
      border: 1px solid rgba(255, 255, 255, 0.08);
      color: #f0f2f5;
      transition: all 0.2s ease;
    }

    .header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 2rem;
      flex-wrap: wrap;
      gap: 0.5rem;
    }

    .logo-section {
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .logo-icon {
      background: #fbbf24;
      color: #0f172a;
      font-weight: 800;
      font-size: 1.8rem;
      width: 48px;
      height: 48px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 18px;
      box-shadow: 0 12px 18px -8px rgba(251, 191, 36, 0.4);
      transform: rotate(2deg);
      transition: transform 0.2s;
      cursor: pointer;
    }

    .logo-icon:active {
      transform: rotate(0deg) scale(0.94);
    }

    .app-name {
      font-size: 2.2rem;
      font-weight: 700;
      letter-spacing: -0.5px;
      background: linear-gradient(to right, #fbbf24, #f59e0b);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      cursor: pointer;
      transition: opacity 0.2s;
      line-height: 1.1;
    }

    .app-name:active {
      opacity: 0.8;
    }

    .balance-card {
      background: rgba(255, 255, 255, 0.05);
      border-radius: 1.8rem;
      padding: 1.3rem 1.4rem;
      margin-bottom: 2rem;
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 255, 255, 0.08);
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .balance-label {
      font-size: 0.9rem;
      text-transform: uppercase;
      letter-spacing: 1px;
      color: #a5b4fc;
      font-weight: 500;
    }

    .balance-amount {
      font-size: 2.2rem;
      font-weight: 700;
      display: flex;
      align-items: baseline;
      gap: 0.2rem;
      color: white;
    }

    .balance-currency {
      font-size: 1.1rem;
      font-weight: 500;
      color: #cbd5e1;
    }

    .menu-grid {
      display: flex;
      flex-direction: column;
      gap: 0.9rem;
      margin: 1.8rem 0 2rem;
    }

    .menu-item {
      background: rgba(255, 255, 255, 0.04);
      border: 1px solid rgba(255, 255, 255, 0.06);
      border-radius: 1.5rem;
      padding: 1rem 1.3rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      transition: all 0.2s ease;
      backdrop-filter: blur(6px);
      cursor: pointer;
      box-shadow: 0 6px 14px rgba(0, 0, 0, 0.2);
    }

    .menu-item:hover {
      background: rgba(255, 255, 255, 0.08);
      border-color: rgba(251, 191, 36, 0.3);
    }

    .menu-item:active {
      transform: scale(0.98);
      background: rgba(251, 191, 36, 0.12);
      border-color: #fbbf24;
    }

    .menu-info {
      display: flex;
      align-items: center;
      gap: 1rem;
    }

    .menu-emoji {
      font-size: 2.1rem;
      width: 48px;
      height: 48px;
      background: rgba(0, 0, 0, 0.3);
      border-radius: 16px;
      display: flex;
      align-items: center;
      justify-content: center;
      backdrop-filter: blur(4px);
    }

    .menu-details {
      display: flex;
      flex-direction: column;
    }

    .menu-name {
      font-weight: 700;
      font-size: 1.2rem;
      color: #f1f5f9;
      letter-spacing: -0.2px;
    }

    .menu-price {
      font-size: 0.9rem;
      color: #94a3b8;
      font-weight: 500;
      margin-top: 0.15rem;
    }

    .buy-action {
      background: #fbbf24;
      border: none;
      color: #0f172a;
      font-weight: 700;
      font-size: 0.9rem;
      padding: 0.55rem 1.2rem;
      border-radius: 2.5rem;
      letter-spacing: 0.3px;
      cursor: pointer;
      transition: 0.2s;
      box-shadow: 0 6px 14px rgba(251, 191, 36, 0.3);
      display: flex;
      align-items: center;
      gap: 0.2rem;
      background: linear-gradient(135deg, #fcd34d, #f59e0b);
      border: 1px solid rgba(255, 255, 255, 0.2);
    }

    .buy-action:active {
      transform: scale(0.94);
      background: #f59e0b;
      box-shadow: 0 4px 10px rgba(251, 191, 36, 0.5);
    }

    .history-section {
      margin-top: 1.2rem;
      border-top: 1px solid rgba(255, 255, 255, 0.1);
      padding-top: 1.5rem;
    }

    .history-title {
      font-size: 1rem;
      font-weight: 600;
      color: #cbd5e1;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }

    .transaction-list {
      list-style: none;
      max-height: 160px;
      overflow-y: auto;
      padding-right: 0.3rem;
      display: flex;
      flex-direction: column;
      gap: 0.7rem;
    }

    .transaction-item {
      background: rgba(0, 0, 0, 0.25);
      border-radius: 1rem;
      padding: 0.7rem 1rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 0.9rem;
      border-left: 4px solid #fbbf24;
      backdrop-filter: blur(4px);
    }

    .transaction-info {
      display: flex;
      flex-direction: column;
      gap: 0.15rem;
    }

    .transaction-menu {
      font-weight: 600;
      color: #f8fafc;
    }

    .transaction-time {
      font-size: 0.7rem;
      color: #94a3b8;
    }

    .transaction-amount {
      font-weight: 700;
      color: #f87171;
    }

    .reset-area {
      display: flex;
      justify-content: flex-end;
      margin-top: 1rem;
    }

    .reset-btn {
      background: transparent;
      border: 1px solid rgba(255, 255, 255, 0.2);
      color: #cbd5e1;
      padding: 0.5rem 1.3rem;
      border-radius: 2rem;
      font-weight: 500;
      font-size: 0.8rem;
      cursor: pointer;
      transition: 0.2s;
      backdrop-filter: blur(10px);
    }

    .reset-btn:active {
      background: rgba(255, 255, 255, 0.1);
      border-color: #f87171;
      color: #fca5a5;
    }

    .empty-history {
      color: #64748b;
      font-style: italic;
      font-size: 0.85rem;
      padding: 0.5rem 0;
    }
  </style>
</head>
<body>
  <div class="app-container">
    <!-- Header dengan nama aplikasi Galan (bisa diklik) -->
    <div class="header">
      <div class="logo-section">
        <div class="logo-icon" id="logoClickable">🍜</div>
        <h1 class="app-name" id="appTitleClickable">Galan</h1>
      </div>
      <div style="color:#94a3b8; font-size:0.8rem;">💰 jajan pintar</div>
    </div>

    <!-- Kartu saldo -->
    <div class="balance-card">
      <div>
        <div class="balance-label">Saldo Kamu</div>
        <div class="balance-amount">
          <span class="balance-currency">Rp</span> <span id="balanceDisplay">50.000</span>
        </div>
      </div>
      <div style="font-size:0.8rem; color:#a5b4fc;">💸 siap jajan</div>
    </div>

    <!-- Daftar menu: nasi goreng, lemon tea, brownies, pizza -->
    <div class="menu-grid" id="menuContainer">
      <!-- Data menu di-render via JavaScript agar dinamis dan rapi -->
    </div>

    <!-- Riwayat transaksi -->
    <div class="history-section">
      <div class="history-title">
        <span>📋 Riwayat Jajan</span>
      </div>
      <ul class="transaction-list" id="historyList">
        <li class="empty-history">Belum ada transaksi hari ini</li>
      </ul>
      <div class="reset-area">
        <button class="reset-btn" id="resetButton">↺ Reset Saldo</button>
      </div>
    </div>
  </div>

  <script>
    (function() {
      // ---------- DATA MENU GALAN ----------
      const menuItems = [
        { id: 1, name: "Nasi Goreng", emoji: "🍛", price: 15000 },
        { id: 2, name: "Lemon Tea", emoji: "🍋", price: 8000 },
        { id: 3, name: "Brownies", emoji: "🍫", price: 12000 },
        { id: 4, name: "Pizza", emoji: "🍕", price: 20000 }
      ];

      // State awal
      let balance = 50000;
      const INITIAL_BALANCE = 50000;
      
      // Riwayat transaksi (array of objects)
      let transactions = [];

      // Referensi elemen DOM
      const balanceSpan = document.getElementById('balanceDisplay');
      const menuContainer = document.getElementById('menuContainer');
      const historyList = document.getElementById('historyList');
      const resetBtn = document.getElementById('resetButton');
      const logoIcon = document.getElementById('logoClickable');
      const appTitle = document.getElementById('appTitleClickable');

      // ---------- FUNGSI UTAMA ----------
      function formatRupiah(amount) {
        return amount.toLocaleString('id-ID');
      }

      function updateBalanceDisplay() {
        if (balanceSpan) {
          balanceSpan.textContent = formatRupiah(balance);
        }
      }

      // Simpan transaksi ke array dan render ulang riwayat
      function addTransaction(menuName, price) {
        const now = new Date();
        const timeString = now.toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit', second: '2-digit' });
        transactions.unshift({ menu: menuName, price, time: timeString }); // terbaru di atas
        renderTransactionHistory();
      }

      // Render riwayat transaksi
      function renderTransactionHistory() {
        if (!historyList) return;
        
        if (transactions.length === 0) {
          historyList.innerHTML = '<li class="empty-history">Belum ada transaksi hari ini</li>';
          return;
        }

        historyList.innerHTML = transactions.map(trans => {
          return `
            <li class="transaction-item">
              <div class="transaction-info">
                <span class="transaction-menu">${trans.menu}</span>
                <span class="transaction-time">${trans.time}</span>
              </div>
              <div class="transaction-amount">-Rp${formatRupiah(trans.price)}</div>
            </li>
          `;
        }).join('');
      }

      // Proses pembelian
      function handleBuy(menu) {
        if (balance >= menu.price) {
          // Kurangi saldo
          balance -= menu.price;
          updateBalanceDisplay();
          
          // Catat transaksi
          addTransaction(menu.name, menu.price);
          
          // Feedback ringan (getar kecil jika perangkat mendukung)
          if (window.navigator && window.navigator.vibrate) {
            window.navigator.vibrate(25);
          }
        } else {
          alert(`❌ Saldo tidak cukup untuk membeli ${menu.name}.\nButuh Rp${formatRupiah(menu.price)}, saldo kamu Rp${formatRupiah(balance)}.`);
        }
      }

      // Reset saldo ke nilai awal & hapus riwayat
      function resetApp() {
        balance = INITIAL_BALANCE;
        transactions = [];
        updateBalanceDisplay();
        renderTransactionHistory();
        // Opsional getaran
        if (window.navigator && window.navigator.vibrate) {
          window.navigator.vibrate(40);
        }
      }

      // Render daftar menu ke dalam grid
      function renderMenu() {
        if (!menuContainer) return;
        
        menuContainer.innerHTML = menuItems.map(menu => {
          return `
            <div class="menu-item" data-menu-id="${menu.id}">
              <div class="menu-info">
                <div class="menu-emoji">${menu.emoji}</div>
                <div class="menu-details">
                  <span class="menu-name">${menu.name}</span>
                  <span class="menu-price">Rp${formatRupiah(menu.price)}</span>
                </div>
              </div>
              <button class="buy-action" data-id="${menu.id}">
                <span>🛒</span> Beli
              </button>
            </div>
          `;
        }).join('');

        // Pasang event listener untuk setiap tombol beli dan klik pada item
        document.querySelectorAll('.buy-action').forEach(btn => {
          btn.addEventListener('click', (e) => {
            e.stopPropagation(); // hindari bubble ke parent menu-item
            const menuId = parseInt(btn.getAttribute('data-id'), 10);
            const selectedMenu = menuItems.find(m => m.id === menuId);
            if (selectedMenu) {
              handleBuy(selectedMenu);
            }
          });
        });

        // Opsional: klik pada seluruh baris menu juga bisa memicu beli (user experience)
        document.querySelectorAll('.menu-item').forEach(item => {
          item.addEventListener('click', (e) => {
            // Jangan trigger jika klik berasal dari tombol beli (sudah ditangani)
            if (e.target.closest('.buy-action')) return;
            const menuId = parseInt(item.getAttribute('data-menu-id'), 10);
            const selectedMenu = menuItems.find(m => m.id === menuId);
            if (selectedMenu) {
              handleBuy(selectedMenu);
            }
          });
        });
      }

      // Event untuk elemen yang bisa diklik (nama Galan & logo)
      function setupClickableBrand() {
        const clickHandler = () => {
          alert("🍜 Galan - Catatan Keuangan Jajan\nNasi Goreng, Lemon Tea, Brownies, Pizza.\nKelola jajanmu dengan bijak!");
        };

        if (logoIcon) {
          logoIcon.addEventListener('click', clickHandler);
          // Aksesibilitas keyboard
          logoIcon.setAttribute('role', 'button');
          logoIcon.setAttribute('tabindex', '0');
          logoIcon.addEventListener('keydown', (e) => {
            if (e.key === 'Enter' || e.key === ' ') {
              e.preventDefault();
              clickHandler();
            }
          });
        }

        if (appTitle) {
          appTitle.addEventListener('click', clickHandler);
          appTitle.setAttribute('role', 'button');
          appTitle.setAttribute('tabindex', '0');
          appTitle.addEventListener('keydown', (e) => {
            if (e.key === 'Enter' || e.key === ' ') {
              e.preventDefault();
              clickHandler();
            }
          });
        }
      }

      // Pasang event listener untuk tombol reset
      if (resetBtn) {
        resetBtn.addEventListener('click', resetApp);
      }

      // Inisialisasi semua tampilan
      function initApp() {
        updateBalanceDisplay();
        renderMenu();
        renderTransactionHistory();
        setupClickableBrand();
      }

      // Jalankan setelah DOM siap
      window.addEventListener('DOMContentLoaded', initApp);
    })();
  </script>
</body>
</html>
