<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>قراصنة الدراسة - نظام الجدولة</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700&display=swap');
        
        :root {
            --straw-hat: #FF6B00;
            --navy-blue: #00308F;
            --gold: #FFD700;
            --red: #FF0000;
            --sea: #00B4D8;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Cairo', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
            min-height: 100vh;
            color: white;
        }
        
        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            text-align: center;
            padding: 40px 0;
            background: rgba(0, 48, 143, 0.8);
            border-radius: 20px;
            margin-bottom: 30px;
            border: 3px solid var(--gold);
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: "🏴‍☠️";
            font-size: 80px;
            position: absolute;
            top: 10px;
            left: 20px;
            opacity: 0.3;
        }
        
        header::after {
            content: "⚓";
            font-size: 80px;
            position: absolute;
            top: 10px;
            right: 20px;
            opacity: 0.3;
        }
        
        h1 {
            font-size: 3em;
            color: var(--gold);
            text-shadow: 3px 3px 0 var(--red);
            margin-bottom: 10px;
        }
        
        .subtitle {
            font-size: 1.5em;
            color: white;
            margin-bottom: 20px;
        }
        
        .main-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .upload-section, .schedule-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 30px;
            border-radius: 15px;
            border: 2px solid var(--straw-hat);
        }
        
        .upload-area {
            border: 3px dashed var(--sea);
            border-radius: 10px;
            padding: 40px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-bottom: 20px;
        }
        
        .upload-area:hover {
            background: rgba(0, 180, 216, 0.2);
            transform: scale(1.02);
        }
        
        .upload-icon {
            font-size: 60px;
            margin-bottom: 15px;
        }
        
        .file-list {
            margin-top: 20px;
        }
        
        .file-item {
            background: rgba(255, 107, 0, 0.2);
            padding: 10px;
            margin: 5px 0;
            border-radius: 5px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .file-size {
            color: var(--gold);
            font-size: 0.9em;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            color: var(--gold);
            font-weight: bold;
        }
        
        input, select, button {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
        }
        
        input, select {
            background: rgba(255, 255, 255, 0.9);
        }
        
        button {
            background: linear-gradient(45deg, var(--straw-hat), var(--red));
            color: white;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid var(--gold);
        }
        
        button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(255, 107, 0, 0.4);
        }
        
        .schedule-display {
            margin-top: 20px;
            max-height: 400px;
            overflow-y: auto;
        }
        
        .day-schedule {
            background: rgba(0, 48, 143, 0.6);
            margin: 10px 0;
            padding: 15px;
            border-radius: 8px;
            border-left: 4px solid var(--straw-hat);
        }
        
        .day-header {
            color: var(--gold);
            font-weight: bold;
            margin-bottom: 8px;
            display: flex;
            justify-content: space-between;
        }
        
        .study-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 8px;
            margin: 5px 0;
            border-radius: 5px;
            display: flex;
            justify-content: space-between;
        }
        
        .pirate-theme {
            text-align: center;
            margin: 20px 0;
        }
        
        .theme-text {
            font-size: 1.2em;
            color: var(--gold);
            font-style: italic;
        }
        
        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
            
            h1 {
                font-size: 2em;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>قراصنة الدراسة 🏴‍☠️</h1>
            <div class="subtitle">اكتشف كنز المعرفة مع طاقم قبعات القش!</div>
        </header>
        
        <div class="pirate-theme">
            <div class="theme-text">"الرجل الذي لا يدرس شيئاً لا يختلف عن الرجل الذي لا يستطيع القراءة!" - المارد</div>
        </div>
        
        <div class="main-content">
            <div class="upload-section">
                <h2>⏫ رفع ملفات الدراسة</h2>
                <div class="upload-area" id="uploadArea">
                    <div class="upload-icon">📚</div>
                    <div>انقر أو اسحب الملفات هنا</div>
                    <div style="font-size: 0.9em; margin-top: 10px; opacity: 0.8;">
                        يدعم: PDF, Word, PowerPoint, الصور
                    </div>
                </div>
                
                <div class="file-list" id="fileList">
                    <!-- الملفات المرفوعة تظهر هنا -->
                </div>
                
                <div class="form-group">
                    <label for="studyDays">🎯 عدد أيام الدراسة:</label>
                    <input type="number" id="studyDays" min="1" max="365" value="7">
                </div>
                
                <div class="form-group">
                    <label for="dailyHours">⏰ ساعات الدراسة اليومية:</label>
                    <select id="dailyHours">
                        <option value="1">1 ساعة</option>
                        <option value="2">2 ساعات</option>
                        <option value="3" selected>3 ساعات</option>
                        <option value="4">4 ساعات</option>
                        <option value="5">5 ساعات</option>
                        <option value="6">6 ساعات</option>
                    </select>
                </div>
                
                <button onclick="generateSchedule()">⚡ إنشاء جدول الدراسة!</button>
            </div>
            
            <div class="schedule-section">
                <h2>📅 جدول الدراسة</h2>
                <div class="schedule-display" id="scheduleDisplay">
                    <div style="text-align: center; padding: 40px; opacity: 0.7;">
                        سيظهر جدول الدراسة هنا بعد رفع الملفات
                    </div>
                </div>
                
                <button onclick="downloadSchedule()" style="margin-top: 15px; background: linear-gradient(45deg, var(--navy-blue), var(--sea));">
                    💾 تحميل الجدول
                </button>
            </div>
        </div>
    </div>

    <script>
        let uploadedFiles = [];
        
        // نظام رفع الملفات
        const uploadArea = document.getElementById('uploadArea');
        const fileList = document.getElementById('fileList');
        
        uploadArea.addEventListener('click', () => {
            const input = document.createElement('input');
            input.type = 'file';
            input.multiple = true;
            input.accept = '.pdf,.doc,.docx,.ppt,.pptx,.jpg,.jpeg,.png,.txt';
            input.onchange = handleFileSelect;
            input.click();
        });
        
        uploadArea.addEventListener('dragover', (e) => {
            e.preventDefault();
            uploadArea.style.background = 'rgba(0, 180, 216, 0.3)';
        });
        
        uploadArea.addEventListener('dragleave', () => {
            uploadArea.style.background = '';
        });
        
        uploadArea.addEventListener('drop', (e) => {
            e.preventDefault();
            uploadArea.style.background = '';
            handleFiles(e.dataTransfer.files);
        });
        
        function handleFileSelect(e) {
            handleFiles(e.target.files);
        }
        
        function handleFiles(files) {
            for (let file of files) {
                uploadedFiles.push({
                    name: file.name,
                    size: file.size,
                    type: file.type
                });
            }
            updateFileList();
        }
        
        function updateFileList() {
            fileList.innerHTML = '';
            uploadedFiles.forEach((file, index) => {
                const fileItem = document.createElement('div');
                fileItem.className = 'file-item';
                fileItem.innerHTML = `
                    <span>${file.name}</span>
                    <span class="file-size">${formatFileSize(file.size)}</span>
                `;
                fileList.appendChild(fileItem);
            });
        }
        
        function formatFileSize(bytes) {
            if (bytes === 0) return '0 Bytes';
            const k = 1024;
            const sizes = ['Bytes', 'KB', 'MB', 'GB'];
            const i = Math.floor(Math.log(bytes) / Math.log(k));
            return parseFloat((bytes / Math.pow(k, i)).toFixed(2)) + ' ' + sizes[i];
        }
        
        // نظام إنشاء الجدول
        function generateSchedule() {
            if (uploadedFiles.length === 0) {
                alert('🏴‍☠️ يا رفيق! تحتاج لرفع بعض ملفات الدراسة أولاً!');
                return;
            }
            
            const studyDays = parseInt(document.getElementById('studyDays').value);
            const dailyHours = parseInt(document.getElementById('dailyHours').value);
            
            const scheduleDisplay = document.getElementById('scheduleDisplay');
            scheduleDisplay.innerHTML = '';
            
            // خوارزمية ذكية لتوزيع الملفات
            const filesPerDay = Math.ceil(uploadedFiles.length / studyDays);
            const studyMinutes = dailyHours * 60;
            const minutesPerFile = Math.floor(studyMinutes / filesPerDay);
            
            for (let day = 1; day <= studyDays; day++) {
                const daySchedule = document.createElement('div');
                daySchedule.className = 'day-schedule';
                
                const dayHeader = document.createElement('div');
                dayHeader.className = 'day-header';
                dayHeader.innerHTML = `اليوم ${day} <span>${dailyHours} ساعات</span>`;
                daySchedule.appendChild(dayHeader);
                
                const startIndex = (day - 1) * filesPerDay;
                const endIndex = Math.min(startIndex + filesPerDay, uploadedFiles.length);
                
                for (let i = startIndex; i < endIndex; i++) {
                    if (i >= uploadedFiles.length) break;
                    
                    const studyItem = document.createElement('div');
                    studyItem.className = 'study-item';
                    
                    const estimatedTime = Math.max(30, Math.min(120, minutesPerFile));
                    const startTime = calculateStartTime((i - startIndex) * estimatedTime);
                    
                    studyItem.innerHTML = `
                        <span>${uploadedFiles[i].name}</span>
                        <span>${startTime} - ${estimatedTime} دقيقة</span>
                    `;
                    daySchedule.appendChild(studyItem);
                }
                
                // إضافة استراحة
                if (endIndex - startIndex > 0) {
                    const breakItem = document.createElement('div');
                    breakItem.className = 'study-item';
                    breakItem.style.background = 'rgba(255, 215, 0, 0.3)';
                    breakItem.innerHTML = `
                        <span>☕ استراحة شاي</span>
                        <span>15 دقيقة</span>
                    `;
                    daySchedule.appendChild(breakItem);
                }
                
                scheduleDisplay.appendChild(daySchedule);
            }
        }
        
        function calculateStartTime(minutesOffset) {
            const startHour = 9; // بداية الدراسة 9 صباحاً
            const totalMinutes = startHour * 60 + minutesOffset;
            const hours = Math.floor(totalMinutes / 60);
            const minutes = totalMinutes % 60;
            return `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}`;
        }
        
        function downloadSchedule() {
            if (!document.querySelector('.day-schedule')) {
                alert('🏴‍☠️ تحتاج لإنشاء جدول أولاً يا رفيق!');
                return;
            }
            
            const scheduleData = {
                files: uploadedFiles,
                schedule: document.getElementById('scheduleDisplay').innerHTML,
                generatedAt: new Date().toLocaleString()
            };
            
            const blob = new Blob([JSON.stringify(scheduleData, null, 2)], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = 'جدول_الدراسة_قراصنة.json';
            a.click();
            URL.revokeObjectURL(url);
            
            alert('✅ تم تحميل جدول الدراسة! إلى الأمام نحو الكنز! 🏴‍☠️');
        }
    </script>
</body>
</html>
