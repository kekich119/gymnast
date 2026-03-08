<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mobile App</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .mobile-container {
            width: 100%;
            max-width: 375px;
            height: 812px;
            background: #f5f5f5;
            border-radius: 40px;
            overflow: hidden;
            position: relative;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }

        /* Header */
        .header {
            background: #fff;
            padding: 50px 20px 15px;
            text-align: center;
            border-bottom: 2px solid #e0e0e0;
        }

        .header-title {
            font-size: 24px;
            font-weight: bold;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: inline-block;
            padding: 10px 30px;
            border: 3px solid #667eea;
            border-radius: 15px;
        }

        /* Main Content */
        .content {
            padding: 20px;
            padding-bottom: 100px;
        }

        /* User Info Card */
        .user-card {
            background: #fff;
            border-radius: 20px;
            padding: 25px;
            margin-bottom: 15px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }

        .user-id {
            font-size: 28px;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 10px;
            letter-spacing: 2px;
        }

        .user-name {
            font-size: 18px;
            color: #333;
            margin-bottom: 8px;
            font-weight: 600;
        }

        .user-name-label {
            color: #999;
            font-size: 14px;
            margin-bottom: 15px;
        }

        .days-left {
            font-size: 16px;
            color: #666;
            background: #f8f9fa;
            padding: 10px 15px;
            border-radius: 10px;
            display: inline-block;
        }

        .days-left strong {
            color: #667eea;
            font-size: 20px;
        }

        /* Extend Button */
        .extend-btn {
            width: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            border: none;
            padding: 18px;
            border-radius: 15px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            margin-bottom: 25px;
            transition: transform 0.2s, box-shadow 0.2s;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
        }

        .extend-btn:active {
            transform: scale(0.98);
            box-shadow: 0 2px 10px rgba(102, 126, 234, 0.4);
        }

        /* Warnings Circle */
        .warnings-section {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-top: 30px;
        }

        .warnings-circle {
            width: 250px;
            height: 250px;
            border-radius: 50%;
            background: linear-gradient(135deg, #fff 0%, #f8f9fa 100%);
            border: 4px solid #667eea;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 20px;
            box-shadow: 0 8px 30px rgba(102, 126, 234, 0.3);
            position: relative;
        }

        .warnings-circle::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 2px dashed #667eea;
            opacity: 0.3;
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .warnings-text {
            font-size: 22px;
            font-weight: 600;
            color: #333;
            z-index: 1;
        }

        .warnings-count {
            font-size: 48px;
            font-weight: bold;
            color: #667eea;
            margin-top: 10px;
            z-index: 1;
        }

        /* Bottom Navigation */
        .bottom-nav {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: #fff;
            border-top: 2px solid #e0e0e0;
            display: flex;
            justify-content: space-around;
            padding: 15px 10px 30px;
        }

        .nav-item {
            flex: 1;
            text-align: center;
            padding: 10px;
            cursor: pointer;
            transition: all 0.3s;
            border-radius: 12px;
            margin: 0 5px;
        }

        .nav-item:hover {
            background: #f8f9fa;
        }

        .nav-item.active {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
        }

        .nav-item.active .nav-icon {
            color: #fff;
        }

        .nav-icon {
            font-size: 24px;
            margin-bottom: 5px;
            color: #667eea;
        }

        .nav-label {
            font-size: 14px;
            font-weight: 600;
            color: #666;
        }

        .nav-item.active .nav-label {
            color: #fff;
        }

        /* Responsive */
        @media (max-width: 480px) {
            .mobile-container {
                max-width: 100%;
                height: 100vh;
                border-radius: 0;
            }
        }
    </style>
</head>
<body>
    <div class="mobile-container">
        <!-- Header -->
        <div class="header">
            <div class="header-title">MAIN</div>
        </div>

        <!-- Main Content -->
        <div class="content">
            <!-- User Info Card -->
            <div class="user-card">
                <div class="user-id">12345678</div>
                <div class="user-name-label">ФИО</div>
                <div class="user-name">Иванов Иван Иванович</div>
                <div class="days-left">Дней осталось: <strong>15</strong></div>
            </div>

            <!-- Extend Button -->
            <button class="extend-btn">Продлить</button>

            <!-- Warnings Section -->
            <div class="warnings-section">
                <div class="warnings-circle">
                    <div class="warnings-text">Предупреждения</div>
                    <div class="warnings-count">3</div>
                </div>
            </div>
        </div>

        <!-- Bottom Navigation -->
        <div class="bottom-nav">
            <div class="nav-item">
                <div class="nav-icon">🛒</div>
                <div class="nav-label">shop</div>
            </div>
            <div class="nav-item active">
                <div class="nav-icon">🏠</div>
                <div class="nav-label">Main</div>
            </div>
            <div class="nav-item">
                <div class="nav-icon">👤</div>
                <div class="nav-label">Profile</div>
            </div>
        </div>
    </div>

    <script>
        // Simple interactivity
        document.querySelector('.extend-btn').addEventListener('click', function() {
            alert('Подписка продлена!');
        });

        document.querySelectorAll('.nav-item').forEach(item => {
            item.addEventListener('click', function() {
                document.querySelectorAll('.nav-item').forEach(i => i.classList.remove('active'));
                this.classList.add('active');
            });
        });
    </script>
</body>
</html>
