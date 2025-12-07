<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>سجل متابعة الطلاب - اللغة الإنجليزية</title>
<style>
:root {
    --primary-color: #00b4d8;
    --secondary-color: #0077b6;
    --accent-color: #48cae4;
    --success-color: #4ade80;
    --warning-color: #f59e0b;
    --danger-color: #e63946;
    --light-color: #f8fafc;
    --dark-color: #1e293b;
    --gray-color: #64748b;
    --border-radius: 12px;
    --shadow: 0 10px 25px rgba(0, 0, 0, 0.05);
    --transition: all 0.3s ease;
}

body {
    font-family: "Tajawal", "Segoe UI", system-ui, sans-serif;
    margin: 0;
    padding: 0;
    background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
    color: var(--dark-color);
    line-height: 1.6;
}

header {
    background: linear-gradient(135deg, #00b4d8, #0077b6);
    color: white;
    padding: 20px 0;
    box-shadow: 0 8px 20px rgba(0, 180, 216, 0.15);
    position: relative;
    overflow: hidden;
}

.header-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 15px;
    padding: 0 20px;
}

.school-name {
    font-size: 32px;
    font-weight: 800;
    text-align: center;
    letter-spacing: -0.5px;
    margin: 0;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
    color: white;
}

.teacher-input-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    margin: 10px 0;
}

.teacher-input-row {
    display: flex;
    align-items: center;
    gap: 15px;
    flex-wrap: wrap;
    justify-content: center;
}

.teacher-input-label {
    font-size: 16px;
    font-weight: 600;
    color: rgba(255, 255, 255, 0.9);
}

.teacher-input {
    padding: 12px 20px;
    border: 2px solid rgba(255, 255, 255, 0.3);
    border-radius: 8px;
    background: rgba(255, 255, 255, 0.15);
    color: white;
    font-family: "Tajawal", sans-serif;
    font-size: 16px;
    font-weight: 500;
    width: 250px;
    text-align: center;
    backdrop-filter: blur(10px);
    transition: var(--transition);
}

.teacher-input::placeholder {
    color: rgba(255, 255, 255, 0.7);
}

.teacher-input:focus {
    outline: none;
    border-color: white;
    background: rgba(255, 255, 255, 0.25);
    box-shadow: 0 0 0 3px rgba(255, 255, 255, 0.2);
}

.teacher-save-btn {
    padding: 12px 25px;
    border: none;
    border-radius: 8px;
    background: rgba(255, 255, 255, 0.2);
    color: white;
    font-family: "Tajawal", sans-serif;
    font-size: 14px;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.3);
}

.teacher-save-btn:hover {
    background: rgba(255, 255, 255, 0.3);
    transform: translateY(-2px);
}

.teacher-display {
    font-size: 18px;
    font-weight: 600;
    text-align: center;
    margin-top: 5px;
    padding: 8px 20px;
    background: rgba(255, 255, 255, 0.15);
    border-radius: 8px;
    border: 1px solid rgba(255, 255, 255, 0.2);
}

.container {
    width: 95%;
    max-width: 1400px;
    margin: 25px auto;
    padding: 25px;
    background: white;
    border-radius: var(--border-radius);
    box-shadow: var(--shadow);
    position: relative;
}

/* تصميم الأزرار */
button {
    margin: 5px;
    padding: 12px 24px;
    border: none;
    border-radius: 8px;
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: white;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition);
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    font-family: "Tajawal", sans-serif;
    font-size: 14px;
    box-shadow: 0 4px 12px rgba(0, 180, 216, 0.2);
}

button:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 20px rgba(0, 180, 216, 0.3);
}

button:active {
    transform: translateY(-1px);
}

.controls {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin-bottom: 25px;
    gap: 10px;
    background: var(--light-color);
    padding: 20px;
    border-radius: var(--border-radius);
}

/* تصميم علامات التبويب للصفوف */
.class-tabs {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 25px;
    gap: 10px;
}

.class-tab {
    padding: 12px 24px;
    background: white;
    border-radius: 8px;
    cursor: pointer;
    transition: var(--transition);
    font-weight: 600;
    border: 2px solid #e2e8f0;
    color: var(--gray-color);
    box-shadow: 0 2px 5px rgba(0,0,0,0.05);
}

.class-tab.active {
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: white;
    border-color: var(--primary-color);
    box-shadow: 0 5px 15px rgba(0, 180, 216, 0.2);
}

.class-tab:hover {
    transform: translateY(-2px);
    border-color: var(--accent-color);
}

/* تصميم الجداول */
table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    font-size: 14px;
    margin-bottom: 25px;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 5px 15px rgba(0,0,0,0.05);
}

th, td {
    border: 1px solid #e2e8f0;
    padding: 14px 10px;
    text-align: center;
    transition: var(--transition);
}

th {
    background: linear-gradient(135deg, #f1f5f9, #e2e8f0);
    color: var(--dark-color);
    font-size: 13px;
    font-weight: 700;
    border-bottom: 2px solid var(--primary-color);
}

td {
    cursor: pointer;
    user-select: none;
    position: relative;
}

tr:hover td {
    background-color: #f8fafc;
}

.class-header {
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: white;
    padding: 15px;
    margin: 25px 0 15px 0;
    border-radius: var(--border-radius);
    text-align: center;
    font-size: 18px;
    font-weight: 700;
    box-shadow: 0 5px 15px rgba(0, 180, 216, 0.15);
}

/* حالة الحضور */
.present {
    background-color: rgba(74, 222, 128, 0.15);
    color: #059669;
    font-weight: 600;
}

.absent {
    background-color: rgba(230, 57, 70, 0.15);
    color: #e63946;
    font-weight: 600;
}

.error-cell {
    background-color: rgba(230, 57, 70, 0.2) !important;
    color: #e63946 !important;
    font-weight: bold;
}

.star-cell {
    color: var(--warning-color);
    font-size: 20px;
    cursor: pointer;
    transition: var(--transition);
}

.star-cell:hover {
    transform: scale(1.2);
}

.starred-student {
    background-color: rgba(245, 158, 11, 0.08) !important;
    border-left: 4px solid var(--warning-color);
}

/* لوحة الإدارة */
.admin-panel {
    display: none;
    margin-top: 25px;
    padding: 25px;
    border: 1px solid #e2e8f0;
    border-radius: var(--border-radius);
    background: linear-gradient(135deg, #f8fafc, #f1f5f9);
}

.admin-section {
    margin: 25px 0;
    padding: 20px;
    background: white;
    border-radius: var(--border-radius);
    border: 1px solid #e2e8f0;
    box-shadow: 0 5px 15px rgba(0,0,0,0.03);
}

.admin-section h4 {
    margin-top: 0;
    color: var(--primary-color);
    text-align: center;
    padding-bottom: 15px;
    border-bottom: 2px solid #e2e8f0;
    font-size: 18px;
}

/* تصميم مربعات اختيار الأسابيع */
.weeks-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 12px;
    margin: 20px 0;
}

.week-checkbox-item {
    display: flex;
    align-items: center;
    padding: 15px;
    background: white;
    border-radius: 10px;
    border: 2px solid #e2e8f0;
    transition: var(--transition);
    cursor: pointer;
}

.week-checkbox-item:hover {
    border-color: var(--accent-color);
    transform: translateY(-3px);
    box-shadow: 0 8px 15px rgba(0,0,0,0.05);
}

.week-checkbox-item input[type="checkbox"] {
    margin-left: 12px;
    transform: scale(1.3);
    cursor: pointer;
    accent-color: var(--primary-color);
}

.week-checkbox-label {
    flex: 1;
    display: flex;
    flex-direction: column;
    cursor: pointer;
}

.week-number {
    font-size: 15px;
    font-weight: 700;
    color: var(--dark-color);
}

.week-dates {
    font-size: 13px;
    color: var(--gray-color);
    margin-top: 4px;
}

.week-days {
    font-size: 12px;
    color: var(--gray-color);
    margin-top: 2px;
}

/* تصميم إدارة الطلاب */
.management-form {
    display: flex;
    flex-direction: column;
    gap: 15px;
    margin: 20px 0;
    padding: 20px;
    background: white;
    border-radius: var(--border-radius);
    border: 1px solid #e2e8f0;
}

.management-form input,
.management-form select {
    padding: 12px 15px;
    border: 2px solid #e2e8f0;
    border-radius: 8px;
    font-family: "Tajawal", sans-serif;
    font-size: 14px;
    transition: var(--transition);
}

.management-form input:focus,
.management-form select:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 0 3px rgba(0, 180, 216, 0.1);
}

/* تصميم العداد */
.student-count {
    text-align: center;
    margin: 25px 0;
    padding: 15px;
    background: linear-gradient(135deg, #f8fafc, #f1f5f9);
    border-radius: var(--border-radius);
    color: var(--dark-color);
    font-weight: 700;
    font-size: 16px;
    border: 1px solid #e2e8f0;
}

/* تصميم الفلاتر */
.status-filter {
    margin: 20px 0;
    text-align: center;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 10px;
}

.status-filter button {
    background: #e2e8f0;
    color: var(--gray-color);
    box-shadow: none;
}

.status-filter button.active {
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: white;
}

/* تصميم قسم التصدير */
.export-section {
    background: linear-gradient(135deg, #fef3c7, #fde68a);
    border: 1px solid #f59e0b;
    border-radius: var(--border-radius);
    padding: 25px;
    margin-top: 25px;
}

/* تصميم القسم الدفعي الجديد */
.batch-selection {
    background: white;
    border-radius: var(--border-radius);
    padding: 20px;
    margin: 20px 0;
    border: 1px solid #e2e8f0;
}

.week-buttons-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
    gap: 10px;
    margin-top: 15px;
}

.week-button {
    padding: 10px 15px;
    background: linear-gradient(135deg, #48cae4, #0096c7);
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    font-family: "Tajawal", sans-serif;
    font-size: 13px;
    font-weight: 600;
    transition: var(--transition);
    text-align: center;
}

.week-button:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 10px rgba(0, 150, 199, 0.2);
}

.week-button.selected {
    background: linear-gradient(135deg, #f59e0b, #d97706);
    box-shadow: 0 0 0 2px rgba(245, 158, 11, 0.3);
}

/* تصميم مؤشر التحميل */
.loading-spinner {
    display: none;
    text-align: center;
    padding: 30px;
    background: white;
    border-radius: var(--border-radius);
    margin: 20px 0;
}

.spinner {
    border: 4px solid #f3f3f3;
    border-top: 4px solid var(--primary-color);
    border-radius: 50%;
    width: 50px;
    height: 50px;
    animation: spin 1s linear infinite;
    margin: 0 auto 15px;
}

@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

/* تصميم حقل كلمة المرور */
input[type="password"] {
    padding: 14px 20px;
    border: 2px solid #e2e8f0;
    border-radius: 8px;
    font-family: "Tajawal", sans-serif;
    font-size: 15px;
    width: 250px;
    text-align: center;
    transition: var(--transition);
}

input[type="password"]:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 0 3px rgba(0, 180, 216, 0.1);
}

/* أنماط إضافية للدفعات */
.selection-mode-btn {
    background: #e2e8f0;
    color: var(--gray-color);
    border: none;
    border-radius: 8px;
    cursor: pointer;
    font-family: "Tajawal", sans-serif;
    font-weight: 600;
    transition: all 0.3s ease;
}

.selection-mode-btn.active {
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: white;
    box-shadow: 0 4px 12px rgba(0, 180, 216, 0.2);
}

.batch-preset-btn {
    padding: 12px 20px;
    background: linear-gradient(135deg, #f0f9ff, #e0f2fe);
    color: var(--primary-color);
    border: 2px solid #0ea5e9;
    border-radius: 8px;
    cursor: pointer;
    font-family: "Tajawal", sans-serif;
    font-weight: 600;
    transition: all 0.3s ease;
}

.batch-preset-btn:hover {
    background: linear-gradient(135deg, #0ea5e9, #0284c7);
    color: white;
    transform: translateY(-2px);
}

.week-button {
    padding: 12px 15px;
    background: linear-gradient(135deg, #f8fafc, #e2e8f0);
    color: var(--dark-color);
    border: 2px solid #cbd5e1;
    border-radius: 8px;
    cursor: pointer;
    font-family: "Tajawal", sans-serif;
    font-size: 14px;
    font-weight: 600;
    transition: all 0.3s ease;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
}

.week-button:hover {
    transform: translateY(-3px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.week-button.selected {
    background: linear-gradient(135deg, #10b981, #059669);
    color: white;
    border-color: #10b981;
    box-shadow: 0 0 0 2px rgba(16, 185, 129, 0.3);
}

.week-button .week-number {
    font-size: 16px;
    font-weight: 700;
}

.week-button .week-range {
    font-size: 11px;
    opacity: 0.8;
}

/* تصميم متجاوب */
@media (max-width: 992px) {
    .container {
        width: 98%;
        padding: 20px;
    }
    
    .school-name {
        font-size: 24px;
    }
    
    .controls {
        padding: 15px;
    }
    
    button {
        padding: 10px 18px;
        font-size: 13px;
    }
    
    .date-container {
        gap: 15px;
    }
    
    .date-card {
        min-width: 180px;
        padding: 12px 20px;
    }
}

@media (max-width: 768px) {
    .school-name {
        font-size: 20px;
    }
    
    .teacher-input-row {
        flex-direction: column;
        gap: 10px;
    }
    
    .teacher-input {
        width: 90%;
    }
    
    .week-buttons-grid {
        grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    }
    
    .class-tabs {
        flex-direction: column;
    }
    
    .class-tab {
        text-align: center;
    }
    
    table {
        font-size: 12px;
    }
    
    th, td {
        padding: 10px 6px;
    }
    
    .weeks-grid {
        grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    }
}

@media (max-width: 480px) {
    .container {
        padding: 15px;
    }
    
    .controls {
        flex-direction: column;
        align-items: center;
    }
    
    button {
        width: 100%;
        max-width: 300px;
    }
    
    input[type="password"] {
        width: 100%;
        max-width: 300px;
    }
    
    .weeks-grid {
        grid-template-columns: 1fr;
    }
    
    .week-buttons-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* تصميم خاص للطباعة */
@media print {
    button, .admin-panel, .status-filter, .class-tabs, 
    .week-checkboxes-container, .selected-weeks-display, 
    .export-section, .student-management, .controls {
        display: none !important;
    }
    
    .container {
        box-shadow: none;
        padding: 0;
    }
    
    header {
        background: white !important;
        color: black !important;
        padding: 10px 0 !important;
        box-shadow: none !important;
    }
    
    .teacher-input-container {
        display: none !important;
    }
    
    .teacher-display {
        display: block !important;
        background: white !important;
        color: black !important;
        border: 1px solid #ccc !important;
    }
    
    table {
        box-shadow: none !important;
    }
}
</style>
<!-- مكتبة ummAlQura لحساب التاريخ الهجري -->
<script src="https://cdn.jsdelivr.net/npm/ummalqura-js@2.0.0/dist/ummalqura.umd.min.js"></script>
<!-- رابط خط Tajawal -->
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
</head>
<body>

<header>
    <div class="header-container">
        <div class="school-name">مدرسة سعيد بن العاص المتوسطة</div>
        
        <div class="teacher-input-container">
            <div class="teacher-input-row">
                <span class="teacher-input-label">اسم المعلم:</span>
                <input type="text" id="teacherNameInput" class="teacher-input" placeholder="أدخل اسم المعلم هنا">
                <button onclick="saveTeacherName()" class="teacher-save-btn">💾 حفظ</button>
            </div>
            <div id="teacherDisplay" class="teacher-display" style="display: none;"></div>
        </div>
    </div>
</header>

<div class="container">
    <div class="controls">
        <button onclick="exportToExcel()">📊 تصدير اليوم Excel</button>
        <button onclick="exportSelectedWeeks()">📅 تصدير الأسابيع المحددة</button>
        <button onclick="printPage()">🖨️ طباعة</button>
        <button onclick="showAllClasses()">👁️ عرض الكل</button>
        <button onclick="showTodayAttendance()">📅 عرض تحضير اليوم</button>
    </div>
    
    <div class="class-tabs" id="classTabs">
        <!-- سيتم إنشاء الألسنة ديناميكياً -->
    </div>
    
    <div class="status-filter">
        <button onclick="filterByStatus('all')" class="active">الكل</button>
        <button onclick="filterByStatus('present')">الحاضرون</button>
        <button onclick="filterByStatus('absent')">الغائبون</button>
        <button onclick="filterByStatus('star')">المتميزون ⭐</button>
    </div>
    
    <div id="tablesContainer">
        <!-- سيتم إنشاء الجداول ديناميكياً -->
    </div>
    
    <div class="student-count" id="studentCount">إجمالي الطلاب: 0</div>
    
    <div style="text-align: center; margin-top: 25px;">
        <input type="password" id="adminPass" placeholder="كلمة المرور للإدارة" style="width: 250px;">
        <button onclick="checkAdmin()">🔓 فتح الإدارة</button>
    </div>

    <div class="admin-panel" id="adminPanel">
        <h3 style="text-align:center; margin-top:0; color: var(--primary-color);">لوحة الإدارة - الخصائص الإدارية</h3>
        
        <div class="admin-section">
            <h4>🎓 إعدادات الفصل الدراسي</h4>
            <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 20px;">
                <div>
                    <label style="display: block; margin-bottom: 8px; font-weight: 600;">الفصل الدراسي:</label>
                    <select id="semesterSelect" onchange="updateSemester()" style="width: 100%; padding: 12px; border-radius: 8px; border: 2px solid #e2e8f0;">
                        <option value="1">الترم الأول</option>
                        <option value="2" selected>الترم الثاني</option>
                    </select>
                </div>
                <div>
                    <label style="display: block; margin-bottom: 8px; font-weight: 600;">السنة الدراسية:</label>
                    <input type="text" id="academicYear" value="١٤٤٦-١٤٤٧هـ" style="width: 100%; padding: 12px; border-radius: 8px; border: 2px solid #e2e8f0;">
                </div>
            </div>
            <div style="text-align: center; margin-top: 20px;">
                <button onclick="saveSemesterSettings()" style="background: linear-gradient(135deg, #10b981, #059669);">💾 حفظ إعدادات الفصل</button>
                <div class="semester-info" id="currentSemesterInfo" style="display: inline-block; padding: 12px 20px; background: linear-gradient(135deg, #dbeafe, #93c5fd); border-radius: 8px; color: var(--primary-color); font-weight: bold; margin-right: 15px;">الترم الثاني ١٤٤٦-١٤٤٧هـ</div>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>📅 التحضير الأسبوعي (الأسابيع الدراسية الفعلية)</h4>
            
            <div class="selected-weeks-display" id="selectedWeeksDisplay" style="background: linear-gradient(135deg, #dbeafe, #93c5fd); border: 2px solid var(--primary-color); border-radius: 12px; padding: 20px; margin: 20px 0; text-align: center;">
                <strong style="font-size: 16px;">الأسابيع المحددة:</strong> 
                <div id="selectedWeeksText" style="margin: 10px 0; color: var(--dark-color);">لا توجد أسابيع محددة</div>
                <div id="selectedWeeksCount" style="color: var(--gray-color); font-size: 14px;">0 أسبوع | 0 يوم</div>
            </div>
            
            <!-- قسم اختيار الدفعات المحسن -->
            <div class="batch-selection" style="background: linear-gradient(135deg, #f0f9ff, #e0f2fe); border: 2px solid #0ea5e9; border-radius: 12px; padding: 25px; margin: 25px 0;">
                <h4 style="text-align: center; color: var(--primary-color); margin-top: 0;">🗓️ تحديد دفعات الأسابيع (19 دفعة)</h4>
                
                <div style="text-align: center; margin-bottom: 20px;">
                    <div style="display: inline-flex; align-items: center; gap: 15px; background: white; padding: 15px 25px; border-radius: 10px; box-shadow: 0 4px 12px rgba(0,0,0,0.08);">
                        <span style="font-weight: 600; color: var(--dark-color);">وضع الاختيار:</span>
                        <div style="display: flex; gap: 10px;">
                            <button id="modeIndividual" onclick="setSelectionMode('individual')" class="selection-mode-btn active" style="padding: 10px 20px;">🔘 فردي</button>
                            <button id="modeBatch" onclick="setSelectionMode('batch')" class="selection-mode-btn" style="padding: 10px 20px;">📋 دفعة</button>
                        </div>
                    </div>
                </div>
                
                <!-- عرض الدفعات المحددة -->
                <div class="selected-batches-display" id="selectedBatchesDisplay" style="background: linear-gradient(135deg, #dbeafe, #93c5fd); border: 2px solid var(--primary-color); border-radius: 12px; padding: 20px; margin: 20px 0; text-align: center; display: none;">
                    <strong style="font-size: 16px;">الدفعات المحددة:</strong> 
                    <div id="selectedBatchesText" style="margin: 10px 0; color: var(--dark-color);">لا توجد دفعات محددة</div>
                    <button onclick="clearBatchSelection()" style="background: linear-gradient(135deg, #e63946, #c1121f); margin-top: 10px;">🗑️ مسح الدفعات</button>
                </div>
                
                <!-- اختيار دفعات مسبقة -->
                <div class="predefined-batches" style="margin: 20px 0;">
                    <h5 style="text-align: center; color: var(--dark-color); margin-bottom: 15px;">📚 دفعات جاهزة</h5>
                    <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 12px; margin-bottom: 25px;">
                        <button onclick="selectBatch('first_half')" class="batch-preset-btn">النصف الأول (أسابيع 1-9)</button>
                        <button onclick="selectBatch('second_half')" class="batch-preset-btn">النصف الثاني (أسابيع 10-19)</button>
                        <button onclick="selectBatch('month1')" class="batch-preset-btn">الشهر الأول (أسابيع 1-4)</button>
                        <button onclick="selectBatch('month2')" class="batch-preset-btn">الشهر الثاني (أسابيع 5-8)</button>
                        <button onclick="selectBatch('month3')" class="batch-preset-btn">الشهر الثالث (أسابيع 9-12)</button>
                        <button onclick="selectBatch('month4')" class="batch-preset-btn">الشهر الرابع (أسابيع 13-16)</button>
                        <button onclick="selectBatch('month5')" class="batch-preset-btn">الشهر الخامس (أسابيع 17-19)</button>
                    </div>
                </div>
                
                <!-- شبكة أزرار الأسابيع -->
                <div class="week-buttons-grid-container" style="background: white; border-radius: 10px; padding: 20px; border: 1px solid #e2e8f0;">
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px; padding-bottom: 15px; border-bottom: 2px solid #e2e8f0;">
                        <span style="font-weight: 600; color: var(--dark-color);">اختر الأسبوع:</span>
                        <div>
                            <button onclick="selectAllWeeks()" style="padding: 8px 15px; font-size: 12px; background: #8b5cf6;">📋 الكل</button>
                            <button onclick="clearSelectedWeeks()" style="padding: 8px 15px; font-size: 12px; background: #e63946;">🗑️ مسح</button>
                        </div>
                    </div>
                    
                    <div class="week-buttons-grid" id="weekButtonsContainer" style="display: grid; grid-template-columns: repeat(auto-fill, minmax(110px, 1fr)); gap: 12px;">
                        <!-- سيتم إنشاء أزرار الأسابيع هنا ديناميكياً -->
                    </div>
                    
                    <!-- اختيار نطاق دفعة -->
                    <div class="batch-range-selector" id="batchRangeSelector" style="display: none; margin-top: 25px; padding: 20px; background: #f8fafc; border-radius: 10px; border: 2px dashed #cbd5e1;">
                        <h5 style="text-align: center; color: var(--primary-color); margin-top: 0;">📅 تحديد نطاق دفعة</h5>
                        <div style="display: flex; justify-content: center; align-items: center; gap: 15px; flex-wrap: wrap;">
                            <div style="display: flex; flex-direction: column; align-items: center;">
                                <label style="font-weight: 600; margin-bottom: 8px;">من أسبوع:</label>
                                <select id="batchStartWeek" style="padding: 10px 15px; border-radius: 8px; border: 2px solid #e2e8f0; min-width: 120px;">
                                    <!-- سيتم تعبئة الخيارات ديناميكياً -->
                                </select>
                            </div>
                            <div style="font-size: 24px; color: var(--primary-color);">→</div>
                            <div style="display: flex; flex-direction: column; align-items: center;">
                                <label style="font-weight: 600; margin-bottom: 8px;">إلى أسبوع:</label>
                                <select id="batchEndWeek" style="padding: 10px 15px; border-radius: 8px; border: 2px solid #e2e8f0; min-width: 120px;">
                                    <!-- سيتم تعبئة الخيارات ديناميكياً -->
                                </select>
                            </div>
                            <button onclick="addBatchRange()" style="padding: 12px 25px; background: linear-gradient(135deg, #10b981, #059669); align-self: flex-end;">➕ إضافة دفعة</button>
                        </div>
                    </div>
                </div>
                
                <div style="text-align: center; margin-top: 25px; color: var(--gray-color); font-size: 14px;">
                    <span>💡 يمكنك اختيار الأسابيع فردياً أو كدفعات (مجموعات)</span>
                </div>
            </div>
            
            <div class="week-controls" style="display: flex; justify-content: center; gap: 15px; margin-bottom: 25px; flex-wrap: wrap;">
                <button onclick="selectAllWeeks()" style="background: linear-gradient(135deg, #8b5cf6, #7c3aed);">📋 تحديد الكل</button>
                <button onclick="clearSelectedWeeks()" style="background: linear-gradient(135deg, #e63946, #c1121f);">🗑️ مسح الكل</button>
                <button onclick="selectFirstSemesterWeeks()" style="background: linear-gradient(135deg, #f59e0b, #d97706);">📚 الترم الأول (19 أسبوع)</button>
            </div>
            
            <div class="week-checkboxes-container" style="background: white; border-radius: 12px; padding: 25px; margin: 25px 0; box-shadow: 0 5px 15px rgba(0,0,0,0.05);">
                <div class="semester-title" style="background: linear-gradient(135deg, var(--primary-color), var(--secondary-color)); color: white; padding: 15px; border-radius: 10px; margin-bottom: 25px; text-align: center; font-size: 18px; font-weight: 700;">الترم الأول (19 أسبوع دراسي)</div>
                <div class="weeks-grid" id="weeksCheckboxesContainer">
                    <!-- سيتم إنشاء مربعات اختيار الأسابيع هنا -->
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 30px;">
                <button onclick="randomAttendanceForSelectedWeeks()" style="background: linear-gradient(135deg, #10b981, #059669); padding: 15px 35px; font-size: 16px; font-weight: 700;">
                    🎲 تحضير عشوائي للأسابيع المحددة
                </button>
            </div>
            
            <div style="text-align:center; margin-top:15px; font-size:13px; color:var(--gray-color); padding: 15px; background: #f8fafc; border-radius: 8px;">
                ⭐ خاصية التحضير العشوائي: سيتم وضع ✓ لكل الخيارات للطلاب المتميزين (الذين لديهم نجمة ⭐)
            </div>
        </div>
        
        <div class="export-section">
            <h4>📤 تصدير التقارير</h4>
            <div style="text-align: center; margin-top: 20px; display: flex; justify-content: center; gap: 20px; flex-wrap: wrap;">
                <button onclick="exportSelectedWeeks()" style="background: linear-gradient(135deg, #10b981, #059669); padding: 15px 30px; font-size: 15px;">
                    📥 تصدير الأسابيع المحددة إلى Excel
                </button>
                <button onclick="exportAllWeeks()" style="background: linear-gradient(135deg, var(--primary-color), var(--secondary-color)); padding: 15px 30px; font-size: 15px;">
                    📚 تصدير جميع أسابيع الترم الأول
                </button>
                <button onclick="exportEachWeekSeparately()" style="background: linear-gradient(135deg, #8b5cf6, #7c3aed); padding: 15px 30px; font-size: 15px;">
                    📁 تصدير كل أسبوع في ملف منفصل
                </button>
            </div>
        </div>
        
        <div class="student-management" style="background: linear-gradient(135deg, #f0f9ff, #e0f2fe); border: 2px solid #0ea5e9; border-radius: 12px; padding: 25px; margin-top: 25px;">
            <h4>👨‍🏫 إدارة الطلاب</h4>
            
            <div class="loading-spinner" id="loadingSpinner">
                <div class="spinner"></div>
                <div style="margin-top: 15px; font-weight: 600; color: var(--primary-color);">جاري المعالجة...</div>
            </div>
            
            <div class="management-form">
                <h5 style="margin-top: 0; color: var(--primary-color); font-size: 16px;">➕ إضافة طالب جديد</h5>
                <input type="text" id="newStudentName" placeholder="اسم الطالب الجديد" style="width: 100%;">
                
                <div style="display: grid; grid-template-columns: 1fr 2fr; gap: 15px; align-items: center;">
                    <div style="font-weight: 600;">الصف:</div>
                    <div>
                        <select id="newStudentClass" style="width: 100%;">
                            <option value="3-1">3-1</option>
                            <option value="2-3">2-3</option>
                            <option value="3-3">3-3</option>
                            <option value="4-3">4-3</option>
                            <option value="5-3">5-3</option>
                        </select>
                    </div>
                </div>
                
                <div class="form-buttons" style="display: flex; justify-content: center; gap: 15px; margin-top: 20px;">
                    <button onclick="addStudent()" style="background: linear-gradient(135deg, #10b981, #059669);">➕ إضافة الطالب</button>
                    <button onclick="clearStudentForm()" style="background: linear-gradient(135deg, #e63946, #c1121f);">🗑️ مسح النموذج</button>
                </div>
            </div>
            
            <div class="management-form">
                <h5 style="margin-top: 0; color: var(--primary-color); font-size: 16px;">↔️ نقل طالب بين الصفوف</h5>
                
                <div style="display: grid; grid-template-columns: 1fr 2fr; gap: 15px; align-items: center;">
                    <div style="font-weight: 600;">اختر الطالب:</div>
                    <div>
                        <select id="studentToMove" style="width: 100%;" onchange="updateStudentMoveInfo()">
                            <option value="">-- اختر الطالب --</option>
                        </select>
                    </div>
                </div>
                
                <div style="display: grid; grid-template-columns: 1fr 2fr; gap: 15px; align-items: center;">
                    <div style="font-weight: 600;">الصف الحالي:</div>
                    <div>
                        <input type="text" id="currentStudentClass" readonly style="width: 100%; background: #f8fafc; border: 2px dashed #cbd5e1;">
                    </div>
                </div>
                
                <div style="display: grid; grid-template-columns: 1fr 2fr; gap: 15px; align-items: center;">
                    <div style="font-weight: 600;">الصف الهدف:</div>
                    <div>
                        <select id="targetClass" style="width: 100%;">
                            <option value="3-1">3-1</option>
                            <option value="2-3">2-3</option>
                            <option value="3-3">3-3</option>
                            <option value="4-3">4-3</option>
                            <option value="5-3">5-3</option>
                        </select>
                    </div>
                </div>
                
                <div class="form-buttons" style="display: flex; justify-content: center; gap: 15px; margin-top: 20px;">
                    <button onclick="moveStudent()" style="background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));">↔️ نقل الطالب</button>
                    <button onclick="refreshStudentList()" style="background: linear-gradient(135deg, #f59e0b, #d97706);">🔄 تحديث القائمة</button>
                </div>
            </div>
            
            <div style="text-align:center; margin-top:25px;">
                <button onclick="randomAttendance()" style="background: linear-gradient(135deg, #8b5cf6, #7c3aed); padding: 15px 30px; font-size: 15px;">🎲 تحضير عشوائي للتاريخ الحالي</button>
            </div>
        </div>
        
        <div style="text-align:center; margin-top:30px;">
            <button onclick="checkAdmin()" style="background: linear-gradient(135deg, #e63946, #c1121f); padding: 15px 40px; font-size: 16px; font-weight: 700;">
                🔒 إغلاق لوحة الإدارة
            </button>
        </div>
    </div>
</div>

<script>
// البيانات والوظائف تبقى كما هي بدون تغيير
// بيانات الطلاب لكل صف
const studentsData = {
    "3-1": [
        "إسماعيل محمد هاشم شفيق الرحمن",
        "ابراهيم علي ابو بكر محمد",
        "باسم محمد ابو طالب",
        "حسين بشير أمادو جازير",
        "حسين هارون عثمان عبدالمؤمن ادم",
        "حمد محمد عثمان بخش",
        "رمضان عيسى باكور محمد",
        "ريان عبد الرحمن موسى جيبو",
        "ريحان محمد مقبول حسين عمر حمزه",
        "عامر مولوي حسن شريف",
        "عبدالحليم نور كبير صديق احمد",
        "عمران يعقوب محمد محمد مسلم",
        "عمير محمد محمد شفيع حكيم علي",
        "فارس محمد ابو البشر واعظ علي",
        "محمد احمد فضل الرحمن فايز اللّٰه",
        "حمد انوار رشيد احمد اظهار مياه",
        "حمد عبدالرزاق محمد عبدالقادر",
        "حمد عبدالشكور عبدالحميد عبد الرشيد",
        "مهدي محمد محمد اسلام عبدالسلام",
        "مهدي موسى حميد الحق احمد",
        "ياسين محمد يوسف"
    ],
    "2-3": [
        "إبراهيم إدريس إبراهيم اولوجيوم",
        "إدريس محمد حسن أحمد",
        "امين عبداللّه دايابو عثمان",
        "بسام عبدالسلام هاشم انور علي",
        "حافظ بيلو موسى سليمان",
        "حسين علي حسن مهاوش",
        "خالد طيب اسماعيل محمد",
        "خالد عبد الحميد محمد هاشم",
        "خالد وليد محمد محمد",
        "ريان عبدالرحمن عمر نانتومي",
        "سليمان ابراهيم ديقوقا",
        "صالح عبدالله محمد قاسم يوسف علي",
        "عبدالعزيز اول اودو محمد",
        "عثمان عبد الرحمن باي محمد",
        "عدنان نور امير حسين",
        "عمر سراج محمد زكريا",
        "فهد محمد حسين عبداللّه مياه حسين",
        "محمد ابراهيم سعيد هو ساوي",
        "محمد محمد امين اسلام خليل الرحمن",
        "مشعل ابو طاهر ناظر حسين عبدالمطلب",
        "موسى ابو بكر الصديق عبدالجبار امة علي",
        "يوسف مهدي عابدين محمد"
    ],
    "3-3": [
        "ابراهيم جزولي اسدانور",
        "تركي عبدالصمد عبدالغني محمد حسين",
        "حسام حسن ابو الكلام مقبول احمد",
        "حسن عيسى بكوري محمد",
        "سعد سلام ستار ارشاد اللّٰه",
        "عايض سيف الاسلام نور احمد علي",
        "عبدالكريم عثمان ابكر كوجو",
        "عزام شمس العالم قاسم علي",
        "عماد محمد صديق محمد شفيع سيد",
        "عمر عبد القدوس عبدالسلام عبد السبحان",
        "عمر مورتلا أبو بكر محمد",
        "فيصل احمد ابو بكر محمد",
        "محمد اسحاق محمد اسلام عبدالحكيم",
        "محمد عبدالله ابو سعيد مياه",
        "حمد محمد اسماعيل امير حسين ابو بكر",
        "حمد موسى ساليفو ديقوقا",
        "مشاري شيهو اسماعيل محمد بكر",
        "ياسر عبدالرحيم محمد علي سفر علي",
        "يوسف محمد عبد الرحمن علي"
    ],
    "4-3": [
        "ابراهيم عوض احمد فليس",
        "احمد ابراهيم ابن زكريا الهوسه",
        "احمد عبد القيوم محمد يعقوب",
        "اسماعيل اول اودو محمد",
        "اوسامة سعيدو دو غويد",
        "تامر عبد الصمد عبد الغني",
        "تركي هارون حسن شريف",
        "ريان محمد مقبول حسين حسين",
        "ريان هارون الرشيد طفيل احمد نذير احمد",
        "عبدالحليم محمد عبدالله عبدالحكيم",
        "عبدالله حفيظ اللّٰه سلطان أحمد",
        "عيسى عثمان سعيد عالم حبيب الرحمن",
        "فهد أسار رشيد احمد",
        "فهد محمد نور مقبول اشرف",
        "محمد محمد ادريس نبية حسين يعقوب علي",
        "مصلح محمد ولي احمد",
        "معاذ عثمان صديق كالو",
        "يوسف بدماسي ابراهيم البد ماسي"
    ],
    "5-3": [
        "ابراهيم خالد سليمان ابراهيم",
        "انس عبدالعزيز نور احمد",
        "بدر بكر عمر محمد",
        "حمد محمد حسين مياه شمس العالم اظهر مياه",
        "رضوان رشيد أحمد نور محمد لال مياه",
        "سعيد عبدالله سعيد محمد",
        "عامر رحمة اللّٰه محمد شفيع",
        "عبد اللّٰه حسين علي فليس",
        "عبد العزيز سراج ابكر عثمان",
        "عبدالله عيسى ابراهيم",
        "عمر محمد عمر صالح",
        "غسان عثمان اسماعيل عبدالله عبد اللّٰه",
        "فاضل عادل صالح الرايس",
        "محمد فريد كبير احمد عباد اللّٰه",
        "محمد محمد سلطان احمد محمد",
        "محمد موسى أدامو محمد",
        "محمد نور محمد زكريا آمال حسين",
        "مشاري محمد هارو",
        "مشاري يعقوب أبو بكر ابراهيم",
        "منذر علي عمر قوني",
        "هود حسن عبدالكريم الياس",
        "يعقوب محمد إسحاق يار محمد فضل على"
    ]
};

// تعريف الأسابيع الجديد مع الترقيم 1-19 (تم إضافة أسبوع إضافي)
const studyWeeks = {
    1: { name: "الأسبوع الأول", days: 5, startDate: "2025/08/24", endDate: "2025/08/28", hijri: "1447/03/01 - 1447/03/05" },
    2: { name: "الأسبوع الثاني", days: 5, startDate: "2025/08/31", endDate: "2025/09/04", hijri: "1447/03/08 - 1447/03/12" },
    3: { name: "الأسبوع الثالث", days: 5, startDate: "2025/09/07", endDate: "2025/09/11", hijri: "1447/03/15 - 1447/03/19" },
    4: { name: "الأسبوع الرابع", days: 5, startDate: "2025/09/14", endDate: "2025/09/18", hijri: "1447/03/22 - 1447/03/26" },
    5: { name: "الأسبوع الخامس", days: 5, startDate: "2025/09/21", endDate: "2025/09/25", hijri: "1447/03/29 - 1447/04/02" },
    6: { name: "الأسبوع السادس", days: 5, startDate: "2025/09/28", endDate: "2025/10/02", hijri: "1447/04/05 - 1447/04/09" },
    7: { name: "الأسبوع السابع", days: 5, startDate: "2025/10/05", endDate: "2025/10/09", hijri: "1447/04/12 - 1447/04/16" },
    8: { name: "الأسبوع الثامن", days: 4, startDate: "2025/10/13", endDate: "2025/10/16", hijri: "1447/04/20 - 1447/04/23" },
    9: { name: "الأسبوع التاسع", days: 5, startDate: "2025/10/19", endDate: "2025/10/23", hijri: "1447/04/26 - 1447/04/30" },
    10: { name: "الأسبوع العاشر", days: 5, startDate: "2025/10/26", endDate: "2025/10/30", hijri: "1447/05/03 - 1447/05/07" },
    11: { name: "الأسبوع الحادي عشر", days: 5, startDate: "2025/11/02", endDate: "2025/11/06", hijri: "1447/05/10 - 1447/05/14" },
    12: { name: "الأسبوع الثاني عشر", days: 5, startDate: "2025/11/09", endDate: "2025/11/13", hijri: "1447/05/17 - 1447/05/21" },
    13: { name: "الأسبوع الثالث عشر", days: 5, startDate: "2025/11/16", endDate: "2025/11/20", hijri: "1447/05/24 - 1447/05/28" },
    14: { name: "الأسبوع الرابع عشر", days: 5, startDate: "2025/11/23", endDate: "2025/11/27", hijri: "1447/06/02 - 1447/06/06" },
    15: { name: "الأسبوع الخامس عشر", days: 4, startDate: "2025/11/30", endDate: "2025/12/03", hijri: "1447/06/09 - 1447/06/12" },
    16: { name: "الأسبوع السادس عشر", days: 4, startDate: "2025/12/08", endDate: "2025/12/11", hijri: "1447/06/17 - 1447/06/20" },
    17: { name: "الأسبوع السابع عشر", days: 5, startDate: "2025/12/14", endDate: "2025/12/18", hijri: "1447/06/23 - 1447/06/27" },
    18: { name: "الأسبوع الثامن عشر", days: 5, startDate: "2025/12/21", endDate: "2025/12/25", hijri: "1447/07/01 - 1447/07/05" },
    19: { name: "الأسبوع التاسع عشر", days: 5, startDate: "2025/12/28", endDate: "2026/01/01", hijri: "1447/07/08 - 1447/07/12" }
};

// حالة الإدارة
let adminActive = false;
let currentFilter = 'all';
let currentClass = 'all';

// إعدادات الفصل الدراسي
let semesterSettings = {
    semester: "2",
    academicYear: "١٤٤٦-١٤٤٧هـ"
};

// اسم المعلم
let teacherName = "";

// الأسابيع المحددة
let selectedWeeks = [];

// بيانات التحضير المخزنة لكل يوم
let periodAttendanceData = {};

// بيانات النجوم المحفوظة
let starredStudents = {};

// ======== دوال إدارة الدفعات ========

let selectionMode = 'individual'; // 'individual' أو 'batch'
let selectedBatches = []; // تخزين الدفعات المحددة

// تحويل الأرقام الإنجليزية إلى عربية
function convertToArabicNumbers(num) {
    const arabicNumbers = ['٠', '١', '٢', '٣', '٤', '٥', '٦', '٧', '٨', '٩'];
    return num.toString().replace(/\d/g, digit => arabicNumbers[digit]);
}

// تهيئة الصفحة
function initPage() {
    // محاولة تحميل إعدادات الفصل الدراسي
    const savedSemester = localStorage.getItem('teacherTracker_semesterSettings');
    if (savedSemester) {
        semesterSettings = JSON.parse(savedSemester);
        document.getElementById('semesterSelect').value = semesterSettings.semester;
        document.getElementById('academicYear').value = semesterSettings.academicYear;
        updateSemesterInfo();
    }
    
    // محاولة تحميل اسم المعلم
    const savedTeacherName = localStorage.getItem('teacherTracker_teacherName');
    if (savedTeacherName) {
        teacherName = savedTeacherName;
        document.getElementById('teacherNameInput').value = teacherName;
        showTeacherDisplay();
    }
    
    // محاولة تحميل الأسابيع المحددة
    const savedWeeks = localStorage.getItem('teacherTracker_selectedWeeks');
    if (savedWeeks) {
        selectedWeeks = JSON.parse(savedWeeks);
    }
    
    // محاولة تحميل بيانات النجوم
    const savedStars = localStorage.getItem('teacherTracker_starredStudents');
    if (savedStars) {
        starredStudents = JSON.parse(savedStars);
    }
    
    // محاولة تحميل بيانات التحضير المحفوظة
    loadPeriodAttendanceData();
    
    createClassTabs();
    createTables();
    createWeekCheckboxes();
    createWeekButtons();
    updateStudentCount();
    refreshStudentList();
    
    // تهيئة وضع الاختيار
    setSelectionMode('individual');
    updateSelectedBatchesDisplay();
}

// حفظ اسم المعلم
function saveTeacherName() {
    const input = document.getElementById('teacherNameInput');
    teacherName = input.value.trim();
    
    if (teacherName) {
        localStorage.setItem('teacherTracker_teacherName', teacherName);
        showTeacherDisplay();
        alert(`✅ تم حفظ اسم المعلم: ${teacherName}`);
    } else {
        alert("⚠️ الرجاء إدخال اسم المعلم");
    }
}

// عرض اسم المعلم المحفوظ
function showTeacherDisplay() {
    if (teacherName) {
        const displayElement = document.getElementById('teacherDisplay');
        displayElement.textContent = `المعلم: ${teacherName}`;
        displayElement.style.display = 'block';
    }
}

// ======== إدارة النجوم ========

// حفظ النجوم
function saveStarredStudents() {
    localStorage.setItem('teacherTracker_starredStudents', JSON.stringify(starredStudents));
}

// التحقق إذا كان الطالب مميزاً
function isStudentStarred(className, studentName) {
    return starredStudents[className] && starredStudents[className].includes(studentName);
}

// ======== إنشاء واجهة المستخدم ========

// إنشاء ألسنة الصفوف
function createClassTabs() {
    const classTabs = document.getElementById('classTabs');
    classTabs.innerHTML = '<div class="class-tab active" onclick="showClass(\'all\')">جميع الصفوف</div>';
    
    for (const className in studentsData) {
        classTabs.innerHTML += `<div class="class-tab" onclick="showClass('${className}')">الصف ${className}</div>`;
    }
}

// إنشاء الجداول للصفوف
function createTables() {
    const container = document.getElementById('tablesContainer');
    container.innerHTML = '';
    
    for (const className in studentsData) {
        const classDiv = document.createElement('div');
        classDiv.className = 'class-section';
        classDiv.id = `class-${className}`;
        
        const classHeader = document.createElement('div');
        classHeader.className = 'class-header';
        classHeader.textContent = `الصف ${className} - ${studentsData[className].length} طالب`;
        
        const table = document.createElement('table');
        table.innerHTML = `
            <thead>
                <tr>
                    <th width="5%">م</th>
                    <th>الاسم</th>
                    <th width="10%">الحضور</th>
                    <th width="10%">الواجبات</th>
                    <th width="10%">المشروعات</th>
                    <th width="10%">تطبيقات وأنشطة</th>
                    <th width="10%">مشاركة</th>
                    <th width="10%">⭐</th>
                </tr>
            </thead>
            <tbody id="tbody-${className}">
            </tbody>
        `;
        
        classDiv.appendChild(classHeader);
        classDiv.appendChild(table);
        container.appendChild(classDiv);
        
        fillClassTable(className);
    }
    
    showClass('all');
}

// ملء جدول الصف بالطلاب
function fillClassTable(className) {
    const tbody = document.getElementById(`tbody-${className}`);
    tbody.innerHTML = '';
    
    studentsData[className].forEach((student, index) => {
        const row = document.createElement('tr');
        const isStarred = isStudentStarred(className, student);
        
        row.innerHTML = `
            <td>${index + 1}</td>
            <td>${student}</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggleStar(this, '${className}', ${index})" class="star-cell">${isStarred ? '⭐' : '☆'}</td>
        `;
        
        if (isStarred) {
            row.classList.add('starred-student');
        }
        
        tbody.appendChild(row);
    });
}

// تبديل النجمة
function toggleStar(cell, className, studentIndex) {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const studentName = studentsData[className][studentIndex];
    
    if (cell.innerHTML === "☆") {
        cell.innerHTML = "⭐";
        cell.closest('tr').classList.add('starred-student');
        
        if (!starredStudents[className]) {
            starredStudents[className] = [];
        }
        if (!starredStudents[className].includes(studentName)) {
            starredStudents[className].push(studentName);
        }
    } else {
        cell.innerHTML = "☆";
        cell.closest('tr').classList.remove('starred-student');
        
        if (starredStudents[className]) {
            const index = starredStudents[className].indexOf(studentName);
            if (index !== -1) {
                starredStudents[className].splice(index, 1);
            }
        }
    }
    
    saveStarredStudents();
}

// تبديل حالة ✔ و ✖
function toggle(cell) {
    if (cell.innerHTML === "✔") {
        cell.innerHTML = "✖";
        cell.classList.remove('present');
        cell.classList.add('absent');
        cell.classList.add('error-cell');
    } else {
        cell.innerHTML = "✔";
        cell.classList.remove('absent');
        cell.classList.remove('error-cell');
        cell.classList.add('present');
    }
}

// ======== التحضير العشوائي ========

// تحضير عشوائي للتاريخ الحالي
function randomAttendance() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const confirmAction = confirm("هل تريد تعيين الحضور عشوائيا لجميع الطلاب للتاريخ الحالي؟");
    if (!confirmAction) return;
    
    document.querySelectorAll('.class-section').forEach(section => {
        const rows = section.querySelectorAll('tbody tr');
        const className = section.id.replace('class-', '');
        
        rows.forEach((row, index) => {
            const studentName = studentsData[className][index];
            const isStarred = isStudentStarred(className, studentName);
            const attendanceCells = row.querySelectorAll('td[onclick="toggle(this)"]');
            
            if (isStarred) {
                // الطلاب المميزون: كل الخيارات ✔
                attendanceCells.forEach(cell => {
                    cell.innerHTML = "✔";
                    cell.classList.remove('absent');
                    cell.classList.remove('error-cell');
                    cell.classList.add('present');
                });
            } else {
                // الطلاب العاديون: 3 ✔ فقط بشكل عشوائي
                const indices = [0, 1, 2, 3, 4];
                
                // خلط المؤشرات
                for (let i = indices.length - 1; i > 0; i--) {
                    const j = Math.floor(Math.random() * (i + 1));
                    [indices[i], indices[j]] = [indices[j], indices[i]];
                }
                
                // اختيار أول 3 مؤشرات للصح
                const trueIndices = indices.slice(0, 3);
                
                attendanceCells.forEach((cell, idx) => {
                    if (trueIndices.includes(idx)) {
                        cell.innerHTML = "✔";
                        cell.classList.remove('absent');
                        cell.classList.remove('error-cell');
                        cell.classList.add('present');
                    } else {
                        cell.innerHTML = "✖";
                        cell.classList.remove('present');
                        cell.classList.add('absent');
                        cell.classList.add('error-cell');
                    }
                });
                
                // التأكد من عدم إعطاء نجمة للطلاب العاديين
                const starCell = row.querySelector('.star-cell');
                if (starCell && starCell.innerHTML === "⭐") {
                    starCell.innerHTML = "☆";
                    row.classList.remove('starred-student');
                }
            }
        });
    });
    
    alert("تم تعيين الحضور عشوائيا للتاريخ الحالي!");
}

// ======== باقي الدوال الأساسية ========

// التحقق من كلمة المرور
function checkAdmin() {
    const pass = document.getElementById("adminPass").value;
    if (pass === "1406") {
        adminActive = !adminActive;
        document.getElementById("adminPanel").style.display = adminActive ? "block" : "none";
        document.getElementById("adminPass").value = "";
        
        if (adminActive) {
            alert("✅ تم تفعيل خصائص الإدارة بنجاح!");
        } else {
            alert("تم إغلاق لوحة الإدارة");
        }
    } else {
        alert("❌ كلمة مرور خاطئة!");
    }
}

// تصدير إلى Excel للتاريخ الحالي
function exportToExcel() {
    const now = new Date();
    
    // استخدام اسم المعلم المحفوظ
    const teacherDisplay = teacherName ? `المعلم: ${teacherName}` : "";
    
    let tablesHTML = `<h2>سجل متابعة الطلاب - ${teacherDisplay}</h2>`;
    tablesHTML += `<h3>المادة: اللغة الإنجليزية - ${document.getElementById('currentSemesterInfo').textContent}</h3>`;
    tablesHTML += `<h3>المدرسة: سعيد بن العاص المتوسطة</h3>`;
    tablesHTML += `<h3>تاريخ التصدير: ${new Date().toLocaleDateString('ar-SA')}</h3>`;
    
    for (const className in studentsData) {
        tablesHTML += `<h3>الصف ${className}</h3>`;
        tablesHTML += document.getElementById(`class-${className}`).querySelector('table').outerHTML;
    }
    
    let uri = 'data:application/vnd.ms-excel;base64,';
    let template = `<html xmlns:o="urn:schemas-microsoft-com:office:office" 
                   xmlns:x="urn:schemas-microsoft-com:office:excel" 
                   xmlns="http://www.w3.org/TR/REC-html40">
                   <head>
                   <meta charset="UTF-8">
                   <!--[if gte mso 9]>
                   <xml>
                   <x:ExcelWorkbook>
                   <x:ExcelWorksheets>
                   <x:ExcelWorksheet>
                   <x:Name>تقرير الطلاب</x:Name>
                   <x:WorksheetOptions><x:DisplayGridlines/></x:WorksheetOptions>
                   </x:ExcelWorksheet>
                   </x:ExcelWorksheets>
                   </x:ExcelWorkbook>
                   </xml>
                   <![endif]-->
                   </head>
                   <body dir="rtl">${tablesHTML}</body></html>`;
    
    let link = document.createElement("a");
    link.href = uri + btoa(unescape(encodeURIComponent(template)));
    const dateStr = now.toISOString().split('T')[0];
    link.download = `تقرير_حضور_${dateStr}.xls`;
    link.click();
    
    alert("✅ تم تصدير التقرير بنجاح!");
}

// طباعة الصفحة
function printPage() {
    window.print();
}

// عرض صف معين أو جميع الصفوف
function showClass(className) {
    currentClass = className;
    
    document.querySelectorAll('.class-tab').forEach(tab => {
        tab.classList.remove('active');
    });
    
    if (className === 'all') {
        document.querySelectorAll('.class-tab')[0].classList.add('active');
        document.querySelectorAll('.class-section').forEach(section => {
            section.style.display = 'block';
        });
    } else {
        document.querySelector(`.class-tab[onclick="showClass('${className}')"]`).classList.add('active');
        document.querySelectorAll('.class-section').forEach(section => {
            section.style.display = 'none';
        });
        document.getElementById(`class-${className}`).style.display = 'block';
    }
    
    filterByStatus(currentFilter);
    updateStudentCount();
}

// عرض جميع الصفوف
function showAllClasses() {
    showClass('all');
}

// تصفية حسب الحالة
function filterByStatus(status) {
    currentFilter = status;
    
    document.querySelectorAll('.status-filter button').forEach(btn => {
        btn.classList.remove('active');
    });
    
    if (event && event.target) {
        event.target.classList.add('active');
    }
    
    let classSections = document.querySelectorAll('.class-section');
    if (currentClass !== 'all') {
        classSections = [document.getElementById(`class-${currentClass}`)];
    }
    
    classSections.forEach(section => {
        const rows = section.querySelectorAll('tbody tr');
        rows.forEach(row => {
            let showRow = false;
            
            if (status === 'all') {
                showRow = true;
            } else if (status === 'present') {
                const attendanceCells = row.querySelectorAll('td[onclick="toggle(this)"]');
                const allPresent = Array.from(attendanceCells).every(cell => cell.innerHTML === "✔");
                showRow = allPresent;
            } else if (status === 'absent') {
                const attendanceCells = row.querySelectorAll('td[onclick="toggle(this)"]');
                const anyAbsent = Array.from(attendanceCells).some(cell => cell.innerHTML === "✖");
                showRow = anyAbsent;
            } else if (status === 'star') {
                const starCell = row.querySelector('.star-cell');
                showRow = starCell && starCell.innerHTML === "⭐";
            }
            
            row.style.display = showRow ? '' : 'none';
        });
    });
}

// تحديث عدد الطلاب
function updateStudentCount() {
    let totalStudents = 0;
    
    if (currentClass === 'all') {
        for (const className in studentsData) {
            totalStudents += studentsData[className].length;
        }
    } else {
        totalStudents = studentsData[currentClass].length;
    }
    
    document.getElementById('studentCount').textContent = `إجمالي الطلاب: ${totalStudents}`;
}

// عرض تحضير اليوم
function showTodayAttendance() {
    alert("✅ تم العرض بتاريخ اليوم الحقيقي");
}

// ======== دوال الإدارة ========

// تحديث معلومات الفصل الدراسي المعروضة
function updateSemesterInfo() {
    const semesterNames = {
        "1": "الترم الأول",
        "2": "الترم الثاني"
    };
    
    const semesterName = semesterNames[semesterSettings.semester] || "الترم الدراسي";
    document.getElementById('currentSemesterInfo').textContent = 
        `${semesterName} ${semesterSettings.academicYear}`;
}

// تحديث إعدادات الفصل الدراسي
function updateSemester() {
    semesterSettings.semester = document.getElementById('semesterSelect').value;
    semesterSettings.academicYear = document.getElementById('academicYear').value;
    updateSemesterInfo();
}

// حفظ إعدادات الفصل الدراسي
function saveSemesterSettings() {
    updateSemester();
    localStorage.setItem('teacherTracker_semesterSettings', JSON.stringify(semesterSettings));
    alert(`✅ تم حفظ إعدادات الفصل الدراسي`);
}

// ======== إدارة الأسابيع ========

// إنشاء مربعات اختيار الأسابيع
function createWeekCheckboxes() {
    const container = document.getElementById('weeksCheckboxesContainer');
    container.innerHTML = '';
    
    // إنشاء مربعات اختيار للأسابيع 1-19
    for (let week = 1; week <= 19; week++) {
        const weekData = studyWeeks[week];
        const checkboxItem = document.createElement('div');
        checkboxItem.className = 'week-checkbox-item';
        checkboxItem.id = `week-checkbox-${week}`;
        
        const checkboxId = `week${week}`;
        
        checkboxItem.innerHTML = `
            <input type="checkbox" id="${checkboxId}" class="week-checkbox" 
                   data-week="${week}" 
                   ${selectedWeeks.includes(week) ? 'checked' : ''}>
            <label for="${checkboxId}" class="week-checkbox-label">
                <span class="week-number">${weekData.name}</span>
                <span class="week-dates">${formatDateForDisplay(weekData.startDate)} - ${formatDateForDisplay(weekData.endDate)}</span>
                <span class="week-days">${weekData.days} أيام دراسية</span>
            </label>
        `;
        
        // إضافة حدث التغيير لمربع الاختيار
        const checkbox = checkboxItem.querySelector('input[type="checkbox"]');
        checkbox.addEventListener('change', function() {
            updateWeekSelection(week, this.checked);
        });
        
        container.appendChild(checkboxItem);
    }
    
    updateSelectedWeeksDisplay();
}

// ======== دوال إدارة الدفعات ========

// تعيين وضع الاختيار
function setSelectionMode(mode) {
    selectionMode = mode;
    
    // تحديث أزرار الوضع
    document.getElementById('modeIndividual').classList.remove('active');
    document.getElementById('modeBatch').classList.remove('active');
    document.getElementById(`mode${mode.charAt(0).toUpperCase() + mode.slice(1)}`).classList.add('active');
    
    // إظهار أو إخفاء أداة اختيار النطاق
    const batchRangeSelector = document.getElementById('batchRangeSelector');
    if (mode === 'batch') {
        batchRangeSelector.style.display = 'block';
        populateBatchWeekOptions();
    } else {
        batchRangeSelector.style.display = 'none';
    }
    
    // تحديث عرض الدفعات
    updateSelectedBatchesDisplay();
}

// ملء خيارات الأسابيع للدفعات
function populateBatchWeekOptions() {
    const startSelect = document.getElementById('batchStartWeek');
    const endSelect = document.getElementById('batchEndWeek');
    
    startSelect.innerHTML = '';
    endSelect.innerHTML = '';
    
    for (let week = 1; week <= 19; week++) {
        const weekData = studyWeeks[week];
        const optionStart = document.createElement('option');
        optionStart.value = week;
        optionStart.textContent = `الأسبوع ${week}`;
        
        const optionEnd = document.createElement('option');
        optionEnd.value = week;
        optionEnd.textContent = `الأسبوع ${week}`;
        
        startSelect.appendChild(optionStart);
        endSelect.appendChild(optionEnd);
    }
    
    // تعيين القيم الافتراضية
    startSelect.value = 1;
    endSelect.value = 19;
}

// إضافة نطاق دفعة
function addBatchRange() {
    const startWeek = parseInt(document.getElementById('batchStartWeek').value);
    const endWeek = parseInt(document.getElementById('batchEndWeek').value);
    
    if (startWeek > endWeek) {
        alert("⚠️ أسبوع البداية يجب أن يكون قبل أسبوع النهاية");
        return;
    }
    
    // إنشاء دفعة جديدة
    const batch = {
        id: Date.now(),
        start: startWeek,
        end: endWeek,
        weeks: []
    };
    
    // إضافة الأسابيع إلى الدفعة
    for (let week = startWeek; week <= endWeek; week++) {
        batch.weeks.push(week);
        
        // إضافة الأسبوع إلى المحدد إذا لم يكن موجوداً
        if (!selectedWeeks.includes(week)) {
            selectedWeeks.push(week);
        }
    }
    
    // إضافة الدفعة إلى القائمة
    selectedBatches.push(batch);
    
    // تحديث العرض
    updateSelectedWeeksDisplay();
    updateWeekButtons();
    updateSelectedBatchesDisplay();
    saveSelectedWeeks();
    
    alert(`✅ تمت إضافة دفعة جديدة: الأسابيع من ${startWeek} إلى ${endWeek}`);
}

// تحديث عرض الدفعات المحددة
function updateSelectedBatchesDisplay() {
    const displayElement = document.getElementById('selectedBatchesDisplay');
    const textElement = document.getElementById('selectedBatchesText');
    
    if (selectedBatches.length === 0) {
        displayElement.style.display = 'none';
    } else {
        displayElement.style.display = 'block';
        
        const batchDescriptions = selectedBatches.map(batch => 
            `الأسابيع ${batch.start}-${batch.end} (${batch.weeks.length} أسبوع)`
        ).join('، ');
        
        textElement.textContent = batchDescriptions;
    }
}

// اختيار دفعة مسبقة التحديد
function selectBatch(batchType) {
    let startWeek, endWeek;
    
    switch(batchType) {
        case 'first_half':
            startWeek = 1;
            endWeek = 9;
            break;
        case 'second_half':
            startWeek = 10;
            endWeek = 19;
            break;
        case 'month1':
            startWeek = 1;
            endWeek = 4;
            break;
        case 'month2':
            startWeek = 5;
            endWeek = 8;
            break;
        case 'month3':
            startWeek = 9;
            endWeek = 12;
            break;
        case 'month4':
            startWeek = 13;
            endWeek = 16;
            break;
        case 'month5':
            startWeek = 17;
            endWeek = 19;
            break;
        default:
            return;
    }
    
    // تعيين القيم في النموذج
    document.getElementById('batchStartWeek').value = startWeek;
    document.getElementById('batchEndWeek').value = endWeek;
    
    // إضافة الدفعة
    addBatchRange();
}

// مسح اختيار الدفعات
function clearBatchSelection() {
    selectedBatches = [];
    updateSelectedBatchesDisplay();
}

// إنشاء أزرار الأسابيع (19 دفعة)
function createWeekButtons() {
    const container = document.getElementById('weekButtonsContainer');
    container.innerHTML = '';
    
    for (let week = 1; week <= 19; week++) {
        const weekData = studyWeeks[week];
        const button = document.createElement('button');
        button.className = 'week-button';
        button.id = `week-button-${week}`;
        
        const weekNumber = document.createElement('div');
        weekNumber.className = 'week-number';
        weekNumber.textContent = `الأسبوع ${week}`;
        
        const weekRange = document.createElement('div');
        weekRange.className = 'week-range';
        weekRange.textContent = formatDateForDisplay(weekData.startDate);
        
        button.appendChild(weekNumber);
        button.appendChild(weekRange);
        
        // تلوين الزر إذا كان الأسبوع محدداً
        if (selectedWeeks.includes(week)) {
            button.classList.add('selected');
        }
        
        // إضافة حدث النقر
        button.addEventListener('click', function() {
            toggleWeekSelection(week);
        });
        
        container.appendChild(button);
    }
}

// تنسيق التاريخ للعرض
function formatDateForDisplay(dateStr) {
    const parts = dateStr.split('/');
    return `${parts[1]}/${parts[2]}`;
}

// تحديث اختيار الأسبوع
function updateWeekSelection(week, isChecked) {
    if (isChecked) {
        if (!selectedWeeks.includes(week)) {
            selectedWeeks.push(week);
        }
    } else {
        const index = selectedWeeks.indexOf(week);
        if (index !== -1) {
            selectedWeeks.splice(index, 1);
        }
    }
    
    // ترتيب الأسابيع تصاعدياً
    selectedWeeks.sort((a, b) => a - b);
    
    updateSelectedWeeksDisplay();
    updateWeekButtons();
    saveSelectedWeeks();
}

// تحديث أزرار الأسابيع
function updateWeekButtons() {
    for (let week = 1; week <= 19; week++) {
        const button = document.getElementById(`week-button-${week}`);
        if (button) {
            if (selectedWeeks.includes(week)) {
                button.classList.add('selected');
            } else {
                button.classList.remove('selected');
            }
        }
    }
}

// تبديل اختيار الأسبوع
function toggleWeekSelection(week) {
    if (selectionMode === 'individual') {
        // السلوك الأصلي للاختيار الفردي
        const isSelected = selectedWeeks.includes(week);
        
        if (isSelected) {
            const index = selectedWeeks.indexOf(week);
            if (index !== -1) {
                selectedWeeks.splice(index, 1);
            }
        } else {
            selectedWeeks.push(week);
        }
        
        // تحديث واجهة المستخدم
        updateSelectedWeeksDisplay();
        updateWeekButtons();
        saveSelectedWeeks();
    } else {
        // في وضع الدفعات، نعرض رسالة توجيهية
        alert('💡 في وضع الدفعات، استخدم أداة "تحديد نطاق دفعة" لإضافة مجموعة أسابيع');
    }
}

// تحديث عرض الأسابيع المحددة
function updateSelectedWeeksDisplay() {
    const displayElement = document.getElementById('selectedWeeksText');
    const countElement = document.getElementById('selectedWeeksCount');
    
    if (selectedWeeks.length === 0) {
        displayElement.textContent = "لا توجد أسابيع محددة";
        countElement.textContent = "0 أسبوع | 0 يوم";
    } else {
        const weekNames = selectedWeeks.map(w => studyWeeks[w].name).join('، ');
        
        // حساب عدد الأيام
        let totalDays = 0;
        selectedWeeks.forEach(weekNum => {
            totalDays += studyWeeks[weekNum].days;
        });
        
        displayElement.textContent = `${weekNames}`;
        countElement.textContent = `${selectedWeeks.length} أسبوع | ${totalDays} يوم`;
    }
    
    // تحديث حالة مربعات الاختيار
    for (let week = 1; week <= 19; week++) {
        const checkbox = document.getElementById(`week${week}`);
        if (checkbox) {
            checkbox.checked = selectedWeeks.includes(week);
        }
    }
}

// حفظ الأسابيع المحددة
function saveSelectedWeeks() {
    localStorage.setItem('teacherTracker_selectedWeeks', JSON.stringify(selectedWeeks));
}

// تحديد جميع الأسابيع
function selectAllWeeks() {
    selectedWeeks = [];
    for (let week = 1; week <= 19; week++) {
        selectedWeeks.push(week);
    }
    
    // إنشاء دفعة واحدة لجميع الأسابيع
    selectedBatches = [{
        id: Date.now(),
        start: 1,
        end: 19,
        weeks: selectedWeeks
    }];
    
    updateSelectedWeeksDisplay();
    updateWeekButtons();
    updateSelectedBatchesDisplay();
    saveSelectedWeeks();
    alert(`تم تحديد جميع أسابيع الترم الأول (${selectedWeeks.length} أسبوع)`);
}

// مسح جميع الأسابيع
function clearSelectedWeeks() {
    selectedWeeks = [];
    selectedBatches = [];
    updateSelectedWeeksDisplay();
    updateWeekButtons();
    updateSelectedBatchesDisplay();
    saveSelectedWeeks();
    alert("تم مسح جميع الأسابيع المحددة");
}

// تحديد أسابيع الترم الأول
function selectFirstSemesterWeeks() {
    selectAllWeeks();
}

// تحديد نطاق من الأسابيع
function selectWeeksRange(start, end) {
    for (let week = start; week <= end; week++) {
        if (!selectedWeeks.includes(week)) {
            selectedWeeks.push(week);
        }
    }
    
    // ترتيب الأسابيع تصاعدياً
    selectedWeeks.sort((a, b) => a - b);
    
    updateSelectedWeeksDisplay();
    updateWeekButtons();
    saveSelectedWeeks();
    alert(`تم إضافة الأسابيع ${start}-${end} إلى المحددة`);
}

// تحميل بيانات التحضير المحفوظة للفترة
function loadPeriodAttendanceData() {
    const savedData = localStorage.getItem('teacherTracker_periodAttendanceData');
    if (savedData) {
        periodAttendanceData = JSON.parse(savedData);
    }
}

// حفظ بيانات التحضير للفترة
function savePeriodAttendanceData() {
    localStorage.setItem('teacherTracker_periodAttendanceData', JSON.stringify(periodAttendanceData));
}

// تحضير عشوائي للأسابيع المحددة
function randomAttendanceForSelectedWeeks() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    if (selectedWeeks.length === 0) {
        alert("⚠️ لم تحدد أي أسابيع!\n\nالرجاء اختيار أسبوع أو أكثر من القائمة");
        return;
    }
    
    const confirmAction = confirm(`هل تريد إنشاء تحضير عشوائي للأسابيع المحددة؟\n\nعدد الأسابيع: ${selectedWeeks.length}\n\nالطلاب المميزون: كل الخيارات ✔\nالطلاب العاديون: 3 ✔ فقط`);
    if (!confirmAction) return;
    
    // حفظ بيانات التحضير العشوائي للأسابيع المحددة
    selectedWeeks.forEach(weekNum => {
        if (!periodAttendanceData[weekNum]) {
            periodAttendanceData[weekNum] = {};
        }
        
        // إنشاء تحضير عشوائي لكل صف
        for (const className in studentsData) {
            if (!periodAttendanceData[weekNum][className]) {
                periodAttendanceData[weekNum][className] = {};
            }
            
            studentsData[className].forEach((student, index) => {
                const isStarred = isStudentStarred(className, student);
                
                // إنشاء بيانات الحضور العشوائية
                const attendanceData = [];
                for (let i = 0; i < 5; i++) {
                    if (isStarred) {
                        // الطلاب المميزون: كل الخيارات ✓
                        attendanceData.push("✔");
                    } else {
                        // الطلاب العاديون: 3 ✓ فقط بشكل عشوائي
                        const seed = (index + 1) * weekNum;
                        const randomPattern = [
                            (seed % 5) < 3,
                            ((seed + 1) % 5) < 3,
                            ((seed + 2) % 5) < 3,
                            ((seed + 3) % 5) < 3,
                            ((seed + 4) % 5) < 3
                        ];
                        
                        attendanceData.push(randomPattern[i] ? "✔" : "✖");
                    }
                }
                
                periodAttendanceData[weekNum][className][student] = attendanceData;
            });
        }
    });
    
    savePeriodAttendanceData();
    
    alert(`✅ تم إنشاء التحضير العشوائي لـ ${selectedWeeks.length} أسبوع!\n\nيمكنك تصدير التقرير باستخدام زر 'تصدير الأسابيع المحددة'`);
}

// ======== تصدير الأسابيع المحددة إلى Excel ========

// عرض/إخفاء مؤشر التحميل
function showLoading(show) {
    const spinner = document.getElementById('loadingSpinner');
    if (spinner) {
        spinner.style.display = show ? 'block' : 'none';
    }
}

// تصدير الأسابيع المحددة إلى Excel (ملف واحد)
function exportSelectedWeeks() {
    if (selectedWeeks.length === 0) {
        alert("⚠️ لم تحدد أي أسابيع!\n\nالرجاء اختيار أسبوع أو أكثر أولاً");
        return;
    }

    showLoading(true);

    // محاكاة المعالجة
    setTimeout(() => {
        // استخدام اسم المعلم المحفوظ
        const teacherDisplay = teacherName ? `المعلم: ${teacherName}` : "";
        
        let tablesHTML = `<h2>تقرير التحضير للأسابيع المحددة</h2>`;
        tablesHTML += `<h3>${teacherDisplay} - المادة: اللغة الإنجليزية</h3>`;
        tablesHTML += `<h3>${document.getElementById('currentSemesterInfo').textContent}</h3>`;
        tablesHTML += `<h3>المدرسة: سعيد بن العاص المتوسطة</h3>`;
        tablesHTML += `<h3>تاريخ التصدير: ${new Date().toLocaleDateString('ar-SA')}</h3>`;

        const weekNames = selectedWeeks.map(w => studyWeeks[w].name).join('، ');
        tablesHTML += `<h3>الأسابيع: ${weekNames} (${selectedWeeks.length} أسابيع)</h3>`;

        let totalWeeks = 0;
        let totalDays = 0;
        let totalStudentsAll = 0;
        let totalPresentAll = 0;
        let totalAbsentAll = 0;
        let totalStarredAll = 0;

        // إضافة جداول لكل أسبوع
        selectedWeeks.forEach(weekNum => {
            totalWeeks++;
            const weekData = studyWeeks[weekNum];
            totalDays += weekData.days;

            tablesHTML += `<h3 style="background:#e8f5e9; padding:10px; margin-top:20px;">${weekData.name}</h3>`;
            tablesHTML += `<p style="text-align:center;">${weekData.startDate} - ${weekData.endDate} (${weekData.days} أيام)</p>`;

            // إضافة جداول لكل صف
            for (const className in studentsData) {
                const classSize = studentsData[className].length;
                totalStudentsAll += classSize;

                tablesHTML += `<h5>الصف ${className} (${classSize} طالب)</h5>`;
                tablesHTML += `<table border="1" cellpadding="5" cellspacing="0" style="width:100%; border-collapse:collapse; margin-bottom:15px;">`;
                tablesHTML += `<thead><tr>
                    <th width="5%">م</th>
                    <th>الاسم</th>
                    <th width="8%">الحضور</th>
                    <th width="8%">الواجبات</th>
                    <th width="8%">المشروعات</th>
                    <th width="8%">تطبيقات وأنشطة</th>
                    <th width="8%">مشاركة</th>
                    <th width="8%">⭐</th>
                </tr></thead><tbody>`;

                studentsData[className].forEach((student, index) => {
                    const isStarred = isStudentStarred(className, student);
                    if (isStarred) totalStarredAll++;

                    tablesHTML += `<tr>`;
                    tablesHTML += `<td>${index + 1}</td>`;
                    tablesHTML += `<td>${student}</td>`;

                    // استخدام البيانات المحفوظة أو إنشاء بيانات عشوائية
                    let attendanceData = [];
                    
                    if (periodAttendanceData[weekNum] && 
                        periodAttendanceData[weekNum][className] && 
                        periodAttendanceData[weekNum][className][student]) {
                        // استخدام البيانات المحفوظة
                        attendanceData = periodAttendanceData[weekNum][className][student];
                    } else {
                        // إنشاء بيانات عشوائية
                        for (let i = 0; i < 5; i++) {
                            if (isStarred) {
                                // الطلاب المميزون: كل الخيارات ✓
                                attendanceData.push("✔");
                            } else {
                                // الطلاب العاديون: 3 ✓ فقط بشكل عشوائي
                                const seed = (index + 1) * weekNum;
                                const randomPattern = [
                                    (seed % 5) < 3,
                                    ((seed + 1) % 5) < 3,
                                    ((seed + 2) % 5) < 3,
                                    ((seed + 3) % 5) < 3,
                                    ((seed + 4) % 5) < 3
                                ];
                                
                                attendanceData.push(randomPattern[i] ? "✔" : "✖");
                            }
                        }
                    }

                    // إضافة بيانات الحضور إلى الجدول
                    attendanceData.forEach((value, i) => {
                        let bgColor = value === "✔" ? "#e8f5e9" : "#ffebee";
                        let color = value === "✔" ? "#059669" : "#dc2626";
                        
                        if (value === "✔") totalPresentAll++;
                        else totalAbsentAll++;
                        
                        tablesHTML += `<td style="background-color:${bgColor}; color:${color}; font-weight:bold;">${value}</td>`;
                    });

                    tablesHTML += `<td>${isStarred ? '⭐' : ''}</td>`;
                    tablesHTML += `</tr>`;
                });

                tablesHTML += `</tbody></table>`;
            }
        });

        // إضافة ملخص شامل
        tablesHTML += `<h3 style="background:#e0f7fa; padding:10px; margin-top:20px;">ملخص شامل للأسابيع المحددة</h3>`;
        tablesHTML += `<div style="padding:15px; background:#fff8e1; border-radius:5px; margin-bottom:20px;">
            <strong>إجمالي جميع الأسابيع المحددة:</strong><br>
            - عدد الأسابيع: ${totalWeeks} أسبوع<br>
            - عدد الأيام: ${totalDays} يوم<br>
            - إجمالي الطلاب: ${totalStudentsAll * selectedWeeks.length} حالة<br>
            - إجمالي الحضور (✔): ${totalPresentAll} حالة<br>
            - إجمالي الغياب (✖): ${totalAbsentAll} حالة<br>
            - إجمالي المتميزين: ${totalStarredAll} طالب<br>
            - نسبة الحضور: ${(totalPresentAll + totalAbsentAll) > 0 ? ((totalPresentAll / (totalPresentAll + totalAbsentAll)) * 100).toFixed(1) : 0}%
        </div>`;

        // إنشاء ملف Excel
        let uri = 'data:application/vnd.ms-excel;base64,';
        let template = `<html xmlns:o="urn:schemas-microsoft-com:office:office" 
                       xmlns:x="urn:schemas-microsoft-com:office:excel" 
                       xmlns="http://www.w3.org/TR/REC-html40">
                       <head>
                       <meta charset="UTF-8">
                       <!--[if gte mso 9]>
                       <xml>
                       <x:ExcelWorkbook>
                       <x:ExcelWorksheets>
                       <x:ExcelWorksheet>
                       <x:Name>تقرير الأسابيع</x:Name>
                       <x:WorksheetOptions><x:DisplayGridlines/></x:WorksheetOptions>
                       </x:ExcelWorksheet>
                       </x:ExcelWorksheets>
                       </x:ExcelWorkbook>
                       </xml>
                       <![endif]-->
                       </head>
                       <body dir="rtl">${tablesHTML}</body></html>`;

        let link = document.createElement("a");
        link.href = uri + btoa(unescape(encodeURIComponent(template)));
        const weekRange = selectedWeeks.length === 1 ? 
            `الأسبوع_${selectedWeeks[0]}` : 
            `الأسابيع_${selectedWeeks[0]}_إلى_${selectedWeeks[selectedWeeks.length - 1]}`;
        link.download = `تقرير_${weekRange}.xls`;
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);

        showLoading(false);

        alert(`✅ تم تصدير التقرير بنجاح!\n\n📊 يحتوي على:\n- ${selectedWeeks.length} أسبوع\n- ${totalDays} يوم\n- ${totalStudentsAll * selectedWeeks.length} حالة حضور`);
    }, 1000);
}

// تصدير كل أسبوع في ملف منفصل
function exportEachWeekSeparately() {
    if (selectedWeeks.length === 0) {
        alert("⚠️ لم تحدد أي أسابيع!\n\nالرجاء اختيار أسبوع أو أكثر أولاً");
        return;
    }

    showLoading(true);

    // محاكاة المعالجة
    setTimeout(() => {
        selectedWeeks.forEach((weekNum, index) => {
            // إنشاء ملف منفصل لكل أسبوع بعد فترة زمنية صغيرة
            setTimeout(() => {
                const weekData = studyWeeks[weekNum];
                const teacherDisplay = teacherName ? `المعلم: ${teacherName}` : "";
                
                let tablesHTML = `<h2>تقرير التحضير - ${weekData.name}</h2>`;
                tablesHTML += `<h3>${teacherDisplay} - المادة: اللغة الإنجليزية</h3>`;
                tablesHTML += `<h3>${document.getElementById('currentSemesterInfo').textContent}</h3>`;
                tablesHTML += `<h3>المدرسة: سعيد بن العاص المتوسطة</h3>`;
                tablesHTML += `<h3>تاريخ التصدير: ${new Date().toLocaleDateString('ar-SA')}</h3>`;
                tablesHTML += `<h3>${weekData.startDate} - ${weekData.endDate} (${weekData.days} أيام)</h3>`;

                let totalPresent = 0;
                let totalAbsent = 0;
                let totalStarred = 0;

                // إضافة جداول لكل صف
                for (const className in studentsData) {
                    const classSize = studentsData[className].length;

                    tablesHTML += `<h4>الصف ${className} (${classSize} طالب)</h4>`;
                    tablesHTML += `<table border="1" cellpadding="5" cellspacing="0" style="width:100%; border-collapse:collapse; margin-bottom:15px;">`;
                    tablesHTML += `<thead><tr>
                        <th width="5%">م</th>
                        <th>الاسم</th>
                        <th width="8%">الحضور</th>
                        <th width="8%">الواجبات</th>
                        <th width="8%">المشروعات</th>
                        <th width="8%">تطبيقات وأنشطة</th>
                        <th width="8%">مشاركة</th>
                        <th width="8%">⭐</th>
                    </tr></thead><tbody>`;

                    studentsData[className].forEach((student, idx) => {
                        const isStarred = isStudentStarred(className, student);
                        if (isStarred) totalStarred++;

                        tablesHTML += `<tr>`;
                        tablesHTML += `<td>${idx + 1}</td>`;
                        tablesHTML += `<td>${student}</td>`;

                        // استخدام البيانات المحفوظة أو إنشاء بيانات عشوائية
                        let attendanceData = [];
                        
                        if (periodAttendanceData[weekNum] && 
                            periodAttendanceData[weekNum][className] && 
                            periodAttendanceData[weekNum][className][student]) {
                            // استخدام البيانات المحفوظة
                            attendanceData = periodAttendanceData[weekNum][className][student];
                        } else {
                            // إنشاء بيانات عشوائية
                            for (let i = 0; i < 5; i++) {
                                if (isStarred) {
                                    // الطلاب المميزون: كل الخيارات ✓
                                    attendanceData.push("✔");
                                } else {
                                    // الطلاب العاديون: 3 ✓ فقط بشكل عشوائي
                                    const seed = (idx + 1) * weekNum;
                                    const randomPattern = [
                                        (seed % 5) < 3,
                                        ((seed + 1) % 5) < 3,
                                        ((seed + 2) % 5) < 3,
                                        ((seed + 3) % 5) < 3,
                                        ((seed + 4) % 5) < 3
                                    ];
                                    
                                    attendanceData.push(randomPattern[i] ? "✔" : "✖");
                                }
                            }
                        }

                        // إضافة بيانات الحضور إلى الجدول
                        attendanceData.forEach((value, i) => {
                            let bgColor = value === "✔" ? "#e8f5e9" : "#ffebee";
                            let color = value === "✔" ? "#059669" : "#dc2626";
                            
                            if (value === "✔") totalPresent++;
                            else totalAbsent++;
                            
                            tablesHTML += `<td style="background-color:${bgColor}; color:${color}; font-weight:bold;">${value}</td>`;
                        });

                        tablesHTML += `<td>${isStarred ? '⭐' : ''}</td>`;
                        tablesHTML += `</tr>`;
                    });

                    tablesHTML += `</tbody></table>`;
                }

                // إضافة ملخص للأسبوع
                tablesHTML += `<h4 style="background:#e0f7fa; padding:10px;">ملخص الأسبوع</h4>`;
                tablesHTML += `<div style="padding:15px; background:#fff8e1; border-radius:5px; margin-bottom:20px;">
                    <strong>إجمالي الأسبوع:</strong><br>
                    - عدد الأيام: ${weekData.days} يوم<br>
                    - إجمالي الطلاب: ${Object.keys(studentsData).reduce((sum, className) => sum + studentsData[className].length, 0)} طالب<br>
                    - إجمالي الحضور (✔): ${totalPresent} حالة<br>
                    - إجمالي الغياب (✖): ${totalAbsent} حالة<br>
                    - إجمالي المتميزين: ${totalStarred} طالب<br>
                    - نسبة الحضور: ${(totalPresent + totalAbsent) > 0 ? ((totalPresent / (totalPresent + totalAbsent)) * 100).toFixed(1) : 0}%
                </div>`;

                // إنشاء ملف Excel
                let uri = 'data:application/vnd.ms-excel;base64,';
                let template = `<html xmlns:o="urn:schemas-microsoft-com:office:office" 
                           xmlns:x="urn:schemas-microsoft-com:office:excel" 
                           xmlns="http://www.w3.org/TR/REC-html40">
                           <head>
                           <meta charset="UTF-8">
                           <!--[if gte mso 9]>
                           <xml>
                           <x:ExcelWorkbook>
                           <x:ExcelWorksheets>
                           <x:ExcelWorksheet>
                           <x:Name>${weekData.name}</x:Name>
                           <x:WorksheetOptions><x:DisplayGridlines/></x:WorksheetOptions>
                           </x:ExcelWorksheet>
                           </x:ExcelWorksheets>
                           </x:ExcelWorkbook>
                           </xml>
                           <![endif]-->
                           </head>
                           <body dir="rtl">${tablesHTML}</body></html>`;

                let link = document.createElement("a");
                link.href = uri + btoa(unescape(encodeURIComponent(template)));
                link.download = `تقرير_${weekData.name}.xls`;
                document.body.appendChild(link);
                link.click();
                document.body.removeChild(link);

            }, index * 500); // تأخير 500 مللي ثانية بين كل ملف
        });

        showLoading(false);
        
        setTimeout(() => {
            alert(`✅ تم تصدير ${selectedWeeks.length} ملف Excel منفصل بنجاح!\n\n📁 كل ملف يحتوي على أسبوع واحد`);
        }, selectedWeeks.length * 500 + 500);
    }, 1000);
}

// تصدير جميع أسابيع الترم الأول
function exportAllWeeks() {
    // تحديد جميع أسابيع الترم الأول
    const allWeeks = [];
    for (let week = 1; week <= 19; week++) {
        allWeeks.push(week);
    }
    
    // حفظ الأسابيع الحالية مؤقتاً
    const tempWeeks = [...selectedWeeks];
    selectedWeeks = allWeeks;
    updateSelectedWeeksDisplay();
    updateWeekButtons();
    
    exportSelectedWeeks();
    
    // استعادة الأسابيع الأصلية
    selectedWeeks = tempWeeks;
    updateSelectedWeeksDisplay();
    updateWeekButtons();
}

// ======== إدارة الطلاب ========

// تحديث قائمة الطلاب في القائمة المنسدلة
function refreshStudentList() {
    const studentSelect = document.getElementById('studentToMove');
    studentSelect.innerHTML = '<option value="">-- اختر الطالب --</option>';
    
    // جمع جميع الطلاب من جميع الصفوف
    let allStudents = [];
    
    for (const className in studentsData) {
        studentsData[className].forEach((studentName, index) => {
            allStudents.push({
                name: studentName,
                class: className,
                index: index
            });
        });
    }
    
    // إضافة الطلاب إلى القائمة
    allStudents.forEach((student, index) => {
        const option = document.createElement('option');
        option.value = `${student.class}_${student.index}`;
        option.textContent = `${student.name} (${student.class})`;
        studentSelect.appendChild(option);
    });
}

// تحديث معلومات نقل الطالب
function updateStudentMoveInfo() {
    const studentSelect = document.getElementById('studentToMove');
    const currentClassInput = document.getElementById('currentStudentClass');
    
    if (studentSelect.value === "") {
        currentClassInput.value = "";
        return;
    }
    
    const [className, _] = studentSelect.value.split('_');
    currentClassInput.value = className;
}

// إضافة طالب جديد
function addStudent() {
    const studentName = document.getElementById('newStudentName').value.trim();
    const studentClass = document.getElementById('newStudentClass').value;
    
    if (!studentName) {
        alert("⚠️ الرجاء إدخال اسم الطالب");
        return;
    }
    
    if (!studentsData[studentClass]) {
        alert("⚠️ الصف المحدد غير صحيح");
        return;
    }
    
    // التحقق من عدم وجود الطالب مسبقاً
    for (const className in studentsData) {
        if (studentsData[className].includes(studentName)) {
            alert(`⚠️ الطالب "${studentName}" موجود بالفعل في الصف ${className}`);
            return;
        }
    }
    
    // إضافة الطالب
    studentsData[studentClass].push(studentName);
    
    // تحديث العرض
    fillClassTable(studentClass);
    updateStudentCount();
    refreshStudentList();
    
    // تحديث عنوان الصف
    document.querySelector(`#class-${studentClass} .class-header`).textContent = 
        `الصف ${studentClass} - ${studentsData[studentClass].length} طالب`;
    
    // مسح النموذج
    document.getElementById('newStudentName').value = "";
    
    alert(`✅ تمت إضافة الطالب "${studentName}" إلى الصف ${studentClass} بنجاح`);
}

// مسح نموذج إضافة الطالب
function clearStudentForm() {
    document.getElementById('newStudentName').value = "";
    document.getElementById('newStudentClass').value = "3-1";
}

// نقل طالب بين الصفوف
function moveStudent() {
    const studentSelect = document.getElementById('studentToMove');
    const targetClass = document.getElementById('targetClass').value;
    
    if (studentSelect.value === "") {
        alert("⚠️ الرجاء اختيار الطالب");
        return;
    }
    
    const [currentClass, studentIndex] = studentSelect.value.split('_');
    const studentName = studentsData[currentClass][parseInt(studentIndex)];
    
    if (currentClass === targetClass) {
        alert("⚠️ الطالب موجود بالفعل في هذا الصف");
        return;
    }
    
    // التحقق من وجود الطالب في الصف الهدف
    if (studentsData[targetClass].includes(studentName)) {
        alert(`⚠️ الطالب "${studentName}" موجود بالفعل في الصف ${targetClass}`);
        return;
    }
    
    // نقل الطالب
    const currentClassIndex = studentsData[currentClass].indexOf(studentName);
    if (currentClassIndex !== -1) {
        // إزالة من الصف الحالي
        studentsData[currentClass].splice(currentClassIndex, 1);
        
        // إضافة إلى الصف الهدف
        studentsData[targetClass].push(studentName);
        
        // تحديث النجوم إذا كان مميزاً
        if (starredStudents[currentClass] && starredStudents[currentClass].includes(studentName)) {
            // إزالة من النجوم القديمة
            const starIndex = starredStudents[currentClass].indexOf(studentName);
            starredStudents[currentClass].splice(starIndex, 1);
            
            // إضافة إلى النجوم الجديدة
            if (!starredStudents[targetClass]) {
                starredStudents[targetClass] = [];
            }
            starredStudents[targetClass].push(studentName);
            saveStarredStudents();
        }
        
        // تحديث العرض
        fillClassTable(currentClass);
        fillClassTable(targetClass);
        updateStudentCount();
        refreshStudentList();
        
        // تحديث عناوين الصفوف
        document.querySelector(`#class-${currentClass} .class-header`).textContent = 
            `الصف ${currentClass} - ${studentsData[currentClass].length} طالب`;
        document.querySelector(`#class-${targetClass} .class-header`).textContent = 
            `الصف ${targetClass} - ${studentsData[targetClass].length} طالب`;
        
        // مسح النموذج
        studentSelect.value = "";
        document.getElementById('currentStudentClass').value = "";
        
        alert(`✅ تم نقل الطالب "${studentName}" من الصف ${currentClass} إلى الصف ${targetClass} بنجاح`);
    } else {
        alert("⚠️ لم يتم العثور على الطالب في الصف الحالي");
    }
}

// تهيئة الصفحة عند التحميل
window.onload = initPage;
</script>
</body>
</html>
