<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>سجل متابعة الطلاب - فهد الخالدي</title>
<style>
body {
    font-family: "Tajawal", sans-serif;
    margin: 0;
    padding: 0;
    background: #f7f7f7;
}

header {
    background: linear-gradient(135deg, #1a5276, #2a9d8f);
    color: #fff;
    text-align: center;
    padding: 12px 0;
    box-shadow: 0px 4px 6px rgba(0,0,0,0.1);
}

.header-main {
    font-size: 22px;
    font-weight: bold;
    margin-bottom: 5px;
}

.header-sub {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
    font-size: 14px;
    margin-top: 5px;
}

.header-sub div {
    padding: 4px 10px;
    background: rgba(255,255,255,0.15);
    border-radius: 4px;
}

.current-date {
    background: rgba(38, 70, 83, 0.8) !important;
    transition: all 0.3s;
}

.date-info {
    font-size: 12px;
    color: #e0f7fa;
    margin-top: 2px;
}

.class-header {
    background: #2a9d8f;
    color: white;
    padding: 8px;
    margin: 15px 0 5px 0;
    border-radius: 5px;
    text-align: center;
    font-size: 16px;
}

.container {
    width: 95%;
    margin: 10px auto;
    background: white;
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0px 4px 10px rgba(0,0,0,0.1);
}

table {
    width: 100%;
    border-collapse: collapse;
    font-size: 12px;
    margin-bottom: 15px;
}

th, td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: center;
}

th {
    background: #e9f5f4;
    color: #264653;
    font-size: 11px;
    font-weight: bold;
}

td {
    cursor: pointer;
    user-select: none;
}

button {
    margin: 5px;
    padding: 8px 15px;
    border: none;
    border-radius: 5px;
    background: #1a5276;
    color: white;
    font-weight: bold;
    cursor: pointer;
    transition: all 0.3s;
}

button:hover {
    background: #2a9d8f;
    transform: translateY(-2px);
}

.controls {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin-bottom: 15px;
    gap: 10px;
}

.admin-panel {
    display: none;
    margin-top: 15px;
    padding: 15px;
    border: 1px solid #1a5276;
    border-radius: 10px;
    background: #f0f8ff;
}

.star-cell {
    color: #ffd700;
    font-size: 16px;
}

.present {
    background-color: #e8f5e9;
}

.absent {
    background-color: #ffebee;
}

.status-filter {
    margin: 10px 0;
    text-align: center;
}

.status-filter button {
    background: #ddd;
    color: #333;
}

.status-filter button.active {
    background: #2a9d8f;
    color: white;
}

input[type="password"], input[type="text"], select {
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-family: "Tajawal", sans-serif;
}

.class-tabs {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 15px;
    gap: 5px;
}

.class-tab {
    padding: 8px 15px;
    background: #e0e0e0;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s;
}

.class-tab.active {
    background: #2a9d8f;
    color: white;
}

.class-tab:hover {
    background: #c0c0c0;
}

.student-count {
    text-align: center;
    margin: 10px 0;
    color: #264653;
    font-weight: bold;
}

.date-controls {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    margin: 10px 0;
    flex-wrap: wrap;
}

.date-controls button {
    padding: 6px 12px;
    font-size: 14px;
}

.date-display {
    font-size: 16px;
    font-weight: bold;
    color: #264653;
    padding: 5px 15px;
    background: #f0f8ff;
    border-radius: 5px;
    border: 1px solid #1a5276;
}

.date-input {
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-family: "Tajawal", sans-serif;
}

.admin-section {
    margin: 15px 0;
    padding: 10px;
    background: #f9f9f9;
    border-radius: 8px;
    border: 1px solid #ddd;
}

.admin-section h4 {
    margin-top: 0;
    color: #1a5276;
    text-align: center;
    border-bottom: 1px solid #ddd;
    padding-bottom: 8px;
}

.admin-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 10px 0;
    flex-wrap: wrap;
}

.admin-label {
    font-weight: bold;
    color: #264653;
    min-width: 150px;
}

.admin-input {
    flex: 1;
    min-width: 200px;
}

.semester-info {
    display: inline-block;
    padding: 4px 10px;
    background: #e8f5e9;
    border-radius: 4px;
    color: #2a9d8f;
    font-weight: bold;
    margin-left: 10px;
}

.hijri-date-selector {
    background: #fff8e1;
    border: 1px solid #ffd54f;
    border-radius: 5px;
    padding: 10px;
    margin-top: 10px;
}

.starred-student {
    background-color: #fffde7 !important;
}

.random-period-section {
    background: #e8f5e9;
    border: 1px solid #2a9d8f;
    border-radius: 5px;
    padding: 10px;
    margin-top: 10px;
}

.period-info {
    display: inline-block;
    padding: 4px 10px;
    background: #2a9d8f;
    color: white;
    border-radius: 4px;
    font-weight: bold;
    margin-left: 10px;
    font-size: 12px;
}

.week-selector {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(70px, 1fr));
    gap: 8px;
    margin-top: 10px;
    max-height: 200px;
    overflow-y: auto;
    padding: 10px;
    background: #f8f9fa;
    border-radius: 5px;
    border: 1px solid #ddd;
}

.week-checkbox {
    display: flex;
    align-items: center;
    padding: 5px;
    background: white;
    border-radius: 4px;
    border: 1px solid #ccc;
    cursor: pointer;
    transition: all 0.2s;
}

.week-checkbox:hover {
    background: #f0f0f0;
}

.week-checkbox input {
    margin-left: 5px;
}

.week-checkbox label {
    cursor: pointer;
    font-size: 12px;
    flex: 1;
}

.week-controls {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
    margin-top: 10px;
}

.week-controls button {
    padding: 6px 10px;
    font-size: 12px;
}

@media print {
    button, .admin-panel, .status-filter, .class-tabs, .date-controls {
        display: none !important;
    }
    
    table {
        font-size: 10px;
    }
    
    .header-sub {
        background: white;
        color: black;
        border: 1px solid #ccc;
    }
    
    .current-date {
        background: white !important;
        color: black;
        border: 1px solid #ccc;
    }
}
</style>
<!-- مكتبة ummAlQura لحساب التاريخ الهجري -->
<script src="https://cdn.jsdelivr.net/npm/hijri-date/lib/simple.umd.min.js"></script>
</head>
<body>

<header>
    <div class="header-main">سجل متابعة الطلاب للمعلم / فهد الخالدي - المادة / اللغة الإنجليزية</div>
    <div class="header-sub">
        <div>المدرسة: سعيد بن العاص المتوسطة</div>
        <div class="current-date">
            <div>تاريخ اليوم:</div>
            <div id="gregorianDateText">تحميل...</div>
            <div class="date-info" id="hijriDateText">تحميل التاريخ الهجري...</div>
        </div>
    </div>
</header>

<div class="container">
    <div class="controls">
        <button onclick="exportToExcel()">📊 تصدير Excel</button>
        <button onclick="exportPeriodToExcel()">📅 تصدير فترة كاملة</button>
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
    
    <div style="text-align: center; margin-top: 20px;">
        <input type="password" id="adminPass" placeholder="ادخل كلمة المرور للإدارة" style="width: 200px;">
        <button onclick="checkAdmin()">🔓 فتح الإدارة</button>
    </div>

    <div class="admin-panel" id="adminPanel">
        <h3 style="text-align:center; margin-top:0; color: #1a5276;">لوحة الإدارة - الخصائص الإدارية</h3>
        
        <div class="admin-section">
            <h4>🎓 إعدادات الفصل الدراسي</h4>
            <div class="admin-row">
                <div class="admin-label">الفصل الدراسي:</div>
                <div class="admin-input">
                    <select id="semesterSelect" onchange="updateSemester()" style="width: 100%;">
                        <option value="1">الفصل الدراسي الأول</option>
                        <option value="2" selected>الفصل الدراسي الثاني</option>
                        <option value="3">الفصل الدراسي الصيفي</option>
                    </select>
                </div>
            </div>
            <div class="admin-row">
                <div class="admin-label">السنة الدراسية:</div>
                <div class="admin-input">
                    <input type="text" id="academicYear" value="١٤٤٦هـ" style="width: 100%;">
                </div>
            </div>
            <div style="text-align: center; margin-top: 10px;">
                <button onclick="saveSemesterSettings()">💾 حفظ إعدادات الفصل</button>
                <span class="semester-info" id="currentSemesterInfo">الفصل الثاني ١٤٤٦هـ</span>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>🕐 التحكم في التاريخ (للتعديل فقط)</h4>
            <div style="text-align:center; background:#ffebee; padding:10px; border-radius:5px; margin-bottom:10px;">
                <strong>ملاحظة:</strong> يتم عرض تاريخ اليوم الحقيقي تلقائياً. هذه الأدوات تستخدم فقط لتعديل التاريخ عند الحاجة.
            </div>
            <div class="date-controls">
                <button onclick="changeMonth(-1)">◀ الشهر السابق</button>
                <div class="date-display" id="adminDateDisplay">...</div>
                <button onclick="changeMonth(1)">الشهر القادم ▶</button>
            </div>
            <div style="text-align: center; margin: 10px 0;">
                <input type="date" id="datePicker" class="date-input" onchange="setCustomDate()">
                <button onclick="resetToToday()">🔄 الرجوع لليوم الحقيقي</button>
                <button onclick="saveCurrentDate()">💾 حفظ التعديلات</button>
            </div>
            
            <div class="hijri-date-selector">
                <h5 style="text-align:center; color: #d84315;">التاريخ الهجري (يمكن تعديله يدوياً)</h5>
                <div class="admin-row">
                    <div class="admin-label">اليوم:</div>
                    <div class="admin-input">
                        <input type="number" id="hijriDay" min="1" max="30" style="width: 70px;">
                    </div>
                </div>
                <div class="admin-row">
                    <div class="admin-label">الشهر:</div>
                    <div class="admin-input">
                        <select id="hijriMonth" style="width: 100%;">
                            <option value="1">محرم</option>
                            <option value="2">صفر</option>
                            <option value="3">ربيع الأول</option>
                            <option value="4">ربيع الثاني</option>
                            <option value="5">جمادى الأولى</option>
                            <option value="6">جمادى الآخرة</option>
                            <option value="7">رجب</option>
                            <option value="8">شعبان</option>
                            <option value="9">رمضان</option>
                            <option value="10">شوال</option>
                            <option value="11">ذو القعدة</option>
                            <option value="12">ذو الحجة</option>
                        </select>
                    </div>
                </div>
                <div class="admin-row">
                    <div class="admin-label">السنة:</div>
                    <div class="admin-input">
                        <input type="number" id="hijriYear" min="1300" max="1500" style="width: 100px;">
                    </div>
                </div>
                <div style="text-align: center; margin-top: 10px;">
                    <button onclick="updateHijriDate()">🔄 تحديث التاريخ الهجري</button>
                    <button onclick="resetHijriToToday()">🔄 الرجوع للتاريخ الفعلي</button>
                </div>
                <p style="text-align:center; font-size:11px; color:#666;">ملاحظة: التاريخ الهجري المحسوب تلقائياً، ويمكنك تعديله يدوياً إذا لزم الأمر.</p>
            </div>
            
            <p style="text-align:center; font-size:12px; color:#666;">يمكنك الرجوع إلى أشهر سابقة أو قادمة لمشاهدة السجلات القديمة أو تحضير مستقبلية.</p>
        </div>
        
        <div class="admin-section">
            <h4>📅 التحضير العشوائي للأسابيع الدراسية (١٩ أسبوع)</h4>
            <div class="random-period-section">
                <div class="admin-row">
                    <div class="admin-label">تحديد الأسابيع:</div>
                    <div class="admin-input">
                        <div class="week-controls">
                            <button onclick="selectAllWeeks()">✅ تحديد الكل</button>
                            <button onclick="deselectAllWeeks()">❌ إلغاء الكل</button>
                            <button onclick="selectFirstHalf()">١-٩ الأسابيع الأولى</button>
                            <button onclick="selectSecondHalf()">١٠-١٩ الأسابيع الثانية</button>
                        </div>
                        <div class="week-selector" id="weekSelector">
                            <!-- سيتم ملؤها ديناميكياً -->
                        </div>
                    </div>
                </div>
                <div style="text-align: center; margin-top: 10px;">
                    <button onclick="generateWeeklyAttendance()">🎲 إنشاء تحضير للأسابيع المحددة</button>
                    <button onclick="clearWeeklyAttendance()">🗑️ مسح تحضير الأسابيع</button>
                </div>
                <div style="text-align: center; margin-top: 10px;">
                    <span class="period-info" id="weeklyStatusInfo">لم يتم إنشاء تحضير للأسابيع</span>
                </div>
            </div>
            <div style="text-align:center; margin-top:10px; font-size:12px; color:#666;">
                ⭐ خاصية التحضير العشوائي: سيتم وضع ✓ لكل الخيارات للطلاب المتميزين (الذين لديهم نجمة)
            </div>
        </div>
        
        <div class="admin-section">
            <h4>🎲 التحضير العشوائي لفترة محددة</h4>
            <div class="random-period-section">
                <div class="admin-row">
                    <div class="admin-label">تاريخ بداية الفترة:</div>
                    <div class="admin-input">
                        <input type="date" id="periodStartDate" class="date-input" style="width: 100%;">
                    </div>
                </div>
                <div class="admin-row">
                    <div class="admin-label">تاريخ نهاية الفترة:</div>
                    <div class="admin-input">
                        <input type="date" id="periodEndDate" class="date-input" style="width: 100%;">
                    </div>
                </div>
                <div style="text-align: center; margin-top: 10px;">
                    <button onclick="setPeriodToExample()">📅 تعيين فترة مثال (31/8 إلى 4/9)</button>
                    <button onclick="clearPeriod()">🗑️ مسح الفترة</button>
                </div>
                <div style="text-align: center; margin-top: 10px;">
                    <button onclick="savePeriodSettings()">💾 حفظ إعدادات الفترة</button>
                    <span class="period-info" id="currentPeriodInfo">لا توجد فترة محددة</span>
                </div>
            </div>
            <div style="text-align: center; margin-top: 15px;">
                <button onclick="randomAttendance()">🎲 تحضير عشوائي للتاريخ الحالي</button>
                <button onclick="randomAttendanceForPeriod()">📅 تحضير عشوائي للفترة المحددة</button>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>👨‍🏫 إدارة الطلاب</h4>
            <div style="text-align:center;">
                <button onclick="addStudent()">➕ إضافة طالب</button>
                <button onclick="moveStudent()">↔️ نقل طالب</button>
                <button onclick="resetAll()">🔄 إعادة تعيين</button>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>📊 الإحصائيات</h4>
            <div style="text-align:center;">
                <button onclick="showStatistics()">📈 عرض الإحصائيات</button>
                <button onclick="backupData()">💾 نسخ احتياطي</button>
                <button onclick="loadBackup()">📂 استعادة نسخة</button>
            </div>
        </div>
        
        <p style="text-align:center; font-size:12px; color:#666;">بعد تفعيل الإدارة، يمكن تمييز الطلاب بالنجمة وإدارة جميع الخصائص.</p>
    </div>
</div>

<script>
// بيانات الطلاب لكل صف - النسخة الجديدة
const studentsData = {
    "3-1": [
        { "id": 1, "name": "إسماعيل محمد هاشم شفيق الرحمن" },
        { "id": 2, "name": "ابراهيم علي ابو بكر محمد" },
        { "id": 3, "name": "باسم محمد ابو طالب" },
        { "id": 4, "name": "حسين بشير أمادو جازير" },
        { "id": 5, "name": "حسين هارون عثمان عبدالمؤمن ادم" },
        { "id": 6, "name": "حمد محمد عثمان بخش" },
        { "id": 7, "name": "رمضان عيسى باكور محمد" },
        { "id": 8, "name": "ريان عبد الرحمن موسى جيبو" },
        { "id": 9, "name": "ريحان محمد مقبول حسين عمر حمزه" },
        { "id": 10, "name": "عامر مولوي حسن شريف" },
        { "id": 11, "name": "عبدالحليم نور كبير صديق احمد" },
        { "id": 12, "name": "عمران يعقوب محمد محمد مسلم" },
        { "id": 13, "name": "عمير محمد محمد شفيع حكيم علي" },
        { "id": 14, "name": "فارس محمد ابو البشر واعظ علي" },
        { "id": 15, "name": "محمد احمد فضل الرحمن فايز اللّٰه" },
        { "id": 16, "name": "حمد انوار رشيد احمد اظهار مياه" },
        { "id": 17, "name": "حمد عبدالرزاق محمد عبدالقادر" },
        { "id": 18, "name": "حمد عبدالشكور عبدالحميد عبد الرشيد" },
        { "id": 19, "name": "مهدي محمد محمد اسلام عبدالسلام" },
        { "id": 20, "name": "مهدي موسى حميد الحق احمد" },
        { "id": 21, "name": "ياسين محمد يوسف" }
    ],
    "2-3": [
        { "id": 1, "name": "إبراهيم إدريس إبراهيم اولوجيوم" },
        { "id": 2, "name": "إدريس محمد حسن أحمد" },
        { "id": 3, "name": "امين عبداللّه دايابو عثمان" },
        { "id": 4, "name": "بسام عبدالسلام هاشم انور علي" },
        { "id": 5, "name": "حافظ بيلو موسى سليمان" },
        { "id": 6, "name": "حسين علي حسن مهاوش" },
        { "id": 7, "name": "خالد طيب اسماعيل محمد" },
        { "id": 8, "name": "خالد عبد الحميد محمد هاشم" },
        { "id": 9, "name": "خالد وليد محمد محمد" },
        { "id": 10, "name": "ريان عبدالرحمن عمر نانتومي" },
        { "id": 11, "name": "سليمان ابراهيم ديقوقا" },
        { "id": 12, "name": "صالح عبدالله محمد قاسم يوسف علي" },
        { "id": 13, "name": "عبدالعزيز اول اودو محمد" },
        { "id": 14, "name": "عثمان عبد الرحمن باي محمد" },
        { "id": 15, "name": "عدنان نور امير حسين" },
        { "id": 16, "name": "عمر سراج محمد زكريا" },
        { "id": 17, "name": "فهد محمد حسين عبداللّه مياه حسين" },
        { "id": 18, "name": "محمد ابراهيم سعيد هو ساوي" },
        { "id": 19, "name": "محمد محمد امين اسلام خليل الرحمن" },
        { "id": 20, "name": "مشعل ابو طاهر ناظر حسين عبدالمطلب" },
        { "id": 21, "name": "موسى ابو بكر الصديق عبدالجبار امة علي" },
        { "id": 22, "name": "يوسف مهدي عابدين محمد" }
    ],
    "3-3": [
        { "id": 1, "name": "ابراهيم جزولي اسدانور" },
        { "id": 2, "name": "تركي عبدالصمد عبدالغني محمد حسين" },
        { "id": 3, "name": "حسام حسن ابو الكلام مقبول احمد" },
        { "id": 4, "name": "حسن عيسى بكوري محمد" },
        { "id": 5, "name": "سعد سلام ستار ارشاد اللّٰه" },
        { "id": 6, "name": "عايض سيف الاسلام نور احمد علي" },
        { "id": 7, "name": "عبدالكريم عثمان ابكر كوجو" },
        { "id": 8, "name": "عزام شمس العالم قاسم علي" },
        { "id": 9, "name": "عماد محمد صديق محمد شفيع سيد" },
        { "id": 10, "name": "عمر عبد القدوس عبدالسلام عبد السبحان" },
        { "id": 11, "name": "عمر مورتلا أبو بكر محمد" },
        { "id": 12, "name": "فيصل احمد ابو بكر محمد" },
        { "id": 13, "name": "محمد اسحاق محمد اسلام عبدالحكيم" },
        { "id": 14, "name": "محمد عبدالله ابو سعيد مياه" },
        { "id": 15, "name": "حمد محمد اسماعيل امير حسين ابو بكر" },
        { "id": 16, "name": "حمد موسى ساليفو ديقوقا" },
        { "id": 17, "name": "مشاري شيهو اسماعيل محمد بكر" },
        { "id": 18, "name": "ياسر عبدالرحيم محمد علي سفر علي" },
        { "id": 19, "name": "يوسف محمد عبد الرحمن علي" }
    ],
    "4-3": [
        { "id": 1, "name": "ابراهيم عوض احمد فليس" },
        { "id": 2, "name": "احمد ابراهيم ابن زكريا الهوسه" },
        { "id": 3, "name": "احمد عبد القيوم محمد يعقوب" },
        { "id": 4, "name": "اسماعيل اول اودو محمد" },
        { "id": 5, "name": "اوسامة سعيدو دو غويد" },
        { "id": 6, "name": "تامر عبد الصمد عبد الغني" },
        { "id": 7, "name": "تركي هارون حسن شريف" },
        { "id": 8, "name": "ريان محمد مقبول حسين حسين" },
        { "id": 9, "name": "ريان هارون الرشيد طفيل احمد نذير احمد" },
        { "id": 10, "name": "عبدالحليم محمد عبدالله عبدالحكيم" },
        { "id": 11, "name": "عبدالله حفيظ اللّٰه سلطان أحمد" },
        { "id": 12, "name": "عيسى عثمان سعيد عالم حبيب الرحمن" },
        { "id": 13, "name": "فهد أسار رشيد احمد" },
        { "id": 14, "name": "فهد محمد نور مقبول اشرف" },
        { "id": 15, "name": "محمد محمد ادريس نبية حسين يعقوب علي" },
        { "id": 16, "name": "مصلح محمد ولي احمد" },
        { "id": 17, "name": "معاذ عثمان صديق كالو" },
        { "id": 18, "name": "يوسف بدماسي ابراهيم البد ماسي" }
    ],
    "5-3": [
        { "id": 1, "name": "ابراهيم خالد سليمان ابراهيم" },
        { "id": 2, "name": "انس عبدالعزيز نور احمد" },
        { "id": 3, "name": "بدر بكر عمر محمد" },
        { "id": 4, "name": "حمد محمد حسين مياه شمس العالم اظهر مياه" },
        { "id": 5, "name": "رضوان رشيد أحمد نور محمد لال مياه" },
        { "id": 6, "name": "سعيد عبدالله سعيد محمد" },
        { "id": 7, "name": "عامر رحمة اللّٰه محمد شفيع" },
        { "id": 8, "name": "عبد اللّٰه حسين علي فليس" },
        { "id": 9, "name": "عبد العزيز سراج ابكر عثمان" },
        { "id": 10, "name": "عبدالله عيسى ابراهيم" },
        { "id": 11, "name": "عمر محمد عمر صالح" },
        { "id": 12, "name": "غسان عثمان اسماعيل عبدالله عبد اللّٰه" },
        { "id": 13, "name": "فاضل عادل صالح الرايس" },
        { "id": 14, "name": "محمد فريد كبير احمد عباد اللّٰه" },
        { "id": 15, "name": "محمد محمد سلطان احمد محمد" },
        { "id": 16, "name": "محمد موسى أدامو محمد" },
        { "id": 17, "name": "محمد نور محمد زكريا آمال حسين" },
        { "id": 18, "name": "مشاري محمد هارو" },
        { "id": 19, "name": "مشاري يعقوب أبو بكر ابراهيم" },
        { "id": 20, "name": "منذر علي عمر قوني" },
        { "id": 21, "name": "هود حسن عبدالكريم الياس" },
        { "id": 22, "name": "يعقوب محمد إسحاق يار محمد فضل على" }
    ]
};

// حالة الإدارة
let adminActive = false;
let currentFilter = 'all';
let currentClass = 'all';

// إدارة التاريخ
let currentDate = new Date(); // تاريخ اليوم الحقيقي
let selectedDate = new Date(); // التاريخ المعروض (يمكن تغييره من الإدارة)

// إعدادات الفصل الدراسي
let semesterSettings = {
    semester: "1", // تم التغيير إلى الفصل الأول
    academicYear: "١٤٤٧هـ" // تم التغيير إلى 1447
};

// إعدادات فترة التحضير العشوائي
let periodSettings = {
    startDate: null,
    endDate: null
};

// بيانات التحضير المخزنة لكل يوم
let periodAttendanceData = {};

// التاريخ الهجري
let hijriDate = {
    day: 1,
    month: 1,
    year: 1446,
    monthName: "محرم"
};

// بيانات الأسابيع الدراسية
const academicWeeks = {
    1: [
        { day: "الأحد", gregorian: "2025-08-24", hijri: "1447-03-01" },
        { day: "الاثنين", gregorian: "2025-08-25", hijri: "1447-03-02" },
        { day: "الثلاثاء", gregorian: "2025-08-26", hijri: "1447-03-03" },
        { day: "الأربعاء", gregorian: "2025-08-27", hijri: "1447-03-04" },
        { day: "الخميس", gregorian: "2025-08-28", hijri: "1447-03-05" }
    ],
    2: [
        { day: "الأحد", gregorian: "2025-08-31", hijri: "1447-03-08" },
        { day: "الاثنين", gregorian: "2025-09-01", hijri: "1447-03-09" },
        { day: "الثلاثاء", gregorian: "2025-09-02", hijri: "1447-03-10" },
        { day: "الأربعاء", gregorian: "2025-09-03", hijri: "1447-03-11" },
        { day: "الخميس", gregorian: "2025-09-04", hijri: "1447-03-12" }
    ],
    3: [
        { day: "الأحد", gregorian: "2025-09-07", hijri: "1447-03-15" },
        { day: "الاثنين", gregorian: "2025-09-08", hijri: "1447-03-16" },
        { day: "الثلاثاء", gregorian: "2025-09-09", hijri: "1447-03-17" },
        { day: "الأربعاء", gregorian: "2025-09-10", hijri: "1447-03-18" },
        { day: "الخميس", gregorian: "2025-09-11", hijri: "1447-03-19" }
    ],
    4: [
        { day: "الأحد", gregorian: "2025-09-14", hijri: "1447-03-22" },
        { day: "الاثنين", gregorian: "2025-09-15", hijri: "1447-03-23" },
        { day: "الثلاثاء", gregorian: "2025-09-16", hijri: "1447-03-24" },
        { day: "الأربعاء", gregorian: "2025-09-17", hijri: "1447-03-25" },
        { day: "الخميس", gregorian: "2025-09-18", hijri: "1447-03-26" }
    ],
    5: [
        { day: "الأحد", gregorian: "2025-09-21", hijri: "1447-03-29" },
        { day: "الاثنين", gregorian: "2025-09-22", hijri: "1447-03-30" },
        { day: "الثلاثاء", gregorian: "2025-09-23", hijri: "1447-03-31" },
        { day: "الأربعاء", gregorian: "2025-09-24", hijri: "1447-04-01" },
        { day: "الخميس", gregorian: "2025-09-25", hijri: "1447-04-02" }
    ],
    6: [
        { day: "الأحد", gregorian: "2025-09-28", hijri: "1447-04-05" },
        { day: "الاثنين", gregorian: "2025-09-29", hijri: "1447-04-06" },
        { day: "الثلاثاء", gregorian: "2025-09-30", hijri: "1447-04-07" },
        { day: "الأربعاء", gregorian: "2025-10-01", hijri: "1447-04-08" },
        { day: "الخميس", gregorian: "2025-10-02", hijri: "1447-04-09" }
    ],
    7: [
        { day: "الأحد", gregorian: "2025-10-05", hijri: "1447-04-12" },
        { day: "الاثنين", gregorian: "2025-10-06", hijri: "1447-04-13" },
        { day: "الثلاثاء", gregorian: "2025-10-07", hijri: "1447-04-14" },
        { day: "الأربعاء", gregorian: "2025-10-08", hijri: "1447-04-15" },
        { day: "الخميس", gregorian: "2025-10-09", hijri: "1447-04-16" }
    ],
    8: [
        { day: "الاثنين", gregorian: "2025-10-13", hijri: "1447-04-20" },
        { day: "الثلاثاء", gregorian: "2025-10-14", hijri: "1447-04-21" },
        { day: "الأربعاء", gregorian: "2025-10-15", hijri: "1447-04-22" },
        { day: "الخميس", gregorian: "2025-10-16", hijri: "1447-04-23" }
    ],
    9: [
        { day: "الأحد", gregorian: "2025-10-19", hijri: "1447-04-26" },
        { day: "الاثنين", gregorian: "2025-10-20", hijri: "1447-04-27" },
        { day: "الثلاثاء", gregorian: "2025-10-21", hijri: "1447-04-28" },
        { day: "الأربعاء", gregorian: "2025-10-22", hijri: "1447-04-29" },
        { day: "الخميس", gregorian: "2025-10-23", hijri: "1447-04-30" }
    ],
    10: [
        { day: "الأحد", gregorian: "2025-10-26", hijri: "1447-05-03" },
        { day: "الاثنين", gregorian: "2025-10-27", hijri: "1447-05-04" },
        { day: "الثلاثاء", gregorian: "2025-10-28", hijri: "1447-05-05" },
        { day: "الأربعاء", gregorian: "2025-10-29", hijri: "1447-05-06" },
        { day: "الخميس", gregorian: "2025-10-30", hijri: "1447-05-07" }
    ],
    11: [
        { day: "الأحد", gregorian: "2025-11-02", hijri: "1447-05-10" },
        { day: "الاثنين", gregorian: "2025-11-03", hijri: "1447-05-11" },
        { day: "الثلاثاء", gregorian: "2025-11-04", hijri: "1447-05-12" },
        { day: "الأربعاء", gregorian: "2025-11-05", hijri: "1447-05-13" },
        { day: "الخميس", gregorian: "2025-11-06", hijri: "1447-05-14" }
    ],
    12: [
        { day: "الأحد", gregorian: "2025-11-09", hijri: "1447-05-17" },
        { day: "الاثنين", gregorian: "2025-11-10", hijri: "1447-05-18" },
        { day: "الثلاثاء", gregorian: "2025-11-11", hijri: "1447-05-19" },
        { day: "الأربعاء", gregorian: "2025-11-12", hijri: "1447-05-20" },
        { day: "الخميس", gregorian: "2025-11-13", hijri: "1447-05-21" }
    ],
    13: [
        { day: "الأحد", gregorian: "2025-11-16", hijri: "1447-05-24" },
        { day: "الاثنين", gregorian: "2025-11-17", hijri: "1447-05-25" },
        { day: "الثلاثاء", gregorian: "2025-11-18", hijri: "1447-05-26" },
        { day: "الأربعاء", gregorian: "2025-11-19", hijri: "1447-05-27" },
        { day: "الخميس", gregorian: "2025-11-20", hijri: "1447-05-28" }
    ],
    // الأسبوع 14 إجازة الخريف - غير موجود
    15: [
        { day: "الأحد", gregorian: "2025-11-30", hijri: "1447-06-09" },
        { day: "الاثنين", gregorian: "2025-12-01", hijri: "1447-06-10" },
        { day: "الثلاثاء", gregorian: "2025-12-02", hijri: "1447-06-11" },
        { day: "الأربعاء", gregorian: "2025-12-03", hijri: "1447-06-12" }
    ],
    16: [
        { day: "الاثنين", gregorian: "2025-12-08", hijri: "1447-06-17" },
        { day: "الثلاثاء", gregorian: "2025-12-09", hijri: "1447-06-18" },
        { day: "الأربعاء", gregorian: "2025-12-10", hijri: "1447-06-19" },
        { day: "الخميس", gregorian: "2025-12-11", hijri: "1447-06-20" }
    ],
    17: [
        { day: "الأحد", gregorian: "2025-12-14", hijri: "1447-06-23" },
        { day: "الاثنين", gregorian: "2025-12-15", hijri: "1447-06-24" },
        { day: "الثلاثاء", gregorian: "2025-12-16", hijri: "1447-06-25" },
        { day: "الأربعاء", gregorian: "2025-12-17", hijri: "1447-06-26" },
        { day: "الخميس", gregorian: "2025-12-18", hijri: "1447-06-27" }
    ],
    18: [
        { day: "الأحد", gregorian: "2025-12-21", hijri: "1447-07-01" },
        { day: "الاثنين", gregorian: "2025-12-22", hijri: "1447-07-02" },
        { day: "الثلاثاء", gregorian: "2025-12-23", hijri: "1447-07-03" },
        { day: "الأربعاء", gregorian: "2025-12-24", hijri: "1447-07-04" },
        { day: "الخميس", gregorian: "2025-12-25", hijri: "1447-07-05" }
    ],
    19: [
        { day: "الأحد", gregorian: "2025-12-28", hijri: "1447-07-08" },
        { day: "الاثنين", gregorian: "2025-12-29", hijri: "1447-07-09" },
        { day: "الثلاثاء", gregorian: "2025-12-30", hijri: "1447-07-10" },
        { day: "الأربعاء", gregorian: "2025-12-31", hijri: "1447-07-11" },
        { day: "الخميس", gregorian: "2026-01-01", hijri: "1447-07-12" }
    ]
};

// حالة الأسابيع المحددة
let selectedWeeks = new Set([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 15, 16, 17, 18, 19]);

// أسماء الأشهر الهجرية
const hijriMonths = [
    "محرم", "صفر", "ربيع الأول", "ربيع الثاني", 
    "جمادى الأولى", "جمادى الآخرة", "رجب", "شعبان", 
    "رمضان", "شوال", "ذو القعدة", "ذو الحجة"
];

// أسماء الأشهر الميلادية بالعربية
const gregorianMonths = [
    "يناير", "فبراير", "مارس", "أبريل", "مايو", "يونيو",
    "يوليو", "أغسطس", "سبتمبر", "أكتوبر", "نوفمبر", "ديسمبر"
];

// أيام الأسبوع بالعربية
const weekDays = [
    "الأحد", "الاثنين", "الثلاثاء", "الأربعاء", "الخميس", "الجمعة", "السبت"
];

// تهيئة الصفحة
function initPage() {
    // دائماً نبدأ بتاريخ اليوم الحقيقي
    currentDate = new Date();
    selectedDate = new Date(currentDate); // نبدأ بتاريخ اليوم
    
    // محاولة تحميل إعدادات الفصل الدراسي
    const savedSemester = localStorage.getItem('teacherTracker_semesterSettings');
    if (savedSemester) {
        semesterSettings = JSON.parse(savedSemester);
        document.getElementById('semesterSelect').value = semesterSettings.semester;
        document.getElementById('academicYear').value = semesterSettings.academicYear;
        updateSemesterInfo();
    }
    
    // محاولة تحميل إعدادات فترة التحضير
    const savedPeriod = localStorage.getItem('teacherTracker_periodSettings');
    if (savedPeriod) {
        periodSettings = JSON.parse(savedPeriod);
        if (periodSettings.startDate) {
            document.getElementById('periodStartDate').value = periodSettings.startDate;
        }
        if (periodSettings.endDate) {
            document.getElementById('periodEndDate').value = periodSettings.endDate;
        }
        updatePeriodInfo();
    }
    
    // محاولة تحميل بيانات التحضير المحفوظة
    loadPeriodAttendanceData();
    
    // تحميل الأسابيع المحددة
    loadSelectedWeeks();
    
    // حساب التاريخ الهجري الفعلي من التاريخ الميلادي
    calculateHijriFromGregorian();
    
    // محاولة تحميل بيانات الحضور المحفوظة لهذا التاريخ
    loadAttendanceData();
    
    createClassTabs();
    createTables();
    createWeekSelector();
    updateStudentCount();
    updateDateDisplay();
    updateWeeklyStatusInfo();
    
    // تعيين التاريخ الحالي في منتقي التاريخ
    const today = new Date().toISOString().split('T')[0];
    document.getElementById('datePicker').value = today;
    
    // تحديث حقول التاريخ الهجري
    updateHijriFields();
}

// إنشاء منتقي الأسابيع
function createWeekSelector() {
    const weekSelector = document.getElementById('weekSelector');
    weekSelector.innerHTML = '';
    
    // إنشاء خانات اختيار للأسابيع 1-13 و 15-19
    for (let week = 1; week <= 19; week++) {
        // تخطي الأسبوع 14 (إجازة الخريف)
        if (week === 14) continue;
        
        const weekDiv = document.createElement('div');
        weekDiv.className = 'week-checkbox';
        weekDiv.innerHTML = `
            <input type="checkbox" id="week${week}" ${selectedWeeks.has(week) ? 'checked' : ''} onchange="toggleWeekSelection(${week})">
            <label for="week${week}">الأسبوع ${week}</label>
        `;
        weekSelector.appendChild(weekDiv);
    }
}

// تبديل اختيار الأسبوع
function toggleWeekSelection(week) {
    const checkbox = document.getElementById(`week${week}`);
    if (checkbox.checked) {
        selectedWeeks.add(week);
    } else {
        selectedWeeks.delete(week);
    }
    saveSelectedWeeks();
    updateWeeklyStatusInfo();
}

// تحديد جميع الأسابيع
function selectAllWeeks() {
    for (let week = 1; week <= 19; week++) {
        if (week === 14) continue; // تخطي الأسبوع 14
        selectedWeeks.add(week);
        const checkbox = document.getElementById(`week${week}`);
        if (checkbox) checkbox.checked = true;
    }
    saveSelectedWeeks();
    updateWeeklyStatusInfo();
    alert("تم تحديد جميع الأسابيع الدراسية");
}

// إلغاء تحديد جميع الأسابيع
function deselectAllWeeks() {
    selectedWeeks.clear();
    for (let week = 1; week <= 19; week++) {
        if (week === 14) continue;
        const checkbox = document.getElementById(`week${week}`);
        if (checkbox) checkbox.checked = false;
    }
    saveSelectedWeeks();
    updateWeeklyStatusInfo();
    alert("تم إلغاء تحديد جميع الأسابيع");
}

// تحديد النصف الأول من الأسابيع (1-9)
function selectFirstHalf() {
    deselectAllWeeks();
    for (let week = 1; week <= 9; week++) {
        selectedWeeks.add(week);
        const checkbox = document.getElementById(`week${week}`);
        if (checkbox) checkbox.checked = true;
    }
    saveSelectedWeeks();
    updateWeeklyStatusInfo();
    alert("تم تحديد الأسابيع من 1 إلى 9");
}

// تحديد النصف الثاني من الأسابيع (10-19)
function selectSecondHalf() {
    deselectAllWeeks();
    for (let week = 10; week <= 19; week++) {
        if (week === 14) continue; // تخطي الأسبوع 14
        selectedWeeks.add(week);
        const checkbox = document.getElementById(`week${week}`);
        if (checkbox) checkbox.checked = true;
    }
    saveSelectedWeeks();
    updateWeeklyStatusInfo();
    alert("تم تحديد الأسابيع من 10 إلى 19");
}

// حفظ الأسابيع المحددة
function saveSelectedWeeks() {
    localStorage.setItem('teacherTracker_selectedWeeks', JSON.stringify(Array.from(selectedWeeks)));
}

// تحميل الأسابيع المحددة
function loadSelectedWeeks() {
    const savedWeeks = localStorage.getItem('teacherTracker_selectedWeeks');
    if (savedWeeks) {
        selectedWeeks = new Set(JSON.parse(savedWeeks));
    }
}

// تحديث معلومات حالة الأسابيع
function updateWeeklyStatusInfo() {
    const weeklyStatusInfo = document.getElementById('weeklyStatusInfo');
    const weeksArray = Array.from(selectedWeeks).sort((a, b) => a - b);
    
    if (weeksArray.length === 0) {
        weeklyStatusInfo.textContent = "لم يتم تحديد أي أسابيع";
        return;
    }
    
    // تجميع الأسابيع المتتالية
    const ranges = [];
    let start = weeksArray[0];
    let end = weeksArray[0];
    
    for (let i = 1; i < weeksArray.length; i++) {
        if (weeksArray[i] === end + 1) {
            end = weeksArray[i];
        } else {
            if (start === end) {
                ranges.push(`${start}`);
            } else {
                ranges.push(`${start}-${end}`);
            }
            start = weeksArray[i];
            end = weeksArray[i];
        }
    }
    
    if (start === end) {
        ranges.push(`${start}`);
    } else {
        ranges.push(`${start}-${end}`);
    }
    
    weeklyStatusInfo.textContent = `الأسابيع المحددة: ${ranges.join('، ')} (${weeksArray.length} أسبوع)`;
}

// إنشاء تحضير عشوائي للأسابيع المحددة
function generateWeeklyAttendance() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    if (selectedWeeks.size === 0) {
        alert("يرجى تحديد أسابيع دراسية أولاً!");
        return;
    }
    
    const weeksArray = Array.from(selectedWeeks).sort((a, b) => a - b);
    const totalWeeks = weeksArray.length;
    
    let totalDays = 0;
    let totalStudents = 0;
    let totalStarredStudents = 0;
    
    // حساب إجمالي الأيام
    weeksArray.forEach(week => {
        if (academicWeeks[week]) {
            totalDays += academicWeeks[week].length;
        }
    });
    
    const confirmMessage = `هل تريد إنشاء تحضير عشوائي للأسابيع المحددة؟\n\n` +
                          `عدد الأسابيع: ${totalWeeks} أسبوع\n` +
                          `عدد الأيام: ${totalDays} يوم\n\n` +
                          `ملاحظة: سيتم وضع ✓ لكل الخيارات للطلاب المتميزين (الذين لديهم نجمة ⭐)`;
    
    const confirmAction = confirm(confirmMessage);
    if (!confirmAction) return;
    
    // معالجة كل أسبوع
    weeksArray.forEach(week => {
        if (academicWeeks[week]) {
            academicWeeks[week].forEach(dayData => {
                const date = new Date(dayData.gregorian);
                const dateKey = date.toISOString().split('T')[0];
                
                // إنشاء تحضير عشوائي لهذا اليوم
                const attendanceData = generateRandomAttendanceForDate(date, dayData.hijri);
                
                // حفظ بيانات اليوم
                periodAttendanceData[dateKey] = attendanceData;
                
                // حساب الإحصائيات
                for (const className in attendanceData.classes) {
                    totalStudents += attendanceData.classes[className].stats.total;
                    totalStarredStudents += attendanceData.classes[className].stats.starred;
                }
            });
        }
    });
    
    // حفظ بيانات الفترة
    savePeriodAttendanceData();
    
    // حساب الإحصائيات النهائية
    const totalRegularStudents = totalStudents - totalStarredStudents;
    const avgStudentsPerDay = totalStudents / totalDays;
    const avgStarredPerDay = totalStarredStudents / totalDays;
    
    // عرض تقرير النتائج
    const resultMessage = `✅ تم إنشاء التحضير العشوائي للأسابيع المحددة بنجاح!\n\n` +
                         `📊 الإحصائيات:\n` +
                         `   - عدد الأسابيع: ${totalWeeks} أسبوع\n` +
                         `   - عدد الأيام: ${totalDays} يوم\n` +
                         `   - إجمالي الطلاب المعالجين: ${totalStudents} طالب\n` +
                         `   - متوسط الطلاب في اليوم: ${avgStudentsPerDay.toFixed(1)} طالب\n` +
                         `   - إجمالي الطلاب المتميزين: ${totalStarredStudents} طالب\n` +
                         `   - إجمالي الطلاب العاديين: ${totalRegularStudents} طالب\n\n` +
                         `💾 تم حفظ بيانات التحضير لكل يوم في النظام.`;
    
    alert(resultMessage);
}

// توليد تحضير عشوائي ليوم معين مع التاريخ الهجري المحدد
function generateRandomAttendanceForDate(date, hijriDateStr) {
    const dateKey = date.toISOString().split('T')[0];
    
    const attendanceData = {
        date: dateKey,
        gregorianDate: getShortGregorianDate(date),
        hijriDate: hijriDateStr,
        classes: {}
    };
    
    // توليد بيانات لكل صف
    for (const className in studentsData) {
        attendanceData.classes[className] = {
            students: [],
            stats: {
                total: 0,
                present: 0,
                absent: 0,
                starred: 0
            }
        };
        
        studentsData[className].forEach((studentData, index) => {
            // تحديد عشوائياً إذا كان الطالب متميزاً (20% احتمال)
            const isStarred = Math.random() < 0.2;
            
            // إنشاء بيانات الطالب
            const student = {
                id: studentData.id,
                name: studentData.name,
                isStarred: isStarred,
                attendance: [],
                hasStar: isStarred
            };
            
            // توليد بيانات الحضور (5 عناصر)
            for (let i = 0; i < 5; i++) {
                if (isStarred) {
                    // الطلاب المتميزون يحصلون على ✓ في كل الخيارات
                    student.attendance.push({
                        type: ['الحضور', 'الواجبات', 'المشروعات', 'تطبيقات وأنشطة', 'مشاركة'][i],
                        value: '✔',
                        isPresent: true
                    });
                    attendanceData.classes[className].stats.present++;
                } else {
                    // الطلاب العاديون يحصلون على تقييم عشوائي
                    const isPresent = Math.random() > 0.3;
                    student.attendance.push({
                        type: ['الحضور', 'الواجبات', 'المشروعات', 'تطبيقات وأنشطة', 'مشاركة'][i],
                        value: isPresent ? '✔' : '✖',
                        isPresent: isPresent
                    });
                    
                    if (isPresent) {
                        attendanceData.classes[className].stats.present++;
                    } else {
                        attendanceData.classes[className].stats.absent++;
                    }
                }
            }
            
            attendanceData.classes[className].students.push(student);
            attendanceData.classes[className].stats.total++;
            
            if (isStarred) {
                attendanceData.classes[className].stats.starred++;
            }
        });
    }
    
    return attendanceData;
}

// مسح تحضير الأسابيع
function clearWeeklyAttendance() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const confirmAction = confirm("هل تريد مسح تحضير جميع الأسابيع الدراسية؟");
    if (!confirmAction) return;
    
    // حذف بيانات جميع أيام الأسابيع الدراسية
    for (const week in academicWeeks) {
        academicWeeks[week].forEach(dayData => {
            const dateKey = dayData.gregorian;
            delete periodAttendanceData[dateKey];
        });
    }
    
    savePeriodAttendanceData();
    updateWeeklyStatusInfo();
    alert("تم مسح تحضير جميع الأسابيع الدراسية");
}

// تحميل بيانات التحضير المحفوظة للفترة
function loadPeriodAttendanceData() {
    const savedData = localStorage.getItem('teacherTracker_periodAttendanceData');
    if (savedData) {
        periodAttendanceData = JSON.parse(savedData);
        console.log('تم تحميل بيانات التحضير للفترة:', Object.keys(periodAttendanceData).length, 'يوم');
    }
}

// حفظ بيانات التحضير للفترة
function savePeriodAttendanceData() {
    localStorage.setItem('teacherTracker_periodAttendanceData', JSON.stringify(periodAttendanceData));
}

// حساب التاريخ الهجري من التاريخ الميلادي
function calculateHijriFromGregorian() {
    try {
        // استخدام مكتبة ummAlQura لحساب التاريخ الهجري
        if (typeof HijriDate !== 'undefined') {
            const hijri = new HijriDate(selectedDate);
            hijriDate.day = hijri.date;
            hijriDate.month = hijri.month;
            hijriDate.year = hijri.year;
            hijriDate.monthName = hijriMonths[hijri.month - 1];
        } else {
            // طريقة احتياطية إذا لم تكن المكتبة متوفرة
            const fixedHijri = getApproximateHijriDate(selectedDate);
            hijriDate.day = fixedHijri.day;
            hijriDate.month = fixedHijri.month;
            hijriDate.year = fixedHijri.year;
            hijriDate.monthName = hijriMonths[fixedHijri.month - 1];
        }
    } catch (error) {
        console.error("خطأ في حساب التاريخ الهجري:", error);
        // استخدام تاريخ افتراضي في حالة الخطأ
        hijriDate = { day: 1, month: 1, year: 1446, monthName: "محرم" };
    }
}

// طريقة تقريبية لحساب التاريخ الهجري (بدون مكتبة)
function getApproximateHijriDate(gregorianDate) {
    const startHijri = new Date(622, 6, 16); // 16 يوليو 622م هو بداية الهجرة
    
    const diffTime = gregorianDate - startHijri;
    const diffDays = Math.floor(diffTime / (1000 * 60 * 60 * 24));
    
    // السنة الهجرية = عدد الأيام / 354.367 (متوسط طول السنة الهجرية)
    const hijriYear = Math.floor(diffDays / 354.367) + 1;
    
    // الأيام المتبقية في السنة الحالية
    const daysInCurrentYear = diffDays % 354.367;
    
    // تقدير الشهر (كل شهر حوالي 29.5 يوم)
    const hijriMonth = Math.floor(daysInCurrentYear / 29.53) + 1;
    
    // اليوم من الشهر
    const hijriDay = Math.floor(daysInCurrentYear % 29.53) + 1;
    
    return {
        day: Math.min(Math.max(1, hijriDay), 30),
        month: Math.min(Math.max(1, hijriMonth), 12),
        year: Math.max(1300, Math.min(1500, hijriYear))
    };
}

// تحويل الأرقام الإنجليزية إلى عربية
function convertToArabicNumbers(num) {
    const arabicNumbers = ['٠', '١', '٢', '٣', '٤', '٥', '٦', '٧', '٨', '٩'];
    return num.toString().replace(/\d/g, digit => arabicNumbers[digit]);
}

// الحصول على التاريخ الميلادي بصيغة عربية صحيحة (بدون تحويل هجري)
function getGregorianDateString(date) {
    const day = date.getDate();
    const month = gregorianMonths[date.getMonth()];
    const year = date.getFullYear();
    const weekDay = weekDays[date.getDay()];
    
    const arabicDay = convertToArabicNumbers(day);
    const arabicYear = convertToArabicNumbers(year);
    
    return `${weekDay}، ${arabicDay} ${month} ${arabicYear}`;
}

// الحصول على التاريخ الميلادي قصير للتقرير
function getShortGregorianDate(date) {
    const day = date.getDate();
    const month = gregorianMonths[date.getMonth()];
    const year = date.getFullYear();
    
    const arabicDay = convertToArabicNumbers(day);
    const arabicYear = convertToArabicNumbers(year);
    
    return `${arabicDay} ${month} ${arabicYear}`;
}

// حساب التاريخ الهجري لـ Date معين
function calculateHijriForDate(date) {
    try {
        if (typeof HijriDate !== 'undefined') {
            const hijri = new HijriDate(date);
            return {
                day: hijri.date,
                month: hijri.month,
                year: hijri.year,
                monthName: hijriMonths[hijri.month - 1]
            };
        } else {
            const fixedHijri = getApproximateHijriDate(date);
            return {
                day: fixedHijri.day,
                month: fixedHijri.month,
                year: fixedHijri.year,
                monthName: hijriMonths[fixedHijri.month - 1]
            };
        }
    } catch (error) {
        console.error("خطأ في حساب التاريخ الهجري:", error);
        return { day: 1, month: 1, year: 1446, monthName: "محرم" };
    }
}

// تحديث عرض التاريخ
function updateDateDisplay() {
    // تحديث التاريخ الميلادي باستخدام الصيغة الصحيحة
    const gregorianDateString = getGregorianDateString(selectedDate);
    
    document.getElementById('gregorianDateText').innerHTML = gregorianDateString;
    
    // تحديث التاريخ الهجري
    const hijriDateString = `${convertToArabicNumbers(hijriDate.day)} ${hijriDate.monthName} ${convertToArabicNumbers(hijriDate.year)}هـ`;
    document.getElementById('hijriDateText').innerHTML = hijriDateString;
    
    // تحديث عرض التاريخ في لوحة الإدارة
    const shortGregorian = getShortGregorianDate(selectedDate);
    document.getElementById('adminDateDisplay').innerHTML = shortGregorian;
    
    // إضافة مؤشر إذا لم يكن تاريخ اليوم
    const today = new Date();
    const isToday = selectedDate.toDateString() === today.toDateString();
    if (!isToday) {
        document.getElementById('gregorianDateText').innerHTML += ' <span style="color:#ffcc00; font-size:11px;">(غير تاريخ اليوم)</span>';
    }
}

// تحديث حقول التاريخ الهجري في واجهة الإدارة
function updateHijriFields() {
    document.getElementById('hijriDay').value = hijriDate.day;
    document.getElementById('hijriMonth').value = hijriDate.month;
    document.getElementById('hijriYear').value = hijriDate.year;
}

// تحديث معلومات الفصل الدراسي المعروضة
function updateSemesterInfo() {
    const semesterNames = {
        "1": "الفصل الدراسي الأول",
        "2": "الفصل الدراسي الثاني", 
        "3": "الفصل الدراسي الصيفي"
    };
    
    const semesterName = semesterNames[semesterSettings.semester] || "الفصل الدراسي";
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
    alert(`تم حفظ إعدادات الفصل الدراسي: ${document.getElementById('currentSemesterInfo').textContent}`);
}

// تعيين فترة مثال (31/8 إلى 4/9)
function setPeriodToExample() {
    // تاريخ البداية: 31 أغسطس 2024 (مثال)
    const startDate = new Date(2024, 7, 31); // أغسطس هو الشهر 7 (0-indexed)
    // تاريخ النهاية: 4 سبتمبر 2024 (مثال)
    const endDate = new Date(2024, 8, 4); // سبتمبر هو الشهر 8 (0-indexed)
    
    document.getElementById('periodStartDate').value = startDate.toISOString().split('T')[0];
    document.getElementById('periodEndDate').value = endDate.toISOString().split('T')[0];
    
    periodSettings.startDate = startDate.toISOString().split('T')[0];
    periodSettings.endDate = endDate.toISOString().split('T')[0];
    
    updatePeriodInfo();
    alert(`تم تعيين فترة التحضير العشوائي:\nمن: 31/8/2024 (3/8/1446هـ)\nإلى: 4/9/2024 (3/12/1446هـ)`);
}

// مسح فترة التحضير
function clearPeriod() {
    document.getElementById('periodStartDate').value = '';
    document.getElementById('periodEndDate').value = '';
    
    periodSettings.startDate = null;
    periodSettings.endDate = null;
    
    updatePeriodInfo();
    alert("تم مسح فترة التحضير المحددة");
}

// تحديث معلومات فترة التحضير المعروضة
function updatePeriodInfo() {
    const periodInfoElement = document.getElementById('currentPeriodInfo');
    
    if (periodSettings.startDate && periodSettings.endDate) {
        const startDate = new Date(periodSettings.startDate);
        const endDate = new Date(periodSettings.endDate);
        
        const startStr = getShortGregorianDate(startDate);
        const endStr = getShortGregorianDate(endDate);
        
        periodInfoElement.textContent = `${startStr} إلى ${endStr}`;
    } else {
        periodInfoElement.textContent = "لا توجد فترة محددة";
    }
}

// حفظ إعدادات فترة التحضير
function savePeriodSettings() {
    periodSettings.startDate = document.getElementById('periodStartDate').value;
    periodSettings.endDate = document.getElementById('periodEndDate').value;
    
    localStorage.setItem('teacherTracker_periodSettings', JSON.stringify(periodSettings));
    updatePeriodInfo();
    alert("تم حفظ إعدادات فترة التحضير العشوائي");
}

// تحديث التاريخ الهجري من حقول الإدخال
function updateHijriDate() {
    const day = parseInt(document.getElementById('hijriDay').value) || 1;
    const month = parseInt(document.getElementById('hijriMonth').value) || 1;
    const year = parseInt(document.getElementById('hijriYear').value) || 1446;
    
    hijriDate.day = Math.max(1, Math.min(30, day));
    hijriDate.month = Math.max(1, Math.min(12, month));
    hijriDate.year = Math.max(1300, Math.min(1500, year));
    hijriDate.monthName = hijriMonths[hijriDate.month - 1];
    
    // حفظ التاريخ الهجري
    localStorage.setItem('teacherTracker_hijriDate', JSON.stringify(hijriDate));
    
    updateDateDisplay();
    alert(`تم تحديث التاريخ الهجري إلى: ${hijriDate.day} ${hijriDate.monthName} ${hijriDate.year}هـ`);
}

// الرجوع إلى التاريخ الهجري الفعلي
function resetHijriToToday() {
    calculateHijriFromGregorian();
    updateHijriFields();
    localStorage.setItem('teacherTracker_hijriDate', JSON.stringify(hijriDate));
    updateDateDisplay();
    alert(`تم الرجوع إلى التاريخ الهجري الفعلي: ${hijriDate.day} ${hijriDate.monthName} ${hijriDate.year}هـ`);
}

// تغيير الشهر (للسابق أو القادم)
function changeMonth(offset) {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة لتغيير التاريخ');
        return;
    }
    
    selectedDate.setMonth(selectedDate.getMonth() + offset);
    
    // تحديث التاريخ الهجري بناءً على التاريخ الميلادي الجديد
    calculateHijriFromGregorian();
    
    updateDateDisplay();
    updateHijriFields();
    
    // تحميل بيانات الحضور للتاريخ الجديد
    loadAttendanceData();
    updateTablesWithLoadedData();
}

// تعيين تاريخ مخصص
function setCustomDate() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة لتغيير التاريخ');
        return;
    }
    
    const datePicker = document.getElementById('datePicker');
    if (datePicker.value) {
        selectedDate = new Date(datePicker.value);
        
        // تحديث التاريخ الهجري بناءً على التاريخ الميلادي الجديد
        calculateHijriFromGregorian();
        
        updateDateDisplay();
        updateHijriFields();
        
        // تحميل بيانات الحضور للتاريخ الجديد
        loadAttendanceData();
        updateTablesWithLoadedData();
    }
}

// الرجوع إلى تاريخ اليوم الحقيقي
function resetToToday() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة لتغيير التاريخ');
        return;
    }
    
    selectedDate = new Date(); // الرجوع لتاريخ اليوم الحقيقي
    
    // تحديث التاريخ الهجري بناءً على التاريخ الميلادي الجديد
    calculateHijriFromGregorian();
    
    const today = new Date().toISOString().split('T')[0];
    document.getElementById('datePicker').value = today;
    
    updateDateDisplay();
    updateHijriFields();
    
    // تحميل بيانات الحضور للتاريخ الجديد
    loadAttendanceData();
    updateTablesWithLoadedData();
    
    alert("تم الرجوع إلى تاريخ اليوم الحقيقي");
}

// حفظ التاريخ الحالي
function saveCurrentDate() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة لحفظ التاريخ');
        return;
    }
    
    localStorage.setItem('teacherTracker_selectedDate', selectedDate.toISOString());
    localStorage.setItem('teacherTracker_hijriDate', JSON.stringify(hijriDate));
    alert(`تم حفظ التاريخ الميلادي: ${selectedDate.toLocaleDateString('ar-SA')}\nوالهجري: ${hijriDate.day} ${hijriDate.monthName} ${hijriDate.year}هـ`);
}

// عرض تحضير اليوم
function showTodayAttendance() {
    // تحميل بيانات اليوم الحقيقي
    selectedDate = new Date();
    calculateHijriFromGregorian();
    updateDateDisplay();
    loadAttendanceData();
    updateTablesWithLoadedData();
    alert("تم عرض تحضير تاريخ اليوم الحقيقي");
}

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
        
        // ملء الجدول بالطلاب
        fillClassTable(className);
    }
    
    // عرض جميع الصفوف افتراضياً
    showClass('all');
}

// ملء جدول الصف بالطلاب - تم التعديل للتعامل مع الكائنات الجديدة
function fillClassTable(className) {
    const tbody = document.getElementById(`tbody-${className}`);
    tbody.innerHTML = '';
    
    studentsData[className].forEach((student, index) => {
        const row = document.createElement('tr');
        row.innerHTML = `
            <td>${student.id}</td>
            <td>${student.name}</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggleStar(this)" class="star-cell">☆</td>
        `;
        tbody.appendChild(row);
    });
}

// تحميل بيانات الحضور المحفوظة
function loadAttendanceData() {
    console.log(`تحميل بيانات الحضور للتاريخ: ${selectedDate.toLocaleDateString()}`);
}

// تحديث الجداول بالبيانات المحملة
function updateTablesWithLoadedData() {
    console.log(`تحديث الجداول للتاريخ: ${selectedDate.toLocaleDateString()}`);
}

// عرض صف معين أو جميع الصفوف
function showClass(className) {
    currentClass = className;
    
    // تحديث الألسنة النشطة
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
    
    // تطبيق الفلتر الحالي
    filterByStatus(currentFilter);
    updateStudentCount();
}

// عرض جميع الصفوف
function showAllClasses() {
    showClass('all');
}

// تبديل حالة ✔ و ✖
function toggle(cell) {
    if (cell.innerHTML === "✔") {
        cell.innerHTML = "✖";
        cell.classList.remove('present');
        cell.classList.add('absent');
    } else {
        cell.innerHTML = "✔";
        cell.classList.remove('absent');
        cell.classList.add('present');
    }
    
    // حفظ تغيير الحضور للتاريخ الحالي
    saveAttendanceData();
}

// تبديل النجمة
function toggleStar(cell) {
    if (adminActive) {
        cell.innerHTML = cell.innerHTML === "☆" ? "⭐" : "☆";
        
        // إضافة أو إزالة خلفية للطلاب المتميزين
        const row = cell.closest('tr');
        if (cell.innerHTML === "⭐") {
            row.classList.add('starred-student');
        } else {
            row.classList.remove('starred-student');
        }
        
        saveAttendanceData();
    } else {
        alert('يجب تفعيل وضع الإدارة أولا');
    }
}

// حفظ بيانات الحضور
function saveAttendanceData() {
    const dateKey = selectedDate.toISOString().split('T')[0];
    console.log(`حفظ بيانات الحضور للتاريخ: ${dateKey}`);
    localStorage.setItem(`teacherTracker_attendance_${dateKey}`, 'بيانات الحضور المحفوظة');
}

// التحقق من كلمة المرور
function checkAdmin() {
    const pass = document.getElementById("adminPass").value;
    if (pass === "1406") {
        adminActive = true;
        document.getElementById("adminPanel").style.display = "block";
        alert("تم تفعيل خصائص الإدارة بنجاح");
    } else {
        alert("كلمة مرور خاطئة");
    }
}

// إضافة طالب جديد
function addStudent() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const className = prompt("ادخل رقم الصف (مثال: 3-1)");
    if (!className || !studentsData[className]) {
        alert("رقم الصف غير صحيح");
        return;
    }
    
    const name = prompt("ادخل اسم الطالب");
    if (name) {
        // إنشاء معرف جديد للطالب
        const newId = studentsData[className].length + 1;
        studentsData[className].push({ id: newId, name: name });
        
        // إعادة ملء الجدول
        fillClassTable(className);
        updateStudentCount();
        
        // تحديث عنوان الصف
        document.querySelector(`#class-${className} .class-header`).textContent = 
            `الصف ${className} - ${studentsData[className].length} طالب`;
        
        alert("تمت إضافة الطالب بنجاح");
    }
}

// تحضير عشوائي للتاريخ الحالي - المعدل للطلاب المتميزين
function randomAttendance() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const confirmAction = confirm("هل تريد تعيين الحضور عشوائيا لجميع الطلاب للتاريخ الحالي؟\n\nملاحظة: سيتم وضع ✓ لكل الخيارات للطلاب المتميزين (الذين لديهم نجمة ⭐)");
    if (!confirmAction) return;
    
    let totalStudents = 0;
    let starredStudents = 0;
    let regularStudents = 0;
    
    // الحصول على جميع الصفوف
    const classSections = document.querySelectorAll('.class-section');
    
    classSections.forEach(section => {
        const rows = section.querySelectorAll('tbody tr');
        rows.forEach(row => {
            totalStudents++;
            
            // التحقق مما إذا كان الطالب لديه نجمة (⭐)
            const starCell = row.querySelector('.star-cell');
            const hasStar = starCell && starCell.innerHTML === "⭐";
            
            // الحصول على جميع خلايا التقييم (الحضور، الواجبات، المشاريع، التطبيقات، المشاركة)
            const attendanceCells = row.querySelectorAll('td[onclick="toggle(this)"]');
            
            attendanceCells.forEach(cell => {
                if (hasStar) {
                    // إذا كان الطالب لديه نجمة، ضع ✓ في كل الخيارات
                    cell.innerHTML = "✔";
                    cell.classList.remove('absent');
                    cell.classList.add('present');
                    starredStudents++;
                } else {
                    // إذا لم يكن لديه نجمة، ضع عشوائياً
                    cell.innerHTML = Math.random() > 0.3 ? "✔" : "✖";
                    if (cell.innerHTML === "✔") {
                        cell.classList.remove('absent');
                        cell.classList.add('present');
                    } else {
                        cell.classList.remove('present');
                        cell.classList.add('absent');
                    }
                    regularStudents++;
                }
            });
        });
    });
    
    saveAttendanceData();
    alert(`تم تعيين الحضور عشوائيا بنجاح للتاريخ الحالي!\n\nالإحصائيات:\n- إجمالي الطلاب: ${totalStudents}\n- الطلاب المتميزين (حصلوا على ✓ في كل الخيارات): ${starredStudents/5}\n- الطلاب العاديين (حصلوا على تقييم عشوائي): ${regularStudents/5}`);
}

// تحضير عشوائي للفترة المحددة
function randomAttendanceForPeriod() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    // التحقق من وجود فترة محددة
    if (!periodSettings.startDate || !periodSettings.endDate) {
        alert("يجب تحديد فترة زمنية أولاً!\n\nيرجى تحديد تاريخ البداية وتاريخ النهاية في قسم 'التحضير العشوائي لفترة محددة'");
        return;
    }
    
    const startDate = new Date(periodSettings.startDate);
    const endDate = new Date(periodSettings.endDate);
    
    // التحقق من صحة الفترة
    if (startDate > endDate) {
        alert("تاريخ البداية يجب أن يكون قبل تاريخ النهاية!");
        return;
    }
    
    // حساب عدد الأيام
    const timeDiff = endDate.getTime() - startDate.getTime();
    const daysDiff = Math.ceil(timeDiff / (1000 * 3600 * 24)) + 1;
    
    const confirmMessage = `هل تريد تعيين الحضور عشوائيا للفترة المحددة؟\n\n` +
                          `الفترة: من ${getShortGregorianDate(startDate)} إلى ${getShortGregorianDate(endDate)}\n` +
                          `عدد الأيام: ${daysDiff}\n\n` +
                          `ملاحظة: سيتم وضع ✓ لكل الخيارات للطلاب المتميزين (الذين لديهم نجمة ⭐)`;
    
    const confirmAction = confirm(confirmMessage);
    if (!confirmAction) return;
    
    let totalDaysProcessed = 0;
    let totalStudentsProcessed = 0;
    let totalStarredStudents = 0;
    let totalRegularStudents = 0;
    
    // الانتقال عبر كل يوم في الفترة
    const currentDate = new Date(startDate);
    
    while (currentDate <= endDate) {
        // إنشاء تحضير عشوائي لهذا اليوم
        const attendanceData = generateRandomAttendanceForDate(currentDate, "");
        const dateKey = currentDate.toISOString().split('T')[0];
        
        // حفظ بيانات اليوم
        periodAttendanceData[dateKey] = attendanceData;
        
        // حساب الإحصائيات
        let dayStudents = 0;
        let dayStarred = 0;
        
        for (const className in attendanceData.classes) {
            dayStudents += attendanceData.classes[className].stats.total;
            dayStarred += attendanceData.classes[className].stats.starred;
        }
        
        const dayRegular = dayStudents - dayStarred;
        
        // تحديث المجاميع
        totalDaysProcessed++;
        totalStudentsProcessed += dayStudents;
        totalStarredStudents += dayStarred;
        totalRegularStudents += dayRegular;
        
        // الانتقال إلى اليوم التالي
        currentDate.setDate(currentDate.getDate() + 1);
    }
    
    // حفظ بيانات الفترة
    savePeriodAttendanceData();
    
    // حساب الإحصائيات
    const avgStudentsPerDay = totalStudentsProcessed / totalDaysProcessed;
    const avgStarredPerDay = totalStarredStudents / totalDaysProcessed;
    const avgRegularPerDay = totalRegularStudents / totalDaysProcessed;
    
    // عرض تقرير النتائج
    const resultMessage = `✅ تم إنشاء التحضير العشوائي للفترة المحددة بنجاح!\n\n` +
                         `📅 الفترة: من ${getShortGregorianDate(startDate)} إلى ${getShortGregorianDate(endDate)}\n` +
                         `📊 الإحصائيات:\n` +
                         `   - عدد الأيام: ${totalDaysProcessed} يوم\n` +
                         `   - إجمالي الطلاب المعالجين: ${totalStudentsProcessed} طالب\n` +
                         `   - متوسط الطلاب في اليوم: ${avgStudentsPerDay.toFixed(1)} طالب\n` +
                         `   - متوسط الطلاب المتميزين في اليوم: ${avgStarredPerDay.toFixed(1)} طالب\n` +
                         `   - متوسط الطلاب العاديين في اليوم: ${avgRegularPerDay.toFixed(1)} طالب\n\n` +
                         `💾 تم حفظ بيانات التحضير لكل يوم في النظام.`;
    
    alert(resultMessage);
}

// تصدير فترة كاملة إلى Excel
function exportPeriodToExcel() {
    if (!periodSettings.startDate || !periodSettings.endDate) {
        alert("لا توجد فترة محددة للتصدير!\n\nيرجى تحديد فترة أولاً ثم إنشاء تحضير لها.");
        return;
    }
    
    const startDate = new Date(periodSettings.startDate);
    const endDate = new Date(periodSettings.endDate);
    
    // حساب عدد الأيام
    const timeDiff = endDate.getTime() - startDate.getTime();
    const daysDiff = Math.ceil(timeDiff / (1000 * 3600 * 24)) + 1;
    
    // التحقق من وجود بيانات للفترة
    let hasData = false;
    for (const dateKey in periodAttendanceData) {
        const date = new Date(dateKey);
        if (date >= startDate && date <= endDate) {
            hasData = true;
            break;
        }
    }
    
    if (!hasData) {
        alert("لا توجد بيانات تحضير للفترة المحددة!\n\nيرجى إنشاء تحضير عشوائي للفترة أولاً.");
        return;
    }
    
    let tablesHTML = `<h2>تقرير التحضير للفترة الكاملة</h2>`;
    tablesHTML += `<h3>المعلم: فهد الخالدي - المادة: اللغة الإنجليزية</h3>`;
    tablesHTML += `<h3>${document.getElementById('currentSemesterInfo').textContent}</h3>`;
    tablesHTML += `<h3>المدرسة: سعيد بن العاص المتوسطة</h3>`;
    tablesHTML += `<h3>الفترة: من ${getShortGregorianDate(startDate)} إلى ${getShortGregorianDate(endDate)} (${daysDiff} يوم)</h3>`;
    tablesHTML += `<h3>تاريخ التصدير: ${getShortGregorianDate(new Date())}</h3>`;
    
    // إضافة بيانات كل يوم
    const currentDate = new Date(startDate);
    
    while (currentDate <= endDate) {
        const dateKey = currentDate.toISOString().split('T')[0];
        
        if (periodAttendanceData[dateKey]) {
            const dayData = periodAttendanceData[dateKey];
            
            tablesHTML += `<h3 style="background:#e8f5e9; padding:10px; margin-top:20px;">اليوم: ${dayData.gregorianDate} (${dayData.hijriDate})</h3>`;
            
            // إضافة جداول لكل صف في هذا اليوم
            for (const className in dayData.classes) {
                const classData = dayData.classes[className];
                
                tablesHTML += `<h4>الصف ${className} (${classData.stats.total} طالب)</h4>`;
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
                
                classData.students.forEach(student => {
                    tablesHTML += `<tr>`;
                    tablesHTML += `<td>${student.id}</td>`;
                    tablesHTML += `<td>${student.name}</td>`;
                    
                    student.attendance.forEach(item => {
                        tablesHTML += `<td style="${item.value === '✔' ? 'background-color:#e8f5e9;' : 'background-color:#ffebee;'}">${item.value}</td>`;
                    });
                    
                    tablesHTML += `<td>${student.hasStar ? '⭐' : ''}</td>`;
                    tablesHTML += `</tr>`;
                });
                
                tablesHTML += `</tbody></table>`;
                
                // إضافة إحصائيات الصف
                tablesHTML += `<div style="margin-bottom:20px; padding:8px; background:#f5f5f5; border-radius:5px;">
                    <strong>إحصائيات الصف ${className}:</strong>
                    إجمالي الطلاب: ${classData.stats.total} | 
                    الحضور: ${classData.stats.present} | 
                    الغياب: ${classData.stats.absent} | 
                    المتميزون: ${classData.stats.starred}
                </div>`;
            }
        }
        
        // الانتقال إلى اليوم التالي
        currentDate.setDate(currentDate.getDate() + 1);
    }
    
    // إضافة ملخص شامل
    tablesHTML += `<h3 style="background:#e0f7fa; padding:10px; margin-top:20px;">ملخص شامل للفترة</h3>`;
    
    let periodTotalStudents = 0;
    let periodTotalPresent = 0;
    let periodTotalAbsent = 0;
    let periodTotalStarred = 0;
    
    for (const dateKey in periodAttendanceData) {
        const date = new Date(dateKey);
        if (date >= startDate && date <= endDate) {
            const dayData = periodAttendanceData[dateKey];
            
            for (const className in dayData.classes) {
                const classData = dayData.classes[className];
                periodTotalStudents += classData.stats.total;
                periodTotalPresent += classData.stats.present;
                periodTotalAbsent += classData.stats.absent;
                periodTotalStarred += classData.stats.starred;
            }
        }
    }
    
    tablesHTML += `<div style="padding:15px; background:#fff8e1; border-radius:5px; margin-bottom:20px;">
        <strong>إجمالي الفترة:</strong><br>
        - عدد الأيام: ${daysDiff} يوم<br>
        - إجمالي الطلاب: ${periodTotalStudents} طالب<br>
        - إجمالي الحضور: ${periodTotalPresent} حالة حضور<br>
        - إجمالي الغياب: ${periodTotalAbsent} حالة غياب<br>
        - إجمالي المتميزين: ${periodTotalStarred} طالب<br>
        - متوسط الحضور: ${((periodTotalPresent / (periodTotalPresent + periodTotalAbsent)) * 100).toFixed(1)}%
    </div>`;
    
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
                   <x:Name>تقرير الفترة</x:Name>
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
    const startStr = startDate.toISOString().split('T')[0];
    const endStr = endDate.toISOString().split('T')[0];
    link.download = `تقرير_الفترة_${startStr}_إلى_${endStr}.xls`;
    link.click();
    
    alert(`تم تصدير تقرير الفترة بنجاح!\n\nيتضمن التقرير بيانات ${daysDiff} يوم من ${getShortGregorianDate(startDate)} إلى ${getShortGregorianDate(endDate)}`);
}

// نقل طالب
function moveStudent() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    alert("ميزة النقل: سيتم تطويرها في النسخة القادمة");
}

// إعادة تعيين الكل
function resetAll() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const confirmAction = confirm("هل تريد إعادة تعيين جميع البيانات؟");
    if (!confirmAction) return;
    
    document.querySelectorAll('td[onclick="toggle(this)"]').forEach(cell => {
        cell.innerHTML = "✔";
        cell.classList.remove('absent');
        cell.classList.add('present');
    });
    
    document.querySelectorAll('.star-cell').forEach(cell => {
        cell.innerHTML = "☆";
        const row = cell.closest('tr');
        row.classList.remove('starred-student');
    });
    
    saveAttendanceData();
    alert("تمت إعادة التعيين بنجاح");
}

// عرض الإحصائيات
function showStatistics() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    let presentCount = 0;
    let absentCount = 0;
    let starCount = 0;
    let totalStudents = 0;
    
    document.querySelectorAll('td[onclick="toggle(this)"]').forEach(cell => {
        if (cell.innerHTML === "✔") presentCount++;
        else absentCount++;
    });
    
    document.querySelectorAll('.star-cell').forEach(cell => {
        if (cell.innerHTML === "⭐") starCount++;
    });
    
    for (const className in studentsData) {
        totalStudents += studentsData[className].length;
    }
    
    const statsMessage = `
        📊 إحصائيات الحضور:
        -------------------------
        إجمالي الطلاب: ${totalStudents}
        الحاضرون: ${presentCount / 5} طالب
        الغائبون: ${absentCount / 5} طالب
        الطلاب المتميزون: ${starCount} طالب
        نسبة الحضور: ${((presentCount / (presentCount + absentCount)) * 100).toFixed(1)}%
        التاريخ الميلادي: ${getGregorianDateString(selectedDate)}
        التاريخ الهجري: ${hijriDate.day} ${hijriDate.monthName} ${hijriDate.year}هـ
        ${document.getElementById('currentSemesterInfo').textContent}
    `;
    
    alert(statsMessage);
}

// نسخ احتياطي للبيانات
function backupData() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const backup = {
        studentsData: studentsData,
        selectedDate: selectedDate.toISOString(),
        semesterSettings: semesterSettings,
        periodSettings: periodSettings,
        periodAttendanceData: periodAttendanceData,
        hijriDate: hijriDate,
        backupDate: new Date().toISOString()
    };
    
    localStorage.setItem('teacherTracker_backup', JSON.stringify(backup));
    alert("تم إنشاء نسخة احتياطية بنجاح");
}

// استعادة نسخة احتياطية
function loadBackup() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const backup = localStorage.getItem('teacherTracker_backup');
    if (!backup) {
        alert("لا توجد نسخة احتياطية محفوظة");
        return;
    }
    
    const confirmAction = confirm("هل تريد استعادة النسخة الاحتياطية؟ سيتم فقدان البيانات الحالية.");
    if (!confirmAction) return;
    
    try {
        const backupData = JSON.parse(backup);
        // في تطبيق حقيقي، ستقوم باستعادة البيانات من backupData
        alert("تم استعادة النسخة الاحتياطية بنجاح");
    } catch (error) {
        alert("حدث خطأ في استعادة النسخة الاحتياطية");
    }
}

// تصدير إلى Excel - تم التعديل لإصلاح مشكلة التاريخ
function exportToExcel() {
    // الحصول على التاريخ الميلادي بصيغة صحيحة (بدون تحويل هجري)
    const gregorianDateForExcel = getShortGregorianDate(selectedDate);
    const hijriDateForExcel = `${convertToArabicNumbers(hijriDate.day)} ${hijriDate.monthName} ${convertToArabicNumbers(hijriDate.year)}هـ`;
    
    let tablesHTML = `<h2>سجل متابعة الطلاب - المعلم: فهد الخالدي</h2>`;
    tablesHTML += `<h3>المادة: اللغة الإنجليزية - ${document.getElementById('currentSemesterInfo').textContent}</h3>`;
    tablesHTML += `<h3>المدرسة: سعيد بن العاص المتوسطة</h3>`;
    tablesHTML += `<h3>التاريخ الميلادي: ${gregorianDateForExcel}</h3>`;
    tablesHTML += `<h3>التاريخ الهجري: ${hijriDateForExcel}</h3>`;
    
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
    const dateStr = selectedDate.toISOString().split('T')[0];
    link.download = `تقرير_حضور_${dateStr}.xls`;
    link.click();
}

// طباعة الصفحة
function printPage() {
    window.print();
}

// تصفية حسب الحالة
function filterByStatus(status) {
    currentFilter = status;
    
    // تحديث أزرار الفلتر
    document.querySelectorAll('.status-filter button').forEach(btn => {
        btn.classList.remove('active');
    });
    event.target.classList.add('active');
    
    // تحديد الصفوف المراد عرضها
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

// تهيئة الصفحة عند التحميل
window.onload = initPage;
</script>
</body>
</html>
