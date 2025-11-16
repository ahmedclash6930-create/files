# files
<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>المكتبة الدراسية - أحمد حاتم أسعد</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px;
            direction: rtl;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.1);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #2c3e50, #34495e);
            color: white;
            padding: 40px;
            text-align: center;
            position: relative;
        }

        .creator-signature {
            background: linear-gradient(135deg, #e74c3c, #c0392b);
            color: white;
            padding: 15px 30px;
            border-radius: 50px;
            display: inline-block;
            font-size: 1.3em;
            font-weight: bold;
            margin-bottom: 20px;
            box-shadow: 0 5px 15px rgba(231, 76, 60, 0.3);
        }

        .header h1 {
            font-size: 2.8em;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #3498db, #2ecc71);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .header p {
            font-size: 1.3em;
            opacity: 0.9;
            margin-bottom: 10px;
        }

        .subtitle {
            color: #bdc3c7;
            font-size: 1.1em;
        }

        .folders-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            padding: 50px;
        }

        .folder {
            background: #f8f9fa;
            border-radius: 20px;
            padding: 35px;
            text-align: center;
            transition: all 0.3s ease;
            border: 4px solid;
            cursor: pointer;
            text-decoration: none;
            color: inherit;
            display: block;
            position: relative;
            overflow: hidden;
        }

        .folder::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: currentColor;
            opacity: 0.3;
        }

        .folder:hover {
            transform: translateY(-8px) scale(1.02);
            box-shadow: 0 15px 35px rgba(0,0,0,0.15);
        }

        .folder-number {
            position: absolute;
            top: 15px;
            left: 15px;
            background: currentColor;
            color: white;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.1em;
        }

        .folder-icon {
            font-size: 3.5em;
            margin-bottom: 20px;
            margin-top: 10px;
        }

        .folder h3 {
            color: #2c3e50;
            margin-bottom: 15px;
            font-size: 1.6em;
            font-weight: bold;
        }

        .folder p {
            color: #7f8c8d;
            font-size: 1em;
            margin-bottom: 20px;
        }

        .files-list {
            background: white;
            border-radius: 12px;
            padding: 20px;
            margin-top: 15px;
            border: 2px dashed #bdc3c7;
        }

        .file-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 12px 15px;
            margin: 8px 0;
            background: #ecf0f1;
            border-radius: 8px;
            transition: all 0.2s ease;
        }

        .file-item:hover {
            background: #d5dbdb;
            transform: translateX(-5px);
        }

        .file-name {
            font-weight: bold;
            color: #2c3e50;
        }

        .file-type {
            background: #3498db;
            color: white;
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 0.8em;
        }

        /* ألوان مختلفة لكل مادة */
        .folder-1 { border-color: #e74c3c; color: #e74c3c; }
        .folder-2 { border-color: #27ae60; color: #27ae60; }
        .folder-3 { border-color: #3498db; color: #3498db; }
        .folder-4 { border-color: #9b59b6; color: #9b59b6; }
        .folder-5 { border-color: #e67e22; color: #e67e22; }
        .folder-6 { border-color: #1abc9c; color: #1abc9c; }
        .folder-7 { border-color: #f39c12; color: #f39c12; }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            padding: 30px 50px;
            background: #34495e;
            color: white;
        }

        .stat-item {
            text-align: center;
            padding: 20px;
            background: rgba(255,255,255,0.1);
            border-radius: 15px;
            backdrop-filter: blur(10px);
        }

        .stat-number {
            font-size: 2.5em;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .stat-label {
            font-size: 1em;
            opacity: 0.9;
        }

        .footer {
            background: #2c3e50;
            color: #bdc3c7;
            text-align: center;
            padding: 30px;
            font-size: 1.1em;
        }

        @media (max-width: 768px) {
            .folders-grid {
                grid-template-columns: 1fr;
                padding: 20px;
            }
            
            .header h1 {
                font-size: 2em;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="creator-signature">
                📚 صنع بواسطة أحمد حاتم أسعد
            </div>
            <h1>المكتبة الدراسية الشاملة</h1>
            <p>تنظيم المواد الدراسية ومذكرات الطالب</p>
            <div class="subtitle">كل ما تحتاجه للدراسة في مكان واحد</div>
        </div>

        <div class="folders-grid">
            <!-- مادة الحيوان -->
            <a href="1-حيوان/" class="folder folder-1">
                <div class="folder-number">1</div>
                <div class="folder-icon">🐾</div>
                <h3>علم الحيوان</h3>
                <p>دراسة الكائنات الحيوانية وتصنيفها</p>
                <div class="files-list">
                    <div class="file-item">
                        <span class="file-name">البيانات الرئيسية</span>
                        <span class="file-type">MD</span>
                    </div>
                    <div class="file-item">
                        <span class="file-name">ملاحظات السكاشن</span>
                        <span class="file-type">MD</span>
                    </div>
                </div>
            </a>

            <!-- مادة النبات -->
            <a href="2-نبات/" class="folder folder-2">
                <div class="folder-number">2</div>
                <div class="folder-icon">🌿</div>
                <h3>علم النبات</h3>
                <p>دراسة الحياة النباتية والتركيب الضوئي</p>
                <div class="files-list">
                    <div class="file-item">
                        <span class="file-name">البيانات الرئيسية</span>
                        <span class="file-type">MD</span>
                    </div>
                    <div class="file-item">
                        <span class="file-name">ملاحظات السكاشن</span>
                        <span class="file-type">MD</span>
                    </div>
                </div>
            </a>

            <!-- مادة الفيزياء -->
            <a href="3-فيزياء/" class="folder folder-3">
                <div class="folder-number">3</div>
                <div class="folder-icon">⚡</div>
                <h3>الفيزياء</h3>
                <p>قوانين الحركة والطاقة والمادة</p>
                <div class="files-list">
                    <div class="file-item">
                        <span class="file-name">البيانات الرئيسية</span>
                        <span class="file-type">MD</span>
                    </div>
                    <div class="file-item">
                        <span class="file-name">ملاحظات السكاشن</span>
                        <span class="file-type">MD</span>
                    </div>
                </div>
            </a>

            <!-- مادة الكيمياء -->
            <a href="4-كيمياء/" class="folder folder-4">
                <div class="folder-number">4</div>
                <div class="folder-icon">🧪</div>
                <h3>الكيمياء</h3>
                <p>تفاعلات العناصر والمركبات الكيميائية</p>
                <div class="files-list">
                    <div class="file-item">
                        <span class="file-name">البيانات الرئيسية</span>
                        <span class="file-type">MD</span>
                    </div>
                    <div class="file-item">
                        <span class="file-name">ملاحظات السكاشن</span>
                        <span class="file-type">MD</span>
                    </div>
                </div>
            </a>

            <!-- مادة الرياضيات -->
            <a href="5-رياضيات/" class="folder folder-5">
                <div class="folder-number">5</div>
                <div class="folder-icon">📐</div>
                <h3>الرياضيات</h3>
                <p>الجبر، الهندسة، التفاضل والتكامل</p>
                <div class="files-list">
                    <div class="file-item">
                        <span class="file-name">البيانات الرئيسية</span>
                        <span class="file-type">MD</span>
                    </div>
                    <div class="file-item">
                        <span class="file-name">ملاحظات السكاشن</span>
                        <span class="file-type">MD</span>
                    </div>
                </div>
            </a>

            <!-- مادة تكنولوجيا المعلومات -->
            <a href="6-تكنولوجيا-المعلومات/" class="folder folder-6">
                <div class="folder-number">6</div>
                <div class="folder-icon">💻</div>
                <h3>تكنولوجيا المعلومات</h3>
                <p>البرمجة، الشبكات، قواعد البيانات</p>
                <div class="files-list">
                    <div class="file-item">
                        <span class="file-name">البيانات الرئيسية</span>
                        <span class="file-type">MD</span>
                    </div>
                    <div class="file-item">
                        <span class="file-name">ملاحظات السكاشن</span>
                        <span class="file-type">MD</span>
                    </div>
                </div>
            </a>

            <!-- متطلب جامعة -->
            <a href="7-متطلب-جامعة/" class="folder folder-7">
                <div class="folder-number">7</div>
                <div class="folder-icon">🎓</div>
                <h3>متطلب جامعة</h3>
                <p>متطلبات الجامعة العامة واللغة</p>
                <div class="files-list">
                    <div class="file-item">
                        <span class="file-name">البيانات الرئيسية</span>
                        <span class="file-type">MD</span>
                    </div>
                    <div class="file-item">
                        <span class="file-name">ملاحظات السكاشن</span>
                        <span class="file-type">MD</span>
                    </div>
                </div>
            </a>
        </div>

        <div class="stats">
            <div class="stat-item">
                <div class="stat-number">7</div>
                <div class="stat-label">مواد دراسية</div>
            </div>
            <div class="stat-item">
                <div class="stat-number">14</div>
                <div class="stat-label">ملف منظم</div>
            </div>
            <div class="stat-item">
                <div class="stat-number">2</div>
                <div class="stat-label">ملف لكل مادة</div>
            </div>
            <div class="stat-item">
                <div class="stat-number">100%</div>
                <div class="stat-label">جاهز للاستخدام</div>
            </div>
        </div>

        <div class="footer">
            <p>📖 مكتبة الطالب المميز - صنع بكل فخر بواسطة أحمد حاتم أسعد</p>
            <p>© 2024 جميع الحقوق محفوظة</p>
        </div>
    </div>

    <script>
        // إضافة تأثيرات تفاعلية
        document.addEventListener('DOMContentLoaded', function() {
            const folders = document.querySelectorAll('.folder');
            
            folders.forEach(folder => {
                folder.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-8px) scale(1.02)';
                });
                
                folder.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0) scale(1)';
                });
            });
        });
    </script>
</body>
</html>
