# INSIGHT-Platform-_-Mr.-Samuel-Gergies
من أجل غد أفضل لأبطال متلازمة داون وطيف التوحد
[index.html](https://github.com/user-attachments/files/35369130/index.html)
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>منصة مبادرة INSIGHT لذوي الهمم | Samuel Gergies</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.1/dist/chart.umd.min.js"></script>
  <script src="https://unpkg.com/lucide@0.460.0/dist/umd/lucide.min.js"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800&family=Inter:wght@400;600;700&display=swap');
    body {
      font-family: 'Cairo', 'Inter', system-ui, -apple-system, sans-serif;
      background-color: #f8fafc;
      color: #0f172a;
    }
    .tab-btn.active {
      background-color: #0f766e;
      color: #ffffff;
      box-shadow: 0 4px 12px rgba(15, 118, 110, 0.25);
    }
    .pill-btn.active {
      background-color: #0f766e;
      color: #ffffff;
      border-color: #0f766e;
    }
    @media print {
      header, nav, .no-print { display: none !important; }
      body { background: #ffffff; }
    }
  </style>
</head>
<body class="min-h-screen flex flex-col">

  <!-- Online-Only Connection Gate -->
  <div id="offline-gate" class="fixed inset-0 z-50 hidden items-center justify-center bg-slate-900/90 p-6 text-center backdrop-blur-sm">
    <div class="max-w-md rounded-2xl bg-white p-6 shadow-2xl space-y-4">
      <div class="mx-auto flex h-14 w-14 items-center justify-center rounded-full bg-amber-100 text-amber-700">
        <i data-lucide="wifi-off" class="h-7 w-7"></i>
      </div>
      <h2 class="text-lg font-extrabold text-slate-900">يلزم الاتصال بالإنترنت</h2>
      <p class="text-sm text-slate-600 leading-relaxed">
        تعمل منصة مبادرة <strong>INSIGHT</strong> التفاعلية عبر الإنترنت لضمان تحميل المكتبات التفاعلية والوصول إلى المراجع النفسية والاسترشادية المعتمدة. يرجى التأكد من اتصالك بالإنترنت للمتابعة.
      </p>
      <button type="button" id="retry-online-btn" class="w-full rounded-xl bg-teal-700 py-2.5 text-sm font-bold text-white hover:bg-teal-800">
        إعادة التحقق من الاتصال
      </button>
    </div>
  </div>

  <!-- Toast Notification -->
  <div id="toast" class="fixed bottom-5 left-5 z-50 hidden items-center gap-2 rounded-xl bg-slate-900 px-4 py-3 text-sm font-semibold text-white shadow-xl transition-all">
    <i data-lucide="check-circle-2" class="h-4 w-4 text-emerald-400"></i>
    <span id="toast-msg">تم النسخ بنجاح</span>
  </div>

  <!-- Header -->
  <header class="bg-gradient-to-l from-teal-900 via-teal-800 to-slate-900 text-white shadow-lg">
    <div class="mx-auto max-w-7xl px-4 py-5 sm:px-6 lg:px-8">
      <div class="flex flex-col gap-4 md:flex-row md:items-center md:justify-between">
        <div class="flex items-center gap-4">
          <div class="flex h-14 w-14 shrink-0 items-center justify-center rounded-2xl bg-white/10 ring-1 ring-white/25 backdrop-blur">
            <i data-lucide="sparkles" class="h-7 w-7 text-amber-300"></i>
          </div>
          <div>
            <div class="flex flex-wrap items-center gap-2">
              <h1 class="text-xl font-extrabold tracking-tight sm:text-2xl">منصة مبادرة INSIGHT لذوي الهمم</h1>
              <span class="rounded-full bg-amber-400/20 px-3 py-0.5 text-xs font-bold text-amber-200 ring-1 ring-amber-300/30">Inclusion • Growth • Holistic Training</span>
            </div>
            <p class="mt-1 text-sm text-teal-100">المرجع التفاعلي لمعلمي ومديري مراكز التربية الخاصة (متلازمة داون وطيف التوحد) — الإسكندرية</p>
          </div>
        </div>
        <div class="flex items-center gap-3 self-start rounded-xl bg-white/10 px-4 py-2.5 ring-1 ring-white/20 md:self-auto">
          <i data-lucide="award" class="h-5 w-5 text-amber-300"></i>
          <div class="text-right">
            <div class="text-xs text-teal-200">مؤسس ومدير المبادرة</div>
            <div class="text-sm font-bold text-white">Samuel Gergies</div>
          </div>
        </div>
      </div>

      <!-- Navigation Tabs -->
      <nav class="mt-5 flex flex-wrap gap-2" aria-label="التنقل الرئيسي">
        <button type="button" data-tab="workshops" class="tab-btn active flex items-center gap-2 rounded-xl bg-white/10 px-4 py-2.5 text-sm font-bold text-teal-50 transition hover:bg-white/20">
          <i data-lucide="calendar-check" class="h-4 w-4"></i>
          <span>الورش المنفذة والإحصائيات</span>
        </button>
        <button type="button" data-tab="references" class="tab-btn flex items-center gap-2 rounded-xl bg-white/10 px-4 py-2.5 text-sm font-bold text-teal-50 transition hover:bg-white/20">
          <i data-lucide="book-open-check" class="h-4 w-4"></i>
          <span>المراجع النفسية والاسترشادية</span>
        </button>
        <button type="button" data-tab="lesson-prep" class="tab-btn flex items-center gap-2 rounded-xl bg-white/10 px-4 py-2.5 text-sm font-bold text-teal-50 transition hover:bg-white/20">
          <i data-lucide="clipboard-list" class="h-4 w-4"></i>
          <span>مساعد الشرح وتحضير الدروس</span>
        </button>
        <button type="button" data-tab="admin-kit" class="tab-btn flex items-center gap-2 rounded-xl bg-white/10 px-4 py-2.5 text-sm font-bold text-teal-50 transition hover:bg-white/20">
          <i data-lucide="folder-kanban" class="h-4 w-4"></i>
          <span>الإدارة والسكرتارية</span>
        </button>
        <button type="button" data-tab="ppt-events" class="tab-btn flex items-center gap-2 rounded-xl bg-white/10 px-4 py-2.5 text-sm font-bold text-teal-50 transition hover:bg-white/20">
          <i data-lucide="presentation" class="h-4 w-4"></i>
          <span>عروض PPT والاحتفالات</span>
        </button>
        <button type="button" data-tab="smart-advisor" class="tab-btn flex items-center gap-2 rounded-xl bg-white/10 px-4 py-2.5 text-sm font-bold text-teal-50 transition hover:bg-white/20">
          <i data-lucide="bot" class="h-4 w-4"></i>
          <span>مستشارك الذكي لحل المشكلات الطلابية</span>
        </button>
        <button type="button" data-tab="directors-hub" class="tab-btn flex items-center gap-2 rounded-xl bg-white/10 px-4 py-2.5 text-sm font-bold text-teal-50 transition hover:bg-white/20">
          <i data-lucide="shield-check" class="h-4 w-4"></i>
          <span>تذليل عقبات المدراء والوكلاء</span>
        </button>
        <button type="button" data-tab="global-pd" class="tab-btn flex items-center gap-2 rounded-xl bg-white/10 px-4 py-2.5 text-sm font-bold text-teal-50 transition hover:bg-white/20">
          <i data-lucide="globe" class="h-4 w-4"></i>
          <span>التنمية المهنية للمعلمين (ورش عالمية)</span>
        </button>
      </nav>
    </div>
  </header>

  <!-- Main Content -->
  <main class="mx-auto w-full max-w-7xl flex-1 px-4 py-6 sm:px-6 lg:px-8">

    <!-- TAB 1: WORKSHOPS & STATS -->
    <section id="tab-workshops" class="tab-panel space-y-6">
      <!-- KPI Row -->
      <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 lg:grid-cols-4">
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm">
          <div class="flex items-center justify-between">
            <span class="text-sm font-semibold text-slate-500">إجمالي الورش المنفذة</span>
            <span class="rounded-lg bg-teal-50 p-2 text-teal-700"><i data-lucide="layers" class="h-5 w-5"></i></span>
          </div>
          <div id="kpi-workshops-count" class="mt-3 text-3xl font-extrabold text-slate-900">2</div>
          <p class="mt-1 text-xs text-slate-500">في الركن الأمريكي بمؤسسة أميدست — الإسكندرية</p>
        </div>

        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm">
          <div class="flex items-center justify-between">
            <span class="text-sm font-semibold text-slate-500">المراكز والمدارس المشاركة</span>
            <span class="rounded-lg bg-indigo-50 p-2 text-indigo-700"><i data-lucide="building-2" class="h-5 w-5"></i></span>
          </div>
          <div class="mt-3 text-3xl font-extrabold text-slate-900">4</div>
          <p class="mt-1 text-xs text-slate-500">سان مارك، سانت جان أنتيد، سان جوزيف، Future Schools</p>
        </div>

        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm">
          <div class="flex items-center justify-between">
            <span class="text-sm font-semibold text-slate-500">مسجلو الورشة الثانية (يونيو ٢٠٢٦)</span>
            <span class="rounded-lg bg-amber-50 p-2 text-amber-700"><i data-lucide="users" class="h-5 w-5"></i></span>
          </div>
          <div id="kpi-participants-count" class="mt-3 text-3xl font-extrabold text-slate-900">23</div>
          <p class="mt-1 text-xs text-slate-500">معلمون، مشرفون، ومديرو مراكز تربية خاصة</p>
        </div>

        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm">
          <div class="flex items-center justify-between">
            <span class="text-sm font-semibold text-slate-500">المحاور التدريبية الرئيسية</span>
            <span class="rounded-lg bg-emerald-50 p-2 text-emerald-700"><i data-lucide="compass" class="h-5 w-5"></i></span>
          </div>
          <div class="mt-3 text-3xl font-extrabold text-slate-900">4</div>
          <p class="mt-1 text-xs text-slate-500">UDL، الذكاء الاصطناعي، السلوك التنظيمي، الابتكار الإداري</p>
        </div>
      </div>

      <!-- Workshops Timeline + Chart -->
      <div class="grid grid-cols-1 gap-6 lg:grid-cols-3">
        <!-- Workshop Cards (2 cols) -->
        <div class="space-y-4 lg:col-span-2">
          <div class="flex flex-wrap items-center justify-between gap-3">
            <h2 class="text-lg font-extrabold text-slate-900">سجل الورش التدريبية المنفذة</h2>
            <button type="button" id="toggle-add-workshop-btn" class="inline-flex items-center gap-1.5 rounded-xl bg-teal-700 px-3.5 py-2 text-xs font-bold text-white shadow-sm transition hover:bg-teal-800">
              <i data-lucide="plus" class="h-4 w-4"></i>
              <span>إضافة ورشة جديدة للسجل</span>
            </button>
          </div>

          <!-- Add Workshop Inline Form -->
          <form id="add-workshop-form" class="hidden rounded-2xl border border-teal-200 bg-teal-50/60 p-4 space-y-3">
            <div class="text-sm font-bold text-teal-900">تسجيل ورشة جديدة في المبادرة</div>
            <div class="grid grid-cols-1 gap-3 sm:grid-cols-2">
              <input type="text" id="new-ws-title" required placeholder="عنوان الورشة" class="rounded-xl border border-slate-300 bg-white px-3 py-2 text-sm focus:border-teal-600 focus:outline-none" />
              <input type="text" id="new-ws-date" required placeholder="التاريخ والوقت (مثال: الأحد ١٥ نوفمبر ٢٠٢٦)" class="rounded-xl border border-slate-300 bg-white px-3 py-2 text-sm focus:border-teal-600 focus:outline-none" />
              <input type="text" id="new-ws-venue" required placeholder="المكان (مثال: مقر أميدست الإسكندرية)" class="rounded-xl border border-slate-300 bg-white px-3 py-2 text-sm focus:border-teal-600 focus:outline-none" />
              <input type="number" id="new-ws-count" min="1" value="25" placeholder="عدد المشاركين" class="rounded-xl border border-slate-300 bg-white px-3 py-2 text-sm focus:border-teal-600 focus:outline-none" />
            </div>
            <textarea id="new-ws-topics" rows="2" required placeholder="المحاور الرئيسية للورشة..." class="w-full rounded-xl border border-slate-300 bg-white px-3 py-2 text-sm focus:border-teal-600 focus:outline-none"></textarea>
            <div class="flex justify-end gap-2">
              <button type="button" id="cancel-add-workshop-btn" class="rounded-xl border border-slate-300 bg-white px-3 py-1.5 text-xs font-bold text-slate-700 hover:bg-slate-50">إلغاء</button>
              <button type="submit" class="rounded-xl bg-teal-700 px-4 py-1.5 text-xs font-bold text-white hover:bg-teal-800">حفظ الورشة</button>
            </div>
          </form>

          <div id="workshops-list" class="space-y-4"></div>
        </div>

        <!-- Chart Card -->
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm flex flex-col justify-between">
          <div>
            <h3 class="text-base font-extrabold text-slate-900">توزيع المسجلين حسب الجهة</h3>
            <p class="mt-1 text-xs text-slate-500">بيانات استمارة الورشة الثانية (٢٨ يونيو ٢٠٢٦ — ٢٣ مشاركاً)</p>
            <div class="relative mt-4 h-72">
              <canvas id="centersChart"></canvas>
            </div>
          </div>
          <div class="mt-4 rounded-xl bg-slate-50 p-3 text-xs text-slate-600 leading-relaxed">
            <strong class="text-slate-800">التخصصات المشاركة:</strong> تخاطب، تعديل سلوك، تدخل مبكر، صعوبات تعلم، تربية فنية ورياضية، أخصائي نفسي واجتماعي، نفس حركي، وإدارة مراكز.
          </div>
        </div>
      </div>
    </section>

    <!-- TAB 2: PSYCHOLOGICAL & PEDAGOGICAL REFERENCES -->
    <section id="tab-references" class="tab-panel hidden space-y-6">
      <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm">
        <div class="flex flex-col gap-4 md:flex-row md:items-center md:justify-between">
          <div>
            <h2 class="text-lg font-extrabold text-slate-900">المكتبة النفسية والاسترشادية (داون وتوحد)</h2>
            <p class="mt-1 text-sm text-slate-600">إرشادات علمية ونفسية موثقة من منظمات دولية لدعم المعلمين والمديرين في الشرح والتدخل التربوي.</p>
          </div>
          <div class="relative w-full md:w-72">
            <i data-lucide="search" class="pointer-events-none absolute right-3 top-2.5 h-4 w-4 text-slate-400"></i>
            <input type="text" id="ref-search" placeholder="ابحث في الاستراتيجيات أو المراجع..." class="w-full rounded-xl border border-slate-300 bg-slate-50 py-2 pr-9 pl-3 text-sm focus:border-teal-600 focus:bg-white focus:outline-none" />
          </div>
        </div>

        <div class="mt-4 flex flex-wrap gap-2">
          <button type="button" data-ref-filter="all" class="pill-btn active rounded-full border border-slate-300 px-4 py-1.5 text-xs font-bold transition">الكل</button>
          <button type="button" data-ref-filter="down" class="pill-btn rounded-full border border-slate-300 px-4 py-1.5 text-xs font-bold text-slate-700 transition hover:bg-slate-100">متلازمة داون (Down Syndrome)</button>
          <button type="button" data-ref-filter="autism" class="pill-btn rounded-full border border-slate-300 px-4 py-1.5 text-xs font-bold text-slate-700 transition hover:bg-slate-100">طيف التوحد (Autism)</button>
          <button type="button" data-ref-filter="udl" class="pill-btn rounded-full border border-slate-300 px-4 py-1.5 text-xs font-bold text-slate-700 transition hover:bg-slate-100">التصميم الشامل للتعلم (UDL 3.0)</button>
          <button type="button" data-ref-filter="admin" class="pill-btn rounded-full border border-slate-300 px-4 py-1.5 text-xs font-bold text-slate-700 transition hover:bg-slate-100">إدارة الدمج والسياسات</button>
        </div>
      </div>

      <div id="references-grid" class="grid grid-cols-1 gap-5 md:grid-cols-2"></div>

      <!-- Free Books & Recent Research Library (AR / EN / FR) -->
      <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm space-y-4">
        <div class="flex flex-col gap-3 md:flex-row md:items-center md:justify-between">
          <div>
            <h2 class="text-lg font-extrabold text-slate-900">مكتبة الكتب المجانية والأبحاث الحديثة (عربي • إنجليزي • فرنسي)</h2>
            <p class="mt-1 text-sm text-slate-600">مراجع وكتب مفتوحة الوصول وأحدث الأبحاث العلمية (٢٠٢٤–٢٠٢٦) حول طيف التوحد ومتلازمة داون.</p>
          </div>
          <div class="relative w-full md:w-72">
            <i data-lucide="search" class="pointer-events-none absolute right-3 top-2.5 h-4 w-4 text-slate-400"></i>
            <input type="text" id="lib-search" placeholder="ابحث في الكتب والأبحاث..." class="w-full rounded-xl border border-slate-300 bg-slate-50 py-2 pr-9 pl-3 text-sm focus:border-teal-600 focus:bg-white focus:outline-none" />
          </div>
        </div>

        <div class="flex flex-wrap items-center gap-2 border-b border-slate-100 pb-3">
          <span class="text-xs font-bold text-slate-500 ml-1">اللغة:</span>
          <button type="button" data-lib-lang="all" class="lib-lang-btn rounded-full border border-teal-700 bg-teal-700 px-3.5 py-1 text-xs font-bold text-white transition">جميع اللغات</button>
          <button type="button" data-lib-lang="ar" class="lib-lang-btn rounded-full border border-slate-300 bg-white px-3.5 py-1 text-xs font-bold text-slate-700 transition hover:bg-slate-100">العربية (AR)</button>
          <button type="button" data-lib-lang="en" class="lib-lang-btn rounded-full border border-slate-300 bg-white px-3.5 py-1 text-xs font-bold text-slate-700 transition hover:bg-slate-100">الإنجليزية (EN)</button>
          <button type="button" data-lib-lang="fr" class="lib-lang-btn rounded-full border border-slate-300 bg-white px-3.5 py-1 text-xs font-bold text-slate-700 transition hover:bg-slate-100">الفرنسية (FR)</button>
          <span class="text-xs font-bold text-slate-500 mr-3 ml-1">المجال:</span>
          <select id="lib-topic" class="rounded-xl border border-slate-300 bg-slate-50 px-3 py-1 text-xs font-bold text-slate-700 focus:border-teal-600 focus:outline-none">
            <option value="all">التوحد ومتلازمة داون</option>
            <option value="autism">طيف التوحد فقط</option>
            <option value="down">متلازمة داون فقط</option>
          </select>
        </div>

        <div id="free-library-grid" class="grid grid-cols-1 gap-4 md:grid-cols-2 lg:grid-cols-3"></div>
      </div>
    </section>

    <!-- TAB 3: LESSON & IEP PREPARATION -->
    <section id="tab-lesson-prep" class="tab-panel hidden space-y-6">
      <div class="grid grid-cols-1 gap-6 lg:grid-cols-12">
        <!-- Builder Form -->
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm lg:col-span-5 space-y-4">
          <div class="flex items-center gap-2">
            <span class="rounded-lg bg-teal-50 p-2 text-teal-700"><i data-lucide="wand-2" class="h-5 w-5"></i></span>
            <div>
              <h2 class="text-base font-extrabold text-slate-900">مُعدّ الدروس والخطة الفردية (UDL)</h2>
              <p class="text-xs text-slate-500">صمّم خطة شرح مكيّفة لمتلازمة داون أو التوحد في ثوانٍ</p>
            </div>
          </div>

          <div class="space-y-3">
            <div>
              <label for="lp-condition" class="block text-xs font-bold text-slate-700 mb-1">الفئة المستهدفة</label>
              <select id="lp-condition" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none">
                <option value="down">متلازمة داون (Down Syndrome)</option>
                <option value="autism">طيف التوحد (Autism Spectrum)</option>
                <option value="mixed">فصل دمج مشترك (داون + توحد)</option>
              </select>
            </div>

            <div>
              <label for="lp-domain" class="block text-xs font-bold text-slate-700 mb-1">المجال التدريبي / المهارة</label>
              <select id="lp-domain" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none">
                <option value="speech">التخاطب والتواصل الوظيفي</option>
                <option value="academic">المهارات الأكاديمية (قراءة / حساب مبسط)</option>
                <option value="sensory">التنظيم الحسي والانتباه</option>
                <option value="social">التفاعل الاجتماعي واللعب التعاوني</option>
                <option value="life">المهارات الحياتية والاستقلالية</option>
              </select>
            </div>

            <div class="grid grid-cols-2 gap-3">
              <div>
                <label for="lp-duration" class="block text-xs font-bold text-slate-700 mb-1">مدة الجلسة</label>
                <select id="lp-duration" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none">
                  <option value="20 دقيقة">20 دقيقة (مكثفة)</option>
                  <option value="35 دقيقة" selected>35 دقيقة (قياسية)</option>
                  <option value="45 دقيقة">45 دقيقة (جماعية)</option>
                </select>
              </div>
              <div>
                <label for="lp-udl" class="block text-xs font-bold text-slate-700 mb-1">ركيزة UDL الأساسية</label>
                <select id="lp-udl" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none">
                  <option value="representation">تعدد وسائل العرض (بصري/سمعي/حسي)</option>
                  <option value="engagement">تعدد وسائل الاندماج والدافعية</option>
                  <option value="expression">تعدد وسائل التعبير والاستجابة</option>
                </select>
              </div>
            </div>

            <div>
              <label for="lp-topic" class="block text-xs font-bold text-slate-700 mb-1">موضوع الدرس أو الهدف السلوكي</label>
              <input type="text" id="lp-topic" value="تمييز الألوان والأشكال الهندسية وتوظيفها في الطلب" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none" />
            </div>

            <button type="button" id="generate-lesson-btn" class="w-full rounded-xl bg-teal-700 py-2.5 text-sm font-bold text-white shadow-sm transition hover:bg-teal-800">
              توليد خطة الدرس التكيفية
            </button>
          </div>
        </div>

        <!-- Output Card -->
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm lg:col-span-7 flex flex-col justify-between">
          <div>
            <div class="flex flex-wrap items-center justify-between gap-2 border-b border-slate-100 pb-3">
              <h3 class="text-base font-extrabold text-slate-900">خطة التحضير المقترحة</h3>
              <div class="flex gap-2 no-print">
                <button type="button" id="copy-lesson-btn" class="inline-flex items-center gap-1.5 rounded-lg border border-slate-300 bg-white px-3 py-1.5 text-xs font-bold text-slate-700 hover:bg-slate-50">
                  <i data-lucide="copy" class="h-3.5 w-3.5"></i>
                  <span>نسخ الخطة</span>
                </button>
                <button type="button" id="print-lesson-btn" class="inline-flex items-center gap-1.5 rounded-lg border border-slate-300 bg-white px-3 py-1.5 text-xs font-bold text-slate-700 hover:bg-slate-50">
                  <i data-lucide="printer" class="h-3.5 w-3.5"></i>
                  <span>طباعة</span>
                </button>
              </div>
            </div>
            <div id="lesson-output" class="mt-4 space-y-4 text-sm text-slate-700 leading-relaxed"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- TAB 4: ADMIN & SECRETARIAL KIT -->
    <section id="tab-admin-kit" class="tab-panel hidden space-y-6">
      <div class="grid grid-cols-1 gap-6 lg:grid-cols-12">
        <!-- Left Controls -->
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm lg:col-span-5 space-y-4">
          <h2 class="text-base font-extrabold text-slate-900">حقيبة الإدارة والسكرتارية للمراكز</h2>
          <p class="text-xs text-slate-500">اختر النموذج وعدّل البيانات ليتم تحديث المستند الجاهز للنسخ والطباعة فوراً.</p>

          <div class="grid grid-cols-2 gap-2">
            <button type="button" data-admin-tpl="letter" class="admin-tpl-btn active rounded-xl border border-teal-700 bg-teal-700 px-3 py-2 text-xs font-bold text-white">خطاب شراكة رسمي</button>
            <button type="button" data-admin-tpl="minutes" class="admin-tpl-btn rounded-xl border border-slate-300 bg-white px-3 py-2 text-xs font-bold text-slate-700 hover:bg-slate-50">محضر اجتماع فريق</button>
            <button type="button" data-admin-tpl="parent" class="admin-tpl-btn rounded-xl border border-slate-300 bg-white px-3 py-2 text-xs font-bold text-slate-700 hover:bg-slate-50">تقرير متابعة لولي الأمر</button>
            <button type="button" data-admin-tpl="checklist" class="admin-tpl-btn rounded-xl border border-slate-300 bg-white px-3 py-2 text-xs font-bold text-slate-700 hover:bg-slate-50">قائمة تنظيم ورشة</button>
          </div>

          <div class="space-y-3 pt-2">
            <div>
              <label for="adm-center" class="block text-xs font-bold text-slate-700 mb-1">اسم المركز / المدرسة</label>
              <input type="text" id="adm-center" value="مركز الحياة - مدرسة سان مارك" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none" />
            </div>
            <div>
              <label for="adm-recipient" class="block text-xs font-bold text-slate-700 mb-1">الجهة المستلمة / اسم الطالب / موضوع الاجتماع</label>
              <input type="text" id="adm-recipient" value="إدارة الرعاية والتدريب — مبادرة INSIGHT" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none" />
            </div>
            <div>
              <label for="adm-date" class="block text-xs font-bold text-slate-700 mb-1">التاريخ</label>
              <input type="text" id="adm-date" value="٢٤ نوفمبر ٢٠٢٦" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none" />
            </div>
            <div>
              <label for="adm-notes" class="block text-xs font-bold text-slate-700 mb-1">ملاحظات أو بنود إضافية</label>
              <textarea id="adm-notes" rows="3" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none">تطبيق استراتيجيات UDL والدمج الحسي خلال الفصل الدراسي الحالي، ومراجعة خطط التدخل الفردي.</textarea>
            </div>
          </div>
        </div>

        <!-- Right Preview -->
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm lg:col-span-7 flex flex-col justify-between">
          <div>
            <div class="flex items-center justify-between border-b border-slate-100 pb-3">
              <h3 class="text-base font-extrabold text-slate-900">معاينة المستند الإداري</h3>
              <button type="button" id="copy-admin-btn" class="inline-flex items-center gap-1.5 rounded-lg bg-slate-900 px-3 py-1.5 text-xs font-bold text-white hover:bg-slate-800">
                <i data-lucide="copy" class="h-3.5 w-3.5"></i>
                <span>نسخ النص</span>
              </button>
            </div>
            <div id="admin-preview" class="mt-4 rounded-xl border border-slate-200 bg-slate-50 p-5 text-sm text-slate-800 leading-relaxed whitespace-pre-line"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- TAB 5: PPT & CELEBRATIONS -->
    <section id="tab-ppt-events" class="tab-panel hidden space-y-6">
      <div class="grid grid-cols-1 gap-6 lg:grid-cols-2">
        <!-- PPT Outline Builder -->
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm space-y-4">
          <div class="flex items-center justify-between gap-2">
            <div class="flex items-center gap-2">
              <span class="rounded-lg bg-amber-50 p-2 text-amber-700"><i data-lucide="presentation" class="h-5 w-5"></i></span>
              <div>
                <h2 class="text-base font-extrabold text-slate-900">مصمم هيكل عروض PowerPoint (PPT)</h2>
                <p class="text-xs text-slate-500">اختر نوع العرض للحصول على هيكل شرائح احترافي</p>
              </div>
            </div>
            <button type="button" id="copy-ppt-btn" class="rounded-lg border border-slate-300 px-3 py-1.5 text-xs font-bold text-slate-700 hover:bg-slate-50">نسخ الهيكل</button>
          </div>

          <select id="ppt-type" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm font-semibold focus:border-teal-600 focus:outline-none">
            <option value="impact">عرض تقرير إنجاز وأثر المركز (لمجلس الإدارة / الشركاء)</option>
            <option value="parents">عرض لقاء توعوي لأولياء أمور أطفال داون والتوحد</option>
            <option value="training">عرض ورشة تدريب معلمين (UDL والذكاء الاصطناعي)</option>
            <option value="inclusion">عرض خطة دمج تربوي وتهيئة البيئة الصفية</option>
          </select>

          <div id="ppt-slides-list" class="space-y-2.5 max-h-[460px] overflow-y-auto pl-1"></div>
        </div>

        <!-- Celebration & Inclusive Events Planner -->
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm space-y-4">
          <div class="flex items-center justify-between gap-2">
            <div class="flex items-center gap-2">
              <span class="rounded-lg bg-rose-50 p-2 text-rose-700"><i data-lucide="party-popper" class="h-5 w-5"></i></span>
              <div>
                <h2 class="text-base font-extrabold text-slate-900">منظم الاحتفالات والفعاليات الدامجة</h2>
                <p class="text-xs text-slate-500">خطة زمنية صديقة للحواس + قائمة تجهيزات تفاعلية</p>
              </div>
            </div>
            <span id="event-progress-badge" class="rounded-full bg-teal-50 px-3 py-1 text-xs font-bold text-teal-800">0 / 6 جاهز</span>
          </div>

          <select id="event-type" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm font-semibold focus:border-teal-600 focus:outline-none">
            <option value="autism-day">اليوم العالمي للتوعية بالتوحد (٢ أبريل)</option>
            <option value="down-day">اليوم العالمي لمتلازمة داون (٢١ مارس)</option>
            <option value="graduation">حفل ختام العام وتكريم الطلاب والمعلمين</option>
            <option value="sensory-fun">يوم فني ورياضي دامج صديق للحواس</option>
          </select>

          <div id="event-timeline" class="rounded-xl bg-slate-50 p-4 text-xs text-slate-700 space-y-2 border border-slate-200"></div>

          <div>
            <h3 class="text-xs font-extrabold text-slate-800 mb-2">قائمة الجاهزية الصديقة للحواس (اضغط للتحديد):</h3>
            <div id="event-checklist" class="space-y-2"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- TAB 6: SMART STUDENT PROBLEM-SOLVING CONSULTANT -->
    <section id="tab-smart-advisor" class="tab-panel hidden space-y-6">
      <div class="grid grid-cols-1 gap-6 lg:grid-cols-12">
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm lg:col-span-5 space-y-4">
          <div class="flex items-center gap-2">
            <span class="rounded-lg bg-teal-50 p-2 text-teal-700"><i data-lucide="bot" class="h-5 w-5"></i></span>
            <div>
              <h2 class="text-base font-extrabold text-slate-900">مستشارك الذكي لحل المشكلات الطلابية</h2>
              <p class="text-xs text-slate-500">تحليل وظيفي للسلوك (ABC) وخطط تدخل فورية لداون والتوحد</p>
            </div>
          </div>

          <div class="space-y-3">
            <div>
              <label for="sa-condition" class="block text-xs font-bold text-slate-700 mb-1">فئة الطالب</label>
              <select id="sa-condition" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none">
                <option value="autism">طيف التوحد (Autism)</option>
                <option value="down">متلازمة داون (Down Syndrome)</option>
              </select>
            </div>

            <div>
              <label for="sa-issue" class="block text-xs font-bold text-slate-700 mb-1">المشكلة السلوكية أو التعليمية</label>
              <select id="sa-issue" class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none">
                <option value="meltdown">نوبة غضب أو انهيار حسي (Sensory Meltdown)</option>
                <option value="refusal">رفض المهمة أو الهروب من النشاط</option>
                <option value="transition">صعوبة الانتقال بين الحصص والأنشطة</option>
                <option value="communication">صعوبة التعبير عن الطلب / الإحباط التواصلي</option>
                <option value="social">الانسحاب أو عدم التفاعل مع الأقران</option>
              </select>
            </div>

            <div>
              <label for="sa-note" class="block text-xs font-bold text-slate-700 mb-1">وصف مختصر للموقف (اختياري — يحلل الكلمات المفتاحية)</label>
              <textarea id="sa-note" rows="2" placeholder="مثال: الطالب يبكي ويغلق أذنيه عند ارتفاع الصوت أو وقت الطابور..." class="w-full rounded-xl border border-slate-300 bg-slate-50 px-3 py-2 text-sm focus:border-teal-600 focus:outline-none"></textarea>
            </div>

            <button type="button" id="sa-solve-btn" class="w-full rounded-xl bg-teal-700 py-2.5 text-sm font-bold text-white shadow-sm transition hover:bg-teal-800">
              تحليل الموقف واقتراح خطة التدخل
            </button>
          </div>
        </div>

        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm lg:col-span-7 space-y-4">
          <div class="flex items-center justify-between border-b border-slate-100 pb-3">
            <h3 class="text-base font-extrabold text-slate-900">التشخيص التربوي وخطة التدخل الفوري</h3>
            <button type="button" id="sa-copy-btn" class="inline-flex items-center gap-1.5 rounded-lg border border-slate-300 px-3 py-1.5 text-xs font-bold text-slate-700 hover:bg-slate-50">
              <i data-lucide="copy" class="h-3.5 w-3.5"></i>
              <span>نسخ التوصية</span>
            </button>
          </div>
          <div id="sa-output" class="space-y-3 text-sm text-slate-700"></div>
        </div>
      </div>
    </section>

    <!-- TAB 7: DIRECTORS & DEPUTIES OBSTACLE SOLVER -->
    <section id="tab-directors-hub" class="tab-panel hidden space-y-6">
      <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm">
        <div class="flex flex-col gap-3 md:flex-row md:items-center md:justify-between">
          <div>
            <h2 class="text-lg font-extrabold text-slate-900">مركز تذليل العقبات أمام المدراء ووكلاء المراكز</h2>
            <p class="mt-1 text-sm text-slate-600">حلول إدارية وتشغيلية مبنية على مبادئ السلوك التنظيمي وإدارة التغيير في مراكز التربية الخاصة.</p>
          </div>
          <span class="rounded-full bg-indigo-50 px-3.5 py-1.5 text-xs font-bold text-indigo-800">دعم القيادة والوكلاء</span>
        </div>

        <div class="mt-4 flex flex-wrap gap-2">
          <button type="button" data-dir-case="burnout" class="dir-case-btn rounded-full border border-teal-700 bg-teal-700 px-4 py-1.5 text-xs font-bold text-white transition">الاحتراق الوظيفي ودوران المعلمين</button>
          <button type="button" data-dir-case="parents" class="dir-case-btn rounded-full border border-slate-300 bg-white px-4 py-1.5 text-xs font-bold text-slate-700 transition hover:bg-slate-100">توقعات أولياء الأمور والخلافات</button>
          <button type="button" data-dir-case="staffing" class="dir-case-btn rounded-full border border-slate-300 bg-white px-4 py-1.5 text-xs font-bold text-slate-700 transition hover:bg-slate-100">نقص الأخصائيين وضغط الجداول</button>
          <button type="button" data-dir-case="resistance" class="dir-case-btn rounded-full border border-slate-300 bg-white px-4 py-1.5 text-xs font-bold text-slate-700 transition hover:bg-slate-100">مقاومة التغيير والأساليب الحديثة (UDL/AI)</button>
          <button type="button" data-dir-case="quality" class="dir-case-btn rounded-full border border-slate-300 bg-white px-4 py-1.5 text-xs font-bold text-slate-700 transition hover:bg-slate-100">ضبط جودة الخطط الفردية والتقارير</button>
        </div>
      </div>

      <div id="directors-output" class="grid grid-cols-1 gap-6 lg:grid-cols-12"></div>
    </section>

    <!-- TAB 8: GLOBAL TEACHER PD WORKSHOPS -->
    <section id="tab-global-pd" class="tab-panel hidden space-y-6">
      <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm space-y-4">
        <div class="flex flex-col gap-3 md:flex-row md:items-center md:justify-between">
          <div>
            <h2 class="text-lg font-extrabold text-slate-900">التنمية المهنية للمعلمين — ورش ومسارات تدريبية عالمية</h2>
            <p class="mt-1 text-sm text-slate-600">دورات وورش عمل دولية مجانية ومفتوحة الوصول (بشهادات معتمدة في معظمها) في التوحد، متلازمة داون، وUDL.</p>
          </div>
          <div class="flex flex-wrap gap-2">
            <button type="button" data-pd-filter="all" class="pd-filter-btn rounded-full border border-teal-700 bg-teal-700 px-3.5 py-1.5 text-xs font-bold text-white">الكل</button>
            <button type="button" data-pd-filter="autism" class="pd-filter-btn rounded-full border border-slate-300 bg-white px-3.5 py-1.5 text-xs font-bold text-slate-700 hover:bg-slate-100">التوحد</button>
            <button type="button" data-pd-filter="udl" class="pd-filter-btn rounded-full border border-slate-300 bg-white px-3.5 py-1.5 text-xs font-bold text-slate-700 hover:bg-slate-100">UDL والذكاء الاصطناعي</button>
            <button type="button" data-pd-filter="inclusion" class="pd-filter-btn rounded-full border border-slate-300 bg-white px-3.5 py-1.5 text-xs font-bold text-slate-700 hover:bg-slate-100">الدمج وداون</button>
          </div>
        </div>
      </div>

      <div id="global-pd-grid" class="grid grid-cols-1 gap-5 md:grid-cols-2 lg:grid-cols-3"></div>
    </section>

  </main>

  <footer class="border-t border-slate-200 bg-white py-4 text-center text-xs text-slate-500">
    منصة مبادرة <strong>INSIGHT</strong> لذوي الهمم — إعداد وتأسيس: <strong>Samuel Gergies</strong> (الإسكندرية، مصر) • جميع المراجع الخارجية مرتبطة بمصادرها الرسمية المعتمدة.
  </footer>

  <script>
    // ---------- STATE & GROUNDED DATA ----------
    const workshops = [
      {
        id: 1,
        number: "ورشة العمل الأولى",
        title: "مستقبل التربية الخاصة بين ذكاء التكنولوجيا واتزان المؤسسة",
        date: "الأحد ٢٩ مارس ٢٠٢٦ | ١:٠٠ ظهراً – ٤:٠٠ عصراً",
        venue: "مقر الركن الأمريكي بمؤسسة أميدست — ٣ شارع الفراعنة، الأزاريطة، الإسكندرية",
        attendees: "معلمون، مشرفون، ومديرون من ٤ مراكز ومدارس بالإسكندرية",
        pillars: [
          "المحور الأول: التصميم الشامل للتعلم (UDL) والذكاء الاصطناعي لتصميم محتوى تعليمي متنوع وخطط تعليم فردية (IEP).",
          "المحور الثاني: السلوك التنظيمي وبناء بيئة عمل متعاونة وإدارة الضغوط وتعزيز القيادة داخل مؤسسات التربية الخاصة."
        ],
        badges: ["UDL + AI", "السلوك التنظيمي", "تطبيق عملي"]
      },
      {
        id: 2,
        number: "ورشة العمل الثانية",
        title: "آفاق الابتكار في التربية الخاصة والإدارة: بناء مجتمع أفضل",
        date: "الأحد ٢٨ يونيو ٢٠٢٦ | ١:٠٠ ظهراً – ٤:٠٠ عصراً",
        venue: "مقر الركن الأمريكي بمؤسسة أميدست — ٣ شارع الفراعنة، الأزاريطة، الإسكندرية",
        attendees: "٢٣ مسجلاً موثقاً (معلمون، مشرفون، مديرو مراكز) من ٤ مؤسسات شريكة",
        pillars: [
          "تطوير آليات الابتكار التربوي في فصول الدمج ورعاية ذوي الهمم.",
          "تكامل الأدوار بين الإدارة والمعلمين والأخصائيين لبناء مجتمع مدرسي داعم ومستدام."
        ],
        badges: ["الابتكار الإداري", "بناء المجتمع", "٢٣ مشاركاً"]
      }
    ];

    const referencesData = [
      {
        category: "udl",
        tag: "التصميم الشامل للتعلم (UDL 3.0)",
        title: "إرشادات CAST للتصميم الشامل للتعلم — الإصدار 3.0",
        org: "CAST (Center for Applied Special Technology)",
        summary: "إطار عمل عالمي يرتكز على ٣ مبادئ: تعدد وسائل الاندماج (Engagement)، تعدد وسائل العرض (Representation)، وتعدد وسائل التعبير (Action & Expression)، مع تركيز خاص في إصدار 3.0 على المتعة واللعب والتعاطف وتقليل الحواجز النظامية.",
        tips: [
          "قدّم المفهوم الواحد بثلاث صور: بطاقة مصورة، مجسم ملموس، وجملة صوتية قصيرة.",
          "اسمح للطالب بالتعبير عن فهمه بالإشارة أو البطاقات أو الرسم وليس بالكلام فقط."
        ],
        url: "https://udlguidelines.cast.org/",
        urlLabel: "الموقع الرسمي لإرشادات CAST UDL 3.0"
      },
      {
        category: "down",
        tag: "متلازمة داون — دليل التعليم",
        title: "استراتيجيات التدريس والدمج لطلاب متلازمة داون",
        org: "National Down Syndrome Society (NDSS)",
        summary: "توصي NDSS بالاعتماد على الجداول البصرية، والأنشطة العملية متعددة الحواس، والمواد ذات الخط الكبير الواضح، مع التكرار المنظم والثناء المحدد، والتنسيق المستمر بين معلم الفصل وأخصائي التخاطب والعلاج الوظيفي.",
        tips: [
          "قسّم المهمة الواحدة إلى خطوات صغيرة متسلسلة مع فاصل استراحة قصير لتجنب الإحباط.",
          "استخدم النمذجة العملية (أرِ الطالب ما تريده فعلياً قبل أن تطلب منه التنفيذ)."
        ],
        url: "https://ndss.org/education",
        urlLabel: "دليل التعليم — الجمعية الوطنية لمتلازمة داون (NDSS)"
      },
      {
        category: "down",
        tag: "متلازمة داون — الاعتبارات الصحية والنفسية",
        title: "المؤشرات الصحية المؤثرة على التعلم والانتباه لدى ذوي متلازمة داون",
        org: "Centers for Disease Control and Prevention (CDC)",
        summary: "توضح بيانات CDC أن الأطفال ذوي متلازمة داون أكثر عرضة لتحديات صحية تؤثر مباشرة على التحصيل داخل الفصل، منها: ضعف السمع (حتى 75%)، مشكلات الإبصار والحاجة لنظارات (50%)، انقطاع التنفس أثناء النوم (50–75%)، وعيوب القلب الخلقية (50–65%).",
        tips: [
          "تأكد من جلوس الطالب في الصف الأمامي وبمواجهة المعلم لتسهيل قراءة الشفاه والتركيز السمعي.",
          "راقب علامات الإرهاق النهاري أو فرك العينين ونسّق مع ولي الأمر للفحص الدوري."
        ],
        url: "https://www.cdc.gov/birth-defects/living-with-down-syndrome/index.html",
        urlLabel: "مرجع CDC الطبي والتربوي لمتلازمة داون"
      },
      {
        category: "autism",
        tag: "طيف التوحد — حقائق وتدخلات نفسية",
        title: "الحقائق العالمية والتدخلات النفسية والاجتماعية لطيف التوحد",
        org: "World Health Organization (WHO)",
        summary: "تشير منظمة الصحة العالمية (تحديث سبتمبر ٢٠٢٥) إلى أن نحو ١ من كل ١٢٧ شخصاً عالمياً لديهم توحد، وأن التدخلات النفسية والاجتماعية المبنية على الأدلة تحسّن مهارات التواصل والتفاعل الاجتماعي وجودة الحياة للطلاب وأسرهم.",
        tips: [
          "حافظ على روتين يومي ثابت ومُعلن مسبقاً، وهيّئ الطالب قبل أي تغيير مفاجئ بوقت كافٍ.",
          "راعِ الفروق الفردية الواسعة في القدرات اللغوية والحسية لكل طالب داخل الطيف."
        ],
        url: "https://www.who.int/news-room/fact-sheets/detail/autism-spectrum-disorders",
        urlLabel: "صحيفة حقائق التوحد — منظمة الصحة العالمية (WHO)"
      },
      {
        category: "autism",
        tag: "طيف التوحد — استراتيجيات الصف",
        title: "استراتيجيات النجاح داخل الفصل لطلاب طيف التوحد",
        org: "CDC & Autism Speaks",
        summary: "تؤكد أدلة CDC وAutism Speaks على أهمية إشراك الطالب مع أقران إيجابيين والعمل في مجموعات صغيرة، وتجنب عزل الطالب في تفاعل حصري مع المعلم المرافق (Shadow Teacher) فقط حتى لا ينقطع تواصله الاجتماعي مع زملائه.",
        tips: [
          "وجّه المعلم المرافق للتدخل التدريجي والانسحاب عند تفاعل الطالب مع أقرانه.",
          "وفّر ركناً هادئاً للتنظيم الحسي عند ارتفاع الضوضاء أو زيادة الحمل البصري."
        ],
        url: "https://www.autismspeaks.org/tool-kit-excerpt/autism-classroom-strategies",
        urlLabel: "دليل Autism Speaks لاستراتيجيات الفصل"
      },
      {
        category: "admin",
        tag: "إدارة المراكز والدمج",
        title: "مبادئ اليونسكو للدمج التربوي وتكافؤ الفرص",
        org: "UNESCO",
        summary: "ترتكز سياسات اليونسكو للدمج التعليمي على ضمان حق كل متعلم دون تمييز (Non-discrimination)، ورفض الإقصاء (Zero-reject)، وتوفير الترتيبات التيسيرية المعقولة (Reasonable Accommodation) داخل البيئة التعليمية.",
        tips: [
          "اعقد اجتماعات دورية أسبوعية بين الإدارة والأخصائيين وأولياء الأمور لمراجعة الخطط الفردية.",
          "درّب الفريق الإداري والسكرتارية على التواصل الداعم والمرن مع الأسر."
        ],
        url: "https://www.unesco.org/en/inclusion-education",
        urlLabel: "بوابة اليونسكو للدمج في التعليم"
      }
    ];

    const pptTemplates = {
      impact: [
        { title: "١. الغلاف والهوية", bullets: "شعار المركز + مبادرة INSIGHT، عنوان التقرير، الفترة الزمنية، واسم المدير.", layout: "غلاف داكن أنيق بصورة رمزية أو أيقونة تعليمية" },
        { title: "٢. الرؤية والرسالة", bullets: "التزام المركز بالدمج، النمو، والتدريب الشامل لطلاب داون والتوحد.", layout: "بطاقتان متقابلتان: الرؤية | الرسالة" },
        { title: "٣. مؤشرات الأداء بالأرقام", bullets: "عدد الطلاب المستفيدين، عدد الجلسات الفردية، نسبة التقدم في الخطط الفردية (IEP).", layout: "٣-٤ بطاقات أرقام كبيرة (KPI Cards)" },
        { title: "٤. البرامج والورش المنفذة", bullets: "تغطية ورش تدريب المعلمين (UDL، الذكاء الاصطناعي، السلوك التنظيمي).", layout: "خط زمني أفقي (Timeline)" },
        { title: "٥. قصص نجاح وتطور الحالات", bullets: "نماذج مجهّلة الهوية لتطور مهارات النطق أو التفاعل الاجتماعي.", layout: "بطاقات مقارنة (قبل / بعد)" },
        { title: "٦. التحديات والخطط المستقبلية", bullets: "الاحتياجات التدريبية واللوجستية للفصل القادم ودعوة للشراكة.", layout: "جدول أولويات + شريحة ختام وتواصل" }
      ],
      parents: [
        { title: "١. ترحيب دافئ بأولياء الأمور", bullets: "رسالة طمأنة وشراكة: الأسرة والمركز فريق واحد.", layout: "خلفية هادئة بألوان دافئة" },
        { title: "٢. فهم خصائص الطفل النفسية والحسية", bullets: "نقاط القوة لدى أطفال داون والتوحد واحتياجاتهم الحسية.", layout: "أيقونات بصرية مبسطة" },
        { title: "٣. روتين المنزل الداعم للفصل", bullets: "الجدول البصري المنزلي، تقليل المشتتات، وتثبيت أوقات النوم.", layout: "قائمة خطوات مرقمة ١-٢-٣" },
        { title: "٤. التواصل الإيجابي والتعزيز", bullets: "كيف نعزز السلوك الإيجابي فوراً وبوضوح بعيداً عن المقارنة.", layout: "مقارنة: جملة غير فعالة vs بديل داعم" },
        { title: "٥. قنوات المتابعة مع المركز", bullets: "دفتر المتابعة الأسبوعي، مواعيد الاستشارات، والأنشطة المشتركة.", layout: "بطاقة بيانات تواصل واضحة" }
      ],
      training: [
        { title: "١. عنوان الورشة والهدف التدريبي", bullets: "مبادرة INSIGHT: توظيف UDL والذكاء الاصطناعي في التربية الخاصة.", layout: "غلاف حديث بتباين عالٍ" },
        { title: "٢. كسر الجليد وتحديد التحديات", bullets: "سؤال تفاعلي للمعلمين حول أبرز صعوبة يواجهونها داخل الفصل.", layout: "شريحة سؤال مفتوح + QR" },
        { title: "٣. مبادئ التصميم الشامل للتعلم (UDL 3.0)", bullets: "الاندماج، التمثيل، التعبير — وكيفية تكييف الدرس الواحد.", layout: "٣ أعمدة ملونة للمبادئ الثلاثة" },
        { title: "٤. تطبيق عملي بالذكاء الاصطناعي", bullets: "كتابة أوامر (Prompts) لإنتاج قصص اجتماعية أو بطاقات بصرية.", layout: "شاشة نموذج أمر + النتيجة" },
        { title: "٥. التوازن المؤسسي وإدارة الضغوط", bullets: "الوقاية من الاحتراق الوظيفي وبناء فريق متعاون داخل المركز.", layout: "رسم دائري للتوازن المهني" }
      ],
      inclusion: [
        { title: "١. أهداف خطة الدمج التربوي", bullets: "تهيئة البيئة الصفية والاجتماعية لاستقبال طلاب داون والتوحد.", layout: "غلاف رسمي بشعار المدرسة" },
        { title: "٢. الترتيبات المكانية والحسية", bullets: "إضاءة هادئة، خفض الضوضاء، الجلوس الأمامي، وركن التهدئة.", layout: "مخطط مبسط لتوزيع مقاعد الفصل" },
        { title: "٣. دور المعلم المرافق (Shadow Teacher)", bullets: "تيسير التفاعل مع الأقران وتقليل الاعتمادية التدريجية.", layout: "نقاط واضحة + تنبيهات هامة" },
        { title: "٤. التقييم المرن والمخرجات", bullets: "تكييف الاختبارات والمهام لتناسب قدرات كل طالب.", layout: "جدول بدائل التقييم" }
      ]
    };

    const eventPlans = {
      "autism-day": {
        title: "اليوم العالمي للتوعية بالتوحد (٢ أبريل)",
        timeline: [
          "٠٩:٣٠ ص: استقبال هادئ للطلاب والأسر بدون مكبرات صوت صاخبة.",
          "١٠:٠٠ ص: افتتاح موجز (٥ دقائق) بلغة بسيطة وبطاقات ترحيب بصرية.",
          "١٠:١٥ ص: محطات أنشطة حسية وفنية هادئة (تلوين، صلصال، ألعاب تركيب).",
          "١١:٠٠ ص: عرض قصير لإنجازات الطلاب أو فيلم صامت بموسيقى ناعمة.",
          "١١:٣٠ ص: توزيع الهدايا التذكارية داخل حقائب منظمة والتقاط صور اختيارية."
        ],
        checklist: [
          "تخصيص غرفة هادئة (Quiet Zone) مزودة بوسائد وإضاءة خافتة",
          "استخدام إشارات بصرية لمسار الحركة وتجنب الزحام في الممرات",
          "خفض مستوى الصوت في الميكروفونات وتجنب البالونات القابلة للانفجار",
          "تجهيز بطاقات تعريف واضحة للمشرفين ومتطوعي الاستقبال",
          "إعداد كتيب أو باركود تعريفي موجز لأولياء الأمور والضيوف",
          "توفير بدائل ضيافة مناسبة للحساسيات الغذائية الشائعة"
        ]
      },
      "down-day": {
        title: "اليوم العالمي لمتلازمة داون (٢١ مارس)",
        timeline: [
          "٠٩:٤٥ ص: استقبال الأسر ونشاط الجوارب الملونة الرمزي (Lots of Socks).",
          "١٠:١٥ ص: فقرة حركية وإيقاعية جماعية بمشاركة الأقران.",
          "١٠:٤٥ ص: معرض أعمال يدوية وفنية من إنتاج طلاب المركز.",
          "١١:١٥ ص: تكريم الطلاب والأمهات بكلمات تشجيعية محددة لكل طفل.",
          "١١:٤٥ ص: ضيافة عائلية وتوثيق صور جماعية مبهجة."
        ],
        checklist: [
          "مراعاة وجود مقاعد مريحة وممرات آمنة لضعف التوتر العضلي",
          "إتاحة فواصل استراحة قصيرة بين الفقرات الحركية",
          "استخدام لوحات وشهادات بخط كبير وواضح وألوان مبهجة",
          "تجهيز فقرات بسيطة تشرك الجميع دون ضغط تنافسي",
          "تعيين منسق لمتابعة الإضاءة والتهوية المريحة بالقاعة",
          "تحضير شهادات تقدير فردية تذكر موهبة كل طالب بالاسم"
        ]
      },
      "graduation": {
        title: "حفل ختام العام وتكريم الطلاب والمعلمين",
        timeline: [
          "١٠:٠٠ ص: استقبال الأسر وتوزيع برنامج الحفل المصوّر.",
          "١٠:٢٠ ص: كلمة مدير المركز وشكر المعلمين والأخصائيين.",
          "١٠:٣٥ ص: عرض مرئي قصير لأبرز محطات التقدم خلال العام.",
          "١٠:٥٥ ص: تسليم الشهادات على مجموعات صغيرة لتقليل الانتظار.",
          "١١:٣٠ ص: صورة ختامية وضيافة خفيفة."
        ],
        checklist: [
          "تدريب الطلاب مسبقاً على خطوات الصعود للمسرح ببروفة هادئة",
          "ترتيب جلوس العائلات بما يضمن سهولة خروج أي طفل عند الحاجة",
          "تقليص مدة الكلمات الخطابية لأقل من ١٠ دقائق إجمالاً",
          "توفير مصور يلتقط صوراً طبيعية بدون فلاش قوي مزعج",
          "تجهيز ملف الإنجاز (Portfolio) لكل طالب لتسليمه مع الشهادة",
          "تكريم المعلمين والإداريين والسكرتارية على جهودهم"
        ]
      },
      "sensory-fun": {
        title: "يوم فني ورياضي دامج صديق للحواس",
        timeline: [
          "٠٩:٣٠ ص: تقسيم الطلاب لمحطات صغيرة (٤–٥ طلاب لكل محطة).",
          "٠٩:٤٥ ص: جولة ١ — محطة الألعاب الحركية والتوازن.",
          "١٠:١٥ ص: استراحة ماء ووجبة خفيفة هادئة.",
          "١٠:٣٠ ص: جولة ٢ — محطة الرسم بالرمل أو الصلصال الآمن.",
          "١١:٠٠ ص: نشاط ختامي تعاوني (جدارية بصمات الألوان)."
        ],
        checklist: [
          "فحص خامات الألوان والصلصال للتأكد من خلوها من السموم",
          "توفير مناديل ومريول لكل طالب لحماية الملابس",
          "تعيين أخصائي أو معلم مرافق لكل ٤ طلاب كحد أقصى",
          "وضع ساعة رملية أو مؤقت بصري لإعلان انتقال المحطات",
          "تجهيز حقيبة إسعافات أولية في نقطة واضحة",
          "إرسال صور الأنشطة للأسر في نفس اليوم مع رسالة شكر"
        ]
      }
    };

    const freeLibraryData = [
      // ARABIC
      {
        lang: "ar",
        langLabel: "العربية",
        topic: "autism",
        type: "دليل مجاني PDF",
        year: "مرجع تربوي مصري",
        title: "اضطراب التوحد: دليل المعلم والأسرة في التشخيص والتدخل",
        source: "المركز القومي للامتحانات والتقويم التربوي (مصر)",
        desc: "دليل عربي تطبيقي مجاني للمعلم والأسرة يغطي مؤشرات التشخيص، التقييم السلوكي، واستراتيجيات التدخل الصفي.",
        url: "https://nceee.edu.eg/puplic/images/nceee/pdf/adala3.pdf"
      },
      {
        lang: "ar",
        langLabel: "العربية",
        topic: "down",
        type: "كتاب / دليل PDF",
        year: "مكتبة قطر للعمل الاجتماعي",
        title: "متلازمة داون: الدليل الإرشادي والبحثي الشامل",
        source: "المؤسسة القطرية للعمل الاجتماعي",
        desc: "مرجع عربي مجاني يتناول الجوانب النمائية، الرعاية الصحية والتربوية، وأهمية التدخل المبكر لأطفال متلازمة داون.",
        url: "https://www.qatarsocial.org/sites/default/files/library/%D9%85%D8%AA%D9%84%D8%A7%D8%B2%D9%85%D8%A9%20%D8%AF%D8%A7%D9%88%D9%86.pdf"
      },
      {
        lang: "ar",
        langLabel: "العربية",
        topic: "down",
        type: "مكتبة كتب مجانية",
        year: "تحديث ٢٠٢٣–٢٠٢٥",
        title: "دليل المعلم: دعم الطلاب من ذوي متلازمة داون داخل الصفوف",
        source: "مكتبة جستر المهنية — قسم متلازمة داون",
        desc: "مجموعة كتب مجانية باللغة العربية مخصصة لمعلمي الفصول وأخصائيي التربية الخاصة لدعم طلاب متلازمة داون.",
        url: "https://www.gestermh.com/download-category/%D9%83%D8%AA%D8%A8-%D9%85%D8%AA%D9%84%D8%A7%D8%B2%D9%85%D8%A9-%D8%AF%D8%A7%D9%88%D9%86/"
      },
      {
        lang: "ar",
        langLabel: "العربية",
        topic: "autism",
        type: "مكتبة كتب مجانية",
        year: "مكتبة رقمية مفتوحة",
        title: "مكتبة كتب التوحد المجانية (التدخل والعلاج والدمج)",
        source: "جمعية إرادة للتوحد",
        desc: "تضم كتباً عربية ومترجمة مجانية مثل: التوحد ووسائل علاجه، والتوحد وفرط الحركة، متاحة للتحميل المباشر.",
        url: "https://www.autismhafar.org.sa/%D9%83%D8%AA%D8%A8-%D8%A7%D9%84%D8%AA%D9%88%D8%AD%D8%AF/"
      },
      {
        lang: "ar",
        langLabel: "العربية",
        topic: "both",
        type: "بحث ودراسة حديثة",
        year: "٢٠٢٥",
        title: "متلازمة داون واضطراب طيف التوحد: التشخيص المزدوج",
        source: "مركز أبحاث التوحد والنمائي (ABADC)",
        desc: "دراسة عربية حديثة تستعرض أبحاث المعاهد الوطنية للصحة حول تزامن التوحد مع متلازمة داون (نحو ١٦٪) وآليات التمييز.",
        url: "https://www.abadc.com.sa/down-syndrome-and-autism-spectrum-disorder/"
      },
      {
        lang: "ar",
        langLabel: "العربية",
        topic: "down",
        type: "مكتبة إلكترونية مجانية",
        year: "محدثة",
        title: "المرجع المبسط وزاوية الكتب العربية لمتلازمة داون",
        source: "منصة متلازمة داون",
        desc: "مكتبة عربية إلكترونية مجانية موجهة للأسر الجديدة والمعلمين لفهم خصائص النمو والتواصل.",
        url: "https://www.downsyndrome.site/book"
      },
      // ENGLISH
      {
        lang: "en",
        langLabel: "English",
        topic: "down",
        type: "Free Medical/Ed Book",
        year: "Feb 2026",
        title: "Down Syndrome — StatPearls Open-Access Reference",
        source: "NCBI Bookshelf (NIH)",
        desc: "مرجع علمي مفتوح ومحدث في فبراير ٢٠٢٦ يغطي الأساس الجيني، الجوانب النمائية، والاعتبارات السريرية والتربوية.",
        url: "https://www.ncbi.nlm.nih.gov/books/NBK526016/"
      },
      {
        lang: "en",
        langLabel: "English",
        topic: "autism",
        type: "Free Open-Access Book",
        year: "Jan 2025",
        title: "Autism Spectrum Disorder — StatPearls (NCBI Bookshelf)",
        source: "National Library of Medicine (NIH)",
        desc: "كتاب مرجعي مجاني محدث في ٢٠٢٥ يشرح التقييم متعدد التخصصات، الخصائص الحسية، وبرامج التدخل المبكر.",
        url: "https://www.ncbi.nlm.nih.gov/books/NBK525976/"
      },
      {
        lang: "en",
        langLabel: "English",
        topic: "autism",
        type: "Open-Access Book",
        year: "Exon / NCBI",
        title: "Autism Spectrum Disorders (Edited by A. M. Grabrucker)",
        source: "NCBI Bookshelf — CC BY-NC 4.0",
        desc: "كتاب علمي كامل مفتوح الوصول يتضمن فصولاً عن الصدمة النفسية في التوحد، آليات التشخيص، وطرق العلاج.",
        url: "https://www.ncbi.nlm.nih.gov/books/NBK573612/"
      },
      {
        lang: "en",
        langLabel: "English",
        topic: "autism",
        type: "Recent Research (2026)",
        year: "2026",
        title: "Autism Spectrum Disorder in the Genomic Era",
        source: "PubMed Central (PMC)",
        desc: "بحث حديث لعام ٢٠٢٦ يستعرض الأنماط الحسية (٦٠–٩٠٪ من ذوي التوحد) والتوجهات الجينية والعلاجية الجديدة.",
        url: "https://pmc.ncbi.nlm.nih.gov/articles/PMC13022905/"
      },
      {
        lang: "en",
        langLabel: "English",
        topic: "autism",
        type: "Recent Review (2025)",
        year: "Sept 2025",
        title: "Autism Spectrum Disorder: What Do We Know and Where Do We Go?",
        source: "PubMed Central (PMC)",
        desc: "مراجعة علمية حديثة (سبتمبر ٢٠٢٥) تلخص أحدث ما توصل إليه العلم حول التدخلات التربوية والدعم السلوكي.",
        url: "https://pmc.ncbi.nlm.nih.gov/articles/PMC12468522/"
      },
      {
        lang: "en",
        langLabel: "English",
        topic: "down",
        type: "Recent Research (2024)",
        year: "Oct 2024",
        title: "Development, Education, and Services in Children with Down Syndrome",
        source: "PubMed Central (PMC)",
        desc: "دراسة مفتوحة الوصول تتناول تباين مراحل النمو وتأثير الخدمات التعليمية المتخصصة على أطفال متلازمة داون.",
        url: "https://pmc.ncbi.nlm.nih.gov/articles/PMC11542095/"
      },
      // FRENCH
      {
        lang: "fr",
        langLabel: "Français",
        topic: "autism",
        type: "Recommandations 2026",
        year: "Fév 2026",
        title: "TSA : Interventions et parcours de vie (nourrisson, enfant, adolescent)",
        source: "Haute Autorité de Santé (HAS — France)",
        desc: "أحدث التوصيات الفرنسية الرسمية (فبراير ٢٠٢٦) للتدخلات النمائية والسلوكية والدمج المدرسي لطلاب طيف التوحد.",
        url: "https://www.has-sante.fr/jcms/p_3448980/fr/trouble-du-spectre-de-l-autisme-interventions-et-parcours-de-vie-du-nourrisson-de-l-enfant-et-de-l-adolescent"
      },
      {
        lang: "fr",
        langLabel: "Français",
        topic: "autism",
        type: "Fiche PDF Gratuite",
        year: "Jan 2026",
        title: "Messages clés HAS : Scolarisation, autonomie et accompagnement TSA",
        source: "Haute Autorité de Santé (HAS)",
        desc: "ملخص PDF مجاني ومباشر (يناير ٢٠٢٦) حول تهيئة البيئة المدرسية، التواصل البديل (CAA)، ودعم الأسر.",
        url: "https://www.has-sante.fr/upload/docs/application/pdf/2026-02/reco463_fiche_messages_tsa_mel.pdf"
      },
      {
        lang: "fr",
        langLabel: "Français",
        topic: "autism",
        type: "Recherche Ouverte (PDF)",
        year: "Jan 2025",
        title: "Challenges and needs of autistic students in higher education",
        source: "HAL Science — Archive ouverte",
        desc: "بحث أكاديمي مفتوح الوصول (يناير ٢٠٢٥) على منصة HAL حول تحديات واحتياجات الطلاب ذوي التوحد في التعليم.",
        url: "https://hal.science/hal-04907221v1/document"
      },
      {
        lang: "fr",
        langLabel: "Français",
        topic: "autism",
        type: "Thèse / PDF Gratuit",
        year: "HAL-Inria",
        title: "L'inclusion scolaire des élèves avec TSA",
        source: "HAL-Inria",
        desc: "دراسة فرنسية مفتوحة حول العلاقة بين المعلمين والطلاب ذوي طيف التوحد في فصول الدمج المدرسي.",
        url: "https://inria.hal.science/hal-03900700v1/document"
      },
      {
        lang: "fr",
        langLabel: "Français",
        topic: "both",
        type: "Mémoire PDF Gratuit",
        year: "Université de Nantes",
        title: "L'autisme dans la trisomie 21 : repérage et accompagnement",
        source: "Université de Nantes (Archive BU)",
        desc: "مرجع جامعي فرنسي مجاني يتناول التقاطع والتشخيص المزدوج بين متلازمة داون (Trisomie 21) وطيف التوحد.",
        url: "https://archive.bu.univ-nantes.fr/pollux/fichiers/download/7c30c708-7867-4448-90b4-bd8503eba03a"
      }
    ];

    let currentLibLang = "all";
    let currentDirCase = "burnout";
    let currentPdFilter = "all";

    const smartAdvisorPlans = {
      meltdown: {
        title: "نوبة غضب أو انهيار حسي (Sensory Meltdown)",
        why: "غالباً ما يحدث الانهيار الحسي نتيجة فرط المثيرات (ضوضاء، إضاءة قوية، زحام) وليس عناداً سلوكياً.",
        now: [
          "أوقف المهمة التعليمية فوراً ووجّه الطالب بهدوء إلى ركن التهدئة (Quiet Zone).",
          "قلّل الكلام لأدنى حد (جملة قصيرة واحدة هادئة) وتجنب التوبيخ أو الأسئلة الكثيرة أثناء النوبة.",
          "وفّر أداة تهدئة حسية مناسبة (سماعات عازلة للصوت، كرة ضغط، أو إضاءة خافتة)."
        ],
        prevent: "استخدم بطاقة «أحتاج استراحة» بصرية قبل تفاقم التوتر، وراقب المثيرات البيئية قبل الحصة.",
        escalate: "استشر الأخصائي النفسي إذا تكررت النوبات يومياً أو صاحبها إيذاء للذات."
      },
      refusal: {
        title: "رفض المهمة أو الهروب من النشاط",
        why: "يحدث غالباً إما لصعوبة المهمة فوق مستوى الطالب الحالي أو لعدم وضوح الخطوات المطلوبة.",
        now: [
          "طبّق قاعدة «أولاً ثم» (First-Then): مهمتان قصيرتان فقط ثم نشاط محبب.",
          "قدّم خياراً محصوراً بين بديلين («تحب نبدأ بالقلم الأزرق أم البطاقات؟») لاستعادة شعور السيطرة.",
          "عزّز فوراً بمجرد إنجاز أول خطوة بسيطة جداً."
        ],
        prevent: "قسّم الورقة أو النشاط إلى أجزاء صغيرة مرئية، وابدأ بمهمة مضمونة النجاح.",
        escalate: "راجع الخطة الفردية (IEP) مع المشرف إذا استمر الرفض لأكثر من أسبوع."
      },
      transition: {
        title: "صعوبة الانتقال بين الحصص والأنشطة",
        why: "التغيير المفاجئ يسبب قلقاً عالياً خاصة لطلاب طيف التوحد، كما يحتاج طلاب داون لوقت معالجة أطول.",
        now: [
          "استخدم مؤقتاً بصرياً (ساعة رملية أو مؤقت شاشة) قبل انتهاء النشاط بـ ٣ دقائق.",
          "أظهر بطاقة النشاط القادم في اليد قبل التحرك من المقعد.",
          "امنح الطالب دوراً انتقالياً محبباً (مثل حمل بطاقة الفصل أو ترتيب الأدوات)."
        ],
        prevent: "ثبّت جدولاً بصرياً يومياً على الحائط أو الطاولة وأشر إليه في كل انتقال.",
        escalate: "نسّق مع الأسرة لتوحيد أسلوب التنبيه المسبق في المنزل."
      },
      communication: {
        title: "صعوبة التعبير عن الطلب / الإحباط التواصلي",
        why: "حين يعجز الطالب عن إيصال احتياجه لفظياً، يلجأ للسلوك غير المرغوب كوسيلة تواصل بديلة.",
        now: [
          "قدّم بطاقات تواصل بصرية (PECS) أو إشارة يدوية واضحة للطلب فوراً.",
          "نمذج الكلمة أو الإشارة بهدوء («أنت تريد ماء؟ قل: ماء») واستجب بمجرد المحاولة.",
          "تجنب إجبار الطالب على نطق جملة طويلة وهو في حالة انفعال."
        ],
        prevent: "اجعل لوحة الطلبات الأساسية (ماء، حمام، استراحة، مساعدة) في متناول يد الطالب دائماً.",
        escalate: "أحِل الحالة لأخصائي التخاطب لتحديث نظام التواصل البديل والمعزز (AAC)."
      },
      social: {
        title: "الانسحاب أو عدم التفاعل مع الأقران",
        why: "قد ينعزل الطالب بسبب التفاعل الحصري مع المعلم المرافق أو غياب قواعد اللعب الواضحة.",
        now: [
          "شكّل مجموعة لعب ثنائية أو ثلاثية هادئة مع قرين داعم وواضح التفاعل.",
          "استخدم ألعاب التبادل الدور (Turn-taking) بوقت قصير وبطاقة دور بصرية.",
          "اسحب تدخل المعلم المرافق تدريجياً لإتاحة مساحة طبيعية للأقران."
        ],
        prevent: "درّب الأقران في الفصل على طرق التواصل البسيطة والمحترمة مع زميلهم.",
        escalate: "نسّق مع الأخصائي الاجتماعي والنفسي لتقييم المهارات الاجتماعية."
      }
    };

    const directorCases = {
      burnout: {
        title: "علاج الاحتراق الوظيفي ودوران المعلمين",
        diagnosis: "العمل المكثف مع ذوي الهمم يستهلك الطاقة العاطفية سريعاً في غياب توزيع عادل للأعباء والتقدير المهني.",
        steps: [
          "١. تطبيق نظام التدوير المتوازن للحالات عالية الشدة أسبوعياً بين الأخصائيين.",
          "٢. تخصيص ٣٠ دقيقة أسبوعياً لاجتماع دعم وتنفيس مهني (Peer Support) دون تقييم عقابي.",
          "٣. اعتماد برنامج تقدير شهري مرتبط بإنجازات الخطط الفردية وليس بالحضور فقط."
        ],
        template: "قرار إداري داعم: تقرر اعتماد نظام المناوبة الأسبوعية للحالات الحسية المكثفة، وتخصيص ساعة تطوير وتبادل خبرات أسبوعية للفريق لضمان جودة الرعاية واستدامة طاقة المعلمين.",
        kpi: "مؤشر المتابعة: نسبة استبقاء المعلمين الفصلية + استبيان الرضا المهني الشهري."
      },
      parents: {
        title: "إدارة توقعات أولياء الأمور والخلافات",
        diagnosis: "تنشأ الخلافات غالباً من توقع نتائج سريعة دون توضيح خطوات التقدم المرحلية الموثقة.",
        steps: [
          "١. توقيع ميثاق توقعات واضح مع الأسرة عند القبول يوضح أهداف الـ ٣ أشهر الأولى.",
          "٢. إرسال تقرير إنجاز مصغر أسبوعي يركز على التقدم الفعلي (وليس المشكلات فقط).",
          "٣. عقد جلسة مصارحة ثنائية بحضور المدير والأخصائي عند أي شكوى خلال ٤٨ ساعة."
        ],
        template: "رسالة طمأنة لولي الأمر: نشكركم على متابعتكم الحريصة؛ نعمل حالياً وفق خطة مرحلية موثقة، ويسعدنا استقبالكم يوم [اليوم] لمراجعة مؤشرات التقدم وتوحيد خطة العمل مع المنزل.",
        kpi: "مؤشر المتابعة: زمن إغلاق الشكوى (< ٤٨ ساعة) + نسبة حضور الأسر للقاءات الدورية."
      },
      staffing: {
        title: "نقص الأخصائيين وضغط الجداول اليومية",
        diagnosis: "التوزيع العشوائي للحصص الفردية يخلق فجوات زمنية ويهدر وقت المعلم المؤهل.",
        steps: [
          "١. تجميع الجلسات المتشابهة في كتل زمنية (Block Scheduling) لتقليل وقت الانتقال.",
          "٢. إسناد المهام الكتابية والسكرتارية لموظف إداري لتفريغ الأخصائي للجلسات.",
          "٣. إشراك متدربين من خريجي التربية الخاصة تحت إشراف مباشر في الأنشطة الجماعية."
        ],
        template: "مذكرة تنظيمية للوكيل: يُعاد توزيع جدول الجلسات الأسبوعي وفق كتل المهارات المتقاربة، وتُرحّل أعمال إدخال البيانات اليومية إلى السكرتارية لتعظيم ساعات التدخل الفعلي.",
        kpi: "مؤشر المتابعة: نسبة استغلال الساعات العلاجية + عدد ساعات العمل الإداري عن المعلم."
      },
      resistance: {
        title: "مقاومة التغيير وتطبيق الأساليب الحديثة (UDL وAI)",
        diagnosis: "يرفض بعض المعلمين الأدوات الجديدة خوفاً من زيادة العبء أو عدم الألفة التقنية.",
        steps: [
          "١. البدء بتجربة طوعية (Pilot) مع معلمَين متحمسَين وعرض نجاحهما عملياً أمام البقية.",
          "٢. تقديم تدريب تطبيقي قصير (٢٠ دقيقة) على أداة واحدة فقط في كل مرة.",
          "٣. توفير قوالب جاهزة تقلل وقت التحضير بدلاً من طلب إنشاء مواد من الصفر."
        ],
        template: "دعوة داخلية للفريق: ندعوكم لتجربة أداة تحضير الدروس السريعة هذا الأسبوع في جلسة تطبيقية مدتها ٢٠ دقيقة؛ الهدف توفير نصف وقت التحضير اليومي وليس زيادة الأعباء.",
        kpi: "مؤشر المتابعة: نسبة المعلمين المطبقين لقوالب UDL خلال ٣٠ يوماً."
      },
      quality: {
        title: "ضبط جودة الخطط الفردية (IEP) والتقارير",
        diagnosis: "تفاوت صياغة الأهداف بين الأخصائيين يضعف قياس الأثر أمام الإدارة والأسر.",
        steps: [
          "١. اعتماد نموذج موحد للهدف السلوكي (SMART) يتضمن معيار النجاح الرقمي.",
          "٢. مراجعة عينة أسبوعية من الخطط بواسطة الوكيل أو المشرف الفني قبل اعتمادها.",
          "٣. حفظ نسخ رقمية منظمة لكل طالب تتيح تتبع التطور عبر الفصول الدراسية."
        ],
        template: "تعميم جودة للوكيل والمشرفين: تُراجع جميع الخطط الفردية الجديدة قبل نهاية الأسبوع الأول من كل شهر للتأكد من قابلية الأهداف للقياس وربطها باستراتيجيات التكييف الحسي.",
        kpi: "مؤشر المتابعة: نسبة الخطط المستوفية لمعايير القياس + انتظام التقارير الشهرية."
      }
    };

    const globalPdWorkshops = [
      {
        cat: "autism",
        badge: "مجاني + شهادة PD",
        provider: "IRIS Center — Vanderbilt University",
        title: "Autism Spectrum Disorder: Evidence-Based Practices",
        desc: "وحدة تدريبية مجانية معتمدة للمعلمين حول ٢٧ ممارسة مبنية على الأدلة لطلاب طيف التوحد مع شهادة تطوير مهني.",
        url: "https://iris.peabody.vanderbilt.edu/module/asd2/"
      },
      {
        cat: "autism",
        badge: "مجاني — ٢٧ ممارسة",
        provider: "UNC — AFIRM Modules",
        title: "Autism Focused Intervention Resources & Modules",
        desc: "سلسلة ورش تفاعلية مجانية من جامعة نورث كارولينا تشرح خطوة بخطوة تطبيق التدخلات السلوكية والتربوية داخل الفصل.",
        url: "https://afirm.fpg.unc.edu/afirm-modules/"
      },
      {
        cat: "autism",
        badge: "مجاني + شهادة",
        provider: "OCALI — Autism Internet Modules",
        title: "Autism Internet Modules (AIM) Online Learning",
        desc: "أكثر من ٤٠ وحدة تدريبية مجانية أونلاين تغطي التقييم الحسي، التواصل، وإدارة السلوك مع شهادة إتمام.",
        url: "https://autisminternetmodules.org/"
      },
      {
        cat: "udl",
        badge: "دورات وندوات مجانية",
        provider: "CAST (UDL Leaders)",
        title: "CAST Courses & Artificial Intelligence for UDL",
        desc: "مسارات وندوات دولية من مؤسسة CAST تضم دورة توظيف الذكاء الاصطناعي في التصميم الشامل للتعلم (AI for UDL).",
        url: "https://www.cast.org/resources/courses/"
      },
      {
        cat: "inclusion",
        badge: "مجاني — داون وتوحد",
        provider: "FutureLearn — University of Leeds",
        title: "Inclusive Education: Exploring SEND Practice & Strategies",
        desc: "مساق تدريبي مجاني لمدة ٤ أسابيع يتناول دراسات حالة لمتلازمة داون وطيف التوحد واستراتيجيات الدعم الصفي.",
        url: "https://www.futurelearn.com/info/courses/inclusive-education-exploring-send-practice-and-strategies/0/steps/406024"
      },
      {
        cat: "inclusion",
        badge: "مجاني (Audit) — Coursera",
        provider: "Coursera — University of Cape Town",
        title: "Disability Inclusion in Education: Building Systems of Support",
        desc: "دورة دولية متخصصة في بناء أنظمة الدعم داخل المدارس ومراكز التربية الخاصة وتحقيق المساواة والدمج.",
        url: "https://www.coursera.org/learn/disability-inclusion-education"
      },
      {
        cat: "udl",
        badge: "مجاني — UNESCO IITE",
        provider: "UNESCO OpenLearning & IITE",
        title: "Teach and Learn with AI & Inclusive Education Courses",
        desc: "ورش ودورات اليونسكو المجانية للمعلمين حول التعليم الدامج وتوظيف الذكاء الاصطناعي التوليدي في دعم المتعلمين.",
        url: "https://openlearning.unesco.org/"
      },
      {
        cat: "autism",
        badge: "مجاني — Coursera",
        provider: "Coursera — UC Davis",
        title: "Autism Spectrum Disorder (ASD) Practical Training",
        desc: "دورة عملية من جامعة كاليفورنيا ديفيس لفهم التشخيص، التواصل، واستراتيجيات التدخل المبكر.",
        url: "https://www.coursera.org/learn/autism-spectrum-disorder-asd"
      }
    ];
    let currentRefFilter = "all";
    let currentAdminTpl = "letter";
    let checkedEventItems = new Set();
    let centersChartInstance = null;

    // ---------- HELPERS ----------
    function showToast(msg) {
      const toast = document.getElementById("toast");
      const msgEl = document.getElementById("toast-msg");
      msgEl.textContent = msg;
      toast.classList.remove("hidden");
      toast.classList.add("flex");
      setTimeout(() => {
        toast.classList.add("hidden");
        toast.classList.remove("flex");
      }, 2400);
    }

    function copyTextSafe(text, successMsg) {
      if (navigator.clipboard && navigator.clipboard.writeText) {
        navigator.clipboard.writeText(text).then(() => showToast(successMsg)).catch(() => fallbackCopy(text, successMsg));
      } else {
        fallbackCopy(text, successMsg);
      }
    }

    function fallbackCopy(text, successMsg) {
      const ta = document.createElement("textarea");
      ta.value = text;
      ta.style.position = "fixed";
      ta.style.opacity = "0";
      document.body.appendChild(ta);
      ta.select();
      try {
        document.execCommand("copy");
        showToast(successMsg);
      } catch (e) {
        showToast("تعذر النسخ التلقائي، يمكنك التظليل والنسخ يدوياً.");
      }
      document.body.removeChild(ta);
    }

    // ---------- TAB SWITCHING ----------
    function switchTab(tabId) {
      document.querySelectorAll(".tab-btn").forEach(btn => {
        const isTarget = btn.getAttribute("data-tab") === tabId;
        btn.classList.toggle("active", isTarget);
      });
      document.querySelectorAll(".tab-panel").forEach(panel => {
        panel.classList.toggle("hidden", panel.id !== `tab-${tabId}`);
      });
      if (tabId === "workshops" && centersChartInstance) {
        centersChartInstance.resize();
      }
    }

    // ---------- RENDER WORKSHOPS ----------
    function renderWorkshops() {
      const container = document.getElementById("workshops-list");
      document.getElementById("kpi-workshops-count").textContent = workshops.length;
      container.innerHTML = workshops.map(ws => `
        <article class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm transition hover:border-teal-300">
          <div class="flex flex-wrap items-center justify-between gap-2">
            <span class="rounded-full bg-teal-50 px-3 py-1 text-xs font-extrabold text-teal-800">${ws.number}</span>
            <div class="flex flex-wrap gap-1.5">
              ${ws.badges.map(b => `<span class="rounded-lg bg-slate-100 px-2.5 py-0.5 text-xs font-semibold text-slate-700">${b}</span>`).join("")}
            </div>
          </div>
          <h3 class="mt-3 text-base font-extrabold text-slate-900">${ws.title}</h3>
          <div class="mt-2 flex flex-col gap-1.5 text-xs text-slate-600">
            <div class="flex items-center gap-2"><i data-lucide="clock" class="h-3.5 w-3.5 text-teal-700"></i><span>${ws.date}</span></div>
            <div class="flex items-center gap-2"><i data-lucide="map-pin" class="h-3.5 w-3.5 text-teal-700"></i><span>${ws.venue}</span></div>
            <div class="flex items-center gap-2"><i data-lucide="users" class="h-3.5 w-3.5 text-teal-700"></i><span>${ws.attendees}</span></div>
          </div>
          <ul class="mt-3 space-y-1.5 border-t border-slate-100 pt-3 text-xs text-slate-700 leading-relaxed">
            ${ws.pillars.map(p => `<li class="flex items-start gap-2"><span class="mt-1 h-1.5 w-1.5 shrink-0 rounded-full bg-teal-600"></span><span>${p}</span></li>`).join("")}
          </ul>
        </article>
      `).join("");
      if (window.lucide) lucide.createIcons();
    }

    function initChart() {
      const ctx = document.getElementById("centersChart").getContext("2d");
      centersChartInstance = new Chart(ctx, {
        type: "doughnut",
        data: {
          labels: [
            "Future Schools (التدخل الأكاديمي)",
            "مركز شمس الحياة (سان جوزيف)",
            "مركز الحياة (سان مارك)",
            "مركز المحبة (سانت جان أنتيد)"
          ],
          datasets: [{
            data: [9, 6, 6, 2],
            backgroundColor: ["#0f766e", "#0284c7", "#f59e0b", "#6366f1"],
            borderWidth: 2,
            borderColor: "#ffffff"
          }]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              position: "bottom",
              labels: {
                font: { family: "Cairo, sans-serif", size: 11 },
                boxWidth: 12,
                padding: 12
              }
            }
          }
        }
      });
    }

    // ---------- RENDER REFERENCES ----------
    function renderReferences() {
      const q = (document.getElementById("ref-search").value || "").trim().toLowerCase();
      const filtered = referencesData.filter(item => {
        const matchCat = currentRefFilter === "all" || item.category === currentRefFilter;
        const matchText = !q || item.title.toLowerCase().includes(q) || item.summary.toLowerCase().includes(q) || item.org.toLowerCase().includes(q) || item.tips.some(t => t.toLowerCase().includes(q));
        return matchCat && matchText;
      });

      const grid = document.getElementById("references-grid");
      if (filtered.length === 0) {
        grid.innerHTML = `<div class="col-span-full rounded-2xl border border-dashed border-slate-300 bg-white p-8 text-center text-sm text-slate-500">لا توجد مراجع مطابقة لبحثك. جرّب كلمة مفتاحية أخرى أو اختر "الكل".</div>`;
        return;
      }

      grid.innerHTML = filtered.map(ref => `
        <article class="flex flex-col justify-between rounded-2xl border border-slate-200 bg-white p-5 shadow-sm">
          <div>
            <div class="flex items-center justify-between gap-2">
              <span class="rounded-full bg-teal-50 px-3 py-1 text-xs font-bold text-teal-800">${ref.tag}</span>
              <span class="text-xs font-semibold text-slate-400">${ref.org}</span>
            </div>
            <h3 class="mt-3 text-base font-extrabold text-slate-900">${ref.title}</h3>
            <p class="mt-2 text-xs text-slate-600 leading-relaxed">${ref.summary}</p>
            <div class="mt-3 rounded-xl bg-slate-50 p-3">
              <div class="text-xs font-bold text-slate-800 mb-1.5">نصائح تطبيقية للمعلم والإدارة:</div>
              <ul class="space-y-1 text-xs text-slate-700">
                ${ref.tips.map(t => `<li class="flex items-start gap-1.5"><span class="text-teal-600 font-bold">•</span><span>${t}</span></li>`).join("")}
              </ul>
            </div>
          </div>
          <div class="mt-4 pt-3 border-t border-slate-100">
            <a href="${ref.url}" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 text-xs font-bold text-teal-700 hover:text-teal-900 hover:underline">
              <i data-lucide="external-link" class="h-3.5 w-3.5"></i>
              <span>${ref.urlLabel}</span>
            </a>
          </div>
        </article>
      `).join("");
      if (window.lucide) lucide.createIcons();
    }

    // ---------- RENDER FREE BOOKS & RESEARCH LIBRARY ----------
    function renderFreeLibrary() {
      const q = (document.getElementById("lib-search").value || "").trim().toLowerCase();
      const topicFilter = document.getElementById("lib-topic").value;
      const filtered = freeLibraryData.filter(item => {
        const matchLang = currentLibLang === "all" || item.lang === currentLibLang;
        const matchTopic = topicFilter === "all" || item.topic === topicFilter || item.topic === "both";
        const matchText = !q || item.title.toLowerCase().includes(q) || item.desc.toLowerCase().includes(q) || item.source.toLowerCase().includes(q);
        return matchLang && matchTopic && matchText;
      });

      const grid = document.getElementById("free-library-grid");
      if (filtered.length === 0) {
        grid.innerHTML = `<div class="col-span-full rounded-xl border border-dashed border-slate-300 p-6 text-center text-xs text-slate-500">لا توجد كتب أو أبحاث مطابقة. جرّب تغيير اللغة أو كلمة البحث.</div>`;
        return;
      }

      const langColors = {
        ar: "bg-emerald-50 text-emerald-800 border-emerald-200",
        en: "bg-indigo-50 text-indigo-800 border-indigo-200",
        fr: "bg-amber-50 text-amber-800 border-amber-200"
      };

      grid.innerHTML = filtered.map(item => `
        <article class="flex flex-col justify-between rounded-xl border border-slate-200 bg-slate-50/70 p-4 transition hover:border-teal-300 hover:bg-white">
          <div>
            <div class="flex flex-wrap items-center justify-between gap-1.5">
              <span class="rounded-full border px-2.5 py-0.5 text-[11px] font-bold ${langColors[item.lang]}">${item.langLabel}</span>
              <span class="rounded-md bg-slate-200/70 px-2 py-0.5 text-[11px] font-semibold text-slate-700">${item.type} • ${item.year}</span>
            </div>
            <h3 class="mt-2.5 text-sm font-extrabold text-slate-900 leading-snug">${item.title}</h3>
            <div class="mt-1 text-[11px] font-bold text-teal-700">${item.source}</div>
            <p class="mt-2 text-xs text-slate-600 leading-relaxed">${item.desc}</p>
          </div>
          <div class="mt-3 pt-2.5 border-t border-slate-200/80">
            <a href="${item.url}" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 text-xs font-bold text-teal-700 hover:text-teal-900 hover:underline">
              <i data-lucide="book-open" class="h-3.5 w-3.5"></i>
              <span>فتح المرجع المجاني</span>
            </a>
          </div>
        </article>
      `).join("");
      if (window.lucide) lucide.createIcons();
    }

    // ---------- SMART STUDENT ADVISOR ----------
    function renderSmartAdvisor() {
      const cond = document.getElementById("sa-condition").value;
      let issue = document.getElementById("sa-issue").value;
      const note = (document.getElementById("sa-note").value || "").trim();

      if (note) {
        if (/صوت|إضاءة|بكاء|أذن|ضوضاء|زحام/.test(note)) issue = "meltdown";
        else if (/رفض|هروب|كتابة|واجب|عناد/.test(note)) issue = "refusal";
        else if (/انتقال|حصة|طابور|تغيير|روتين/.test(note)) issue = "transition";
        else if (/كلام|نطق|طلب|تواصل|إشارة/.test(note)) issue = "communication";
        else if (/لعب|أصدقاء|عزلة|أقران|وحده/.test(note)) issue = "social";
        document.getElementById("sa-issue").value = issue;
      }

      const plan = smartAdvisorPlans[issue];
      const condNote = cond === "down"
        ? "مراعاة خاصة لمتلازمة داون: تأكد من فحص وضوح السمع والرؤية، واستخدم جملاً قصيرة ونمذجة عملية."
        : "مراعاة خاصة لطيف التوحد: تجنب اللمس المفاجئ، واخفض شدة المثيرات الصوتية والبصرية فوراً.";

      document.getElementById("sa-output").innerHTML = `
        <div class="rounded-xl bg-teal-50 p-4 border border-teal-100">
          <div class="text-xs font-bold text-teal-800">${cond === "down" ? "متلازمة داون" : "طيف التوحد"} • خطة استجابة سريعة</div>
          <div class="mt-1 text-base font-extrabold text-slate-900">${plan.title}</div>
          <p class="mt-1.5 text-xs text-slate-700"><strong>التفسير الوظيفي:</strong> ${plan.why}</p>
        </div>
        <div class="rounded-xl border border-slate-200 p-4">
          <div class="text-xs font-extrabold text-slate-900 mb-2">ماذا تفعل الآن داخل الفصل؟</div>
          <ol class="list-decimal list-inside space-y-1.5 text-xs text-slate-700">
            ${plan.now.map(step => `<li>${step}</li>`).join("")}
          </ol>
        </div>
        <div class="grid grid-cols-1 gap-3 sm:grid-cols-2">
          <div class="rounded-xl bg-slate-50 border border-slate-200 p-3.5 text-xs text-slate-700">
            <strong class="block text-slate-900 mb-1">الوقاية قبل الحصة القادمة:</strong>${plan.prevent}
          </div>
          <div class="rounded-xl bg-amber-50 border border-amber-200 p-3.5 text-xs text-amber-950">
            <strong class="block text-amber-900 mb-1">توجيه الفئة ومتى نحيل الحالة؟</strong>${condNote} ${plan.escalate}
          </div>
        </div>
      `;
    }

    // ---------- DIRECTORS & DEPUTIES HUB ----------
    function renderDirectorsHub() {
      const data = directorCases[currentDirCase];
      document.getElementById("directors-output").innerHTML = `
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm lg:col-span-7 space-y-4">
          <div class="flex items-center justify-between border-b border-slate-100 pb-3">
            <h3 class="text-base font-extrabold text-slate-900">${data.title}</h3>
            <span class="rounded-lg bg-teal-50 px-2.5 py-1 text-xs font-bold text-teal-800">خطة تنفيذية</span>
          </div>
          <p class="text-xs text-slate-600 leading-relaxed"><strong class="text-slate-800">التشخيص الإداري:</strong> ${data.diagnosis}</p>
          <div class="space-y-2">
            ${data.steps.map(st => `<div class="rounded-xl bg-slate-50 border border-slate-200 p-3 text-xs font-semibold text-slate-800">${st}</div>`).join("")}
          </div>
          <div class="rounded-xl bg-indigo-50 border border-indigo-200 p-3.5 text-xs font-bold text-indigo-950">
            ${data.kpi}
          </div>
        </div>
        <div class="rounded-2xl border border-slate-200 bg-white p-5 shadow-sm lg:col-span-5 flex flex-col justify-between space-y-4">
          <div>
            <div class="flex items-center justify-between border-b border-slate-100 pb-3">
              <h3 class="text-sm font-extrabold text-slate-900">صيغة قرار / رسالة جاهزة للنسخ</h3>
              <button type="button" id="copy-dir-tpl-btn" class="inline-flex items-center gap-1 rounded-lg bg-slate-900 px-3 py-1.5 text-xs font-bold text-white hover:bg-slate-800">
                <i data-lucide="copy" class="h-3.5 w-3.5"></i>
                <span>نسخ</span>
              </button>
            </div>
            <div id="dir-tpl-text" class="mt-4 rounded-xl border border-slate-200 bg-slate-50 p-4 text-xs text-slate-800 leading-relaxed">${data.template}</div>
          </div>
        </div>
      `;
      const copyBtn = document.getElementById("copy-dir-tpl-btn");
      if (copyBtn) {
        copyBtn.addEventListener("click", () => {
          copyTextSafe(document.getElementById("dir-tpl-text").textContent, "تم نسخ الصيغة الإدارية");
        });
      }
      if (window.lucide) lucide.createIcons();
    }

    // ---------- GLOBAL PD WORKSHOPS ----------
    function renderGlobalPD() {
      const items = globalPdWorkshops.filter(w => currentPdFilter === "all" || w.cat === currentPdFilter);
      document.getElementById("global-pd-grid").innerHTML = items.map(w => `
        <article class="flex flex-col justify-between rounded-2xl border border-slate-200 bg-white p-5 shadow-sm">
          <div>
            <div class="flex items-center justify-between gap-2">
              <span class="rounded-full bg-teal-50 px-3 py-1 text-[11px] font-bold text-teal-800">${w.badge}</span>
              <span class="text-[11px] font-bold text-slate-400">${w.provider}</span>
            </div>
            <h3 class="mt-3 text-sm font-extrabold text-slate-900 leading-snug">${w.title}</h3>
            <p class="mt-2 text-xs text-slate-600 leading-relaxed">${w.desc}</p>
          </div>
          <div class="mt-4 pt-3 border-t border-slate-100">
            <a href="${w.url}" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 text-xs font-bold text-teal-700 hover:text-teal-900 hover:underline">
              <i data-lucide="external-link" class="h-3.5 w-3.5"></i>
              <span>الانتقال إلى الورشة التدريبية</span>
            </a>
          </div>
        </article>
      `).join("");
      if (window.lucide) lucide.createIcons();
    }

    // ---------- LESSON & IEP BUILDER ----------
    function generateLessonPlan() {
      const condition = document.getElementById("lp-condition").value;
      const domain = document.getElementById("lp-domain").value;
      const duration = document.getElementById("lp-duration").value;
      const udl = document.getElementById("lp-udl").value;
      const topic = (document.getElementById("lp-topic").value || "مهارة تعليمية مخصصة").trim();

      const condMap = {
        down: {
          label: "متلازمة داون",
          setup: "الجلوس في الصف الأول بمواجهة المعلم، بطاقات بخط كبير واضح، مجسمات ملموسة، وفاصل حركي قصير كل ١٠ دقائق.",
          reinforce: "ثناء لفظي فوري ومحدد («أحسنت في مطابقة اللون الأحمر!») مع تعزيز رمزي بصري."
        },
        autism: {
          label: "طيف التوحد",
          setup: "جدول بصري من ٣ خطوات على الطاولة، تقليل المشتتات البصرية والضوضاء، ومؤقت بصري يوضح بداية ونهاية النشاط.",
          reinforce: "تعزيز مرتبط باهتمام الطالب الخاص بعد كل استجابة صحيحة، وتجنب اللمس المفاجئ."
        },
        mixed: {
          label: "فصل دمج مشترك (داون + توحد)",
          setup: "توزيع ثنائي مع أقران داعمين، تعليمات قصيرة مصحوبة بصورة، وركن هادئ متاح للتهدئة الحسية.",
          reinforce: "نظام نجوم جماعي وفردي مرن يراعي سرعة استجابة كل طالب."
        }
      };

      const domainMap = {
        speech: "التخاطب والتواصل الوظيفي",
        academic: "المهارات الأكاديمية المبسطة",
        sensory: "التنظيم الحسي والانتباه",
        social: "التفاعل الاجتماعي واللعب التعاوني",
        life: "المهارات الحياتية والاستقلالية"
      };

      const udlMap = {
        representation: "تقديم المعلومة عبر ٣ قنوات: صورة واضحة + مجسم ملموس + جملة من كلمتين إلى ثلاث كلمات.",
        engagement: "ربط النشاط باختيار الطالب بين بديلين محفّزين وإدخال عنصر اللعب الحركي القصير.",
        expression: "قبول الاستجابة بالإشارة، أو تسليم البطاقة، أو النطق، أو التركيب العملي دون حصرها في الكلام."
      };

      const c = condMap[condition];
      const out = document.getElementById("lesson-output");
      out.innerHTML = `
        <div class="rounded-xl bg-teal-50 p-4 border border-teal-100">
          <div class="text-xs font-bold text-teal-800">بطاقة الدرس | ${c.label} • ${domainMap[domain]} • ${duration}</div>
          <div class="mt-1 text-base font-extrabold text-slate-900">الهدف: ${topic}</div>
        </div>
        <div class="grid grid-cols-1 gap-3 sm:grid-cols-2">
          <div class="rounded-xl border border-slate-200 p-3.5">
            <div class="text-xs font-extrabold text-slate-900 mb-1">١. التهيئة البيئية والحسية</div>
            <p class="text-xs text-slate-600">${c.setup}</p>
          </div>
          <div class="rounded-xl border border-slate-200 p-3.5">
            <div class="text-xs font-extrabold text-slate-900 mb-1">٢. تطبيق التصميم الشامل (UDL)</div>
            <p class="text-xs text-slate-600">${udlMap[udl]}</p>
          </div>
        </div>
        <div class="rounded-xl border border-slate-200 p-3.5">
          <div class="text-xs font-extrabold text-slate-900 mb-1.5">٣. تسلسل الشرح والأنشطة (${duration})</div>
          <ol class="list-decimal list-inside space-y-1 text-xs text-slate-700">
            <li><strong>التمهيد والنمذجة (٥–٧ دقائق):</strong> عرض الجدول البصري، وتنفيذ المعلم للنموذج أمام الطالب بهدوء ووضوح.</li>
            <li><strong>الممارسة الموجّهة (١٥–٢٠ دقيقة):</strong> تطبيق الطالب للنشاط بمشاركة قرين أو مساعدة متدرجة تقل تدريجياً.</li>
            <li><strong>التعميم والختام (٥–٨ دقائق):</strong> نقل المهارة لموقف حياتي بسيط، ومراجعة البطاقة الختامية قبل الانتقال للحصة التالية.</li>
          </ol>
        </div>
        <div class="rounded-xl bg-amber-50/70 border border-amber-200 p-3.5">
          <div class="text-xs font-extrabold text-amber-900 mb-1">٤. التعزيز والتقييم</div>
          <p class="text-xs text-amber-950">${c.reinforce}</p>
        </div>
      `;
    }

    // ---------- ADMIN & SECRETARIAL KIT ----------
    function renderAdminPreview() {
      const center = document.getElementById("adm-center").value || "اسم المركز";
      const recipient = document.getElementById("adm-recipient").value || "الجهة المعنية";
      const date = document.getElementById("adm-date").value || "التاريخ";
      const notes = document.getElementById("adm-notes").value || "";

      const templates = {
        letter: `التاريخ: ${date}
من: إدارة ${center}
إلى: السادة / ${recipient}

تحية طيبة وبعد،،،

في إطار حرصنا المستمر على تطوير جودة الرعاية التربوية والنفسية المقدمة لأبنائنا من ذوي الهمم (متلازمة داون وطيف التوحد)، يسعدنا التنسيق مع سيادتكم بشأن أوجه التعاون والتدريب المشترك.

تفاصيل الموضوع:
${notes}

نرجو التكرم بتحديد موعد مناسب لمناقشة الخطوات التنفيذية وتبادل الخبرات بين فريق العمل.

وتفضلوا بقبول فائق الاحترام،،،
إدارة ${center}`,

        minutes: `محضر اجتماع فريق العمل التربوي والإداري
المركز: ${center}
التاريخ: ${date}
موضوع الاجتماع: ${recipient}

أولاً — جدول الأعمال:
١. مراجعة الخطط التربوية الفردية (IEP) لطلاب داون والتوحد.
٢. متابعة التجهيزات الحسية والبيئية داخل الفصول.
٣. توزيع المهام الإدارية والسكرتارية والتواصل مع أولياء الأمور.

ثانياً — القرارات والتوصيات:
${notes}

ثالثاً — التكليفات وموعد المتابعة:
• يلتزم كل معلم وأخصائي برفع تقرير التقدم الأسبوعي للسكرتارية يوم الخميس.
• يُعتمد المحضر من مدير المركز ويدرج في سجل المتابعة.`,

        parent: `تقرير متابعة دوري لولي الأمر
المركز: ${center}
اسم الطالب / الموضوع: ${recipient}
التاريخ: ${date}

ولي الأمر الفاضل، تحية طيبة،،،
نشارككم باعتزاز ملخص متابعة ابننا/ابنتنا خلال الفترة الحالية، حيث نعمل معاً وفق استراتيجيات التصميم الشامل للتعلم (UDL) لتعزيز قدراته في بيئة آمنة ومحفزة.

ملاحظات التقدم والتوصيات المنزلية:
${notes}

نسعد بتواصلكم الدائم معنا لتعزيز تكامل الدور بين المنزل والمركز.
مع خالص التقدير،،،
الفريق التربوي والنفسي — ${center}`,

        checklist: `قائمة التحقق الإدارية واللوجستية لتنظيم ورشة عمل
الجهة المنظمة: ${center} بالتعاون مع ${recipient}
التاريخ: ${date}

[ ] ١. تأكيد حجز القاعة والتحقق من شروط الدخول الأمني (تطابق الاسم والرقم القومي ١٤ رقماً إذا لزم).
[ ] ٢. إعداد استمارة التسجيل الرقمية (الاسم رباعي، رقم واتساب، الوظيفة، جهة العمل، التخصص، سنوات الخبرة).
[ ] ٣. إرسال رسالة تأكيد قبل الموعد بـ ٤٨ ساعة تتضمن رابط الموقع الجغرافي (Maps) وموعد البدء والختام.
[ ] ٤. تجهيز كشوف الحضور، بطاقات التعريف، والهدايا التذكارية أو الشهادات المعتمدة.
[ ] ٥. اختبار أجهزة العرض (PPT) والصوت وتوفير ضيافة مناسبة.

ملاحظات إضافية:
${notes}`
      };

      document.getElementById("admin-preview").textContent = templates[currentAdminTpl];
    }

    // ---------- PPT & EVENTS ----------
    function renderPPT() {
      const type = document.getElementById("ppt-type").value;
      const slides = pptTemplates[type];
      const list = document.getElementById("ppt-slides-list");
      list.innerHTML = slides.map(s => `
        <div class="rounded-xl border border-slate-200 bg-slate-50 p-3">
          <div class="flex items-center justify-between gap-2">
            <span class="text-xs font-extrabold text-slate-900">${s.title}</span>
            <span class="rounded-md bg-amber-100 px-2 py-0.5 text-[11px] font-bold text-amber-900">${s.layout}</span>
          </div>
          <p class="mt-1 text-xs text-slate-600">${s.bullets}</p>
        </div>
      `).join("");
    }

    function renderEventPlanner() {
      const type = document.getElementById("event-type").value;
      const plan = eventPlans[type];
      checkedEventItems = new Set();

      document.getElementById("event-timeline").innerHTML = `
        <div class="font-extrabold text-slate-900 text-sm mb-1">${plan.title} — البرنامج الزمني المقترح</div>
        ${plan.timeline.map(line => `<div class="flex items-start gap-2"><i data-lucide="clock-3" class="h-3.5 w-3.5 mt-0.5 shrink-0 text-rose-600"></i><span>${line}</span></div>`).join("")}
      `;

      const cl = document.getElementById("event-checklist");
      cl.innerHTML = plan.checklist.map((item, idx) => `
        <label class="flex cursor-pointer items-center gap-2.5 rounded-xl border border-slate-200 bg-white px-3 py-2 text-xs text-slate-700 hover:bg-slate-50">
          <input type="checkbox" data-ev-idx="${idx}" class="ev-check h-4 w-4 rounded accent-teal-700" />
          <span>${item}</span>
        </label>
      `).join("");

      updateEventProgress(plan.checklist.length);
      if (window.lucide) lucide.createIcons();
    }

    function updateEventProgress(total) {
      document.getElementById("event-progress-badge").textContent = `${checkedEventItems.size} / ${total} جاهز`;
    }

    // ---------- EVENT LISTENERS ----------
    document.addEventListener("DOMContentLoaded", () => {
      // Tabs
      document.querySelectorAll(".tab-btn").forEach(btn => {
        btn.addEventListener("click", () => switchTab(btn.getAttribute("data-tab")));
      });

      // Add Workshop form
      const addForm = document.getElementById("add-workshop-form");
      document.getElementById("toggle-add-workshop-btn").addEventListener("click", () => addForm.classList.toggle("hidden"));
      document.getElementById("cancel-add-workshop-btn").addEventListener("click", () => addForm.classList.add("hidden"));
      addForm.addEventListener("submit", (e) => {
        e.preventDefault();
        const title = document.getElementById("new-ws-title").value.trim();
        const date = document.getElementById("new-ws-date").value.trim();
        const venue = document.getElementById("new-ws-venue").value.trim();
        const count = document.getElementById("new-ws-count").value || "20";
        const topics = document.getElementById("new-ws-topics").value.trim();
        if (!title || !date || !venue) return;

        workshops.push({
          id: workshops.length + 1,
          number: `ورشة العمل #${workshops.length + 1}`,
          title,
          date,
          venue,
          attendees: `${count} مشاركاً (مضاف حديثاً)`,
          pillars: topics.split("\n").filter(Boolean),
          badges: ["مبادرة INSIGHT", `${count} مشاركاً`]
        });
        addForm.reset();
        addForm.classList.add("hidden");
        renderWorkshops();
        showToast("تمت إضافة الورشة إلى سجل المبادرة");
      });

      // References filter & search
      document.querySelectorAll("[data-ref-filter]").forEach(btn => {
        btn.addEventListener("click", () => {
          currentRefFilter = btn.getAttribute("data-ref-filter");
          document.querySelectorAll("[data-ref-filter]").forEach(b => b.classList.remove("active"));
          btn.classList.add("active");
          renderReferences();
      renderFreeLibrary();

      // Smart Advisor
      document.getElementById("sa-solve-btn").addEventListener("click", renderSmartAdvisor);
      document.getElementById("sa-condition").addEventListener("change", renderSmartAdvisor);
      document.getElementById("sa-issue").addEventListener("change", renderSmartAdvisor);
      document.getElementById("sa-copy-btn").addEventListener("click", () => {
        copyTextSafe(document.getElementById("sa-output").innerText, "تم نسخ خطة التدخل الطلابي");
      });
      renderSmartAdvisor();

      // Directors Hub
      document.querySelectorAll(".dir-case-btn").forEach(btn => {
        btn.addEventListener("click", () => {
          currentDirCase = btn.getAttribute("data-dir-case");
          document.querySelectorAll(".dir-case-btn").forEach(b => {
            const active = b === btn;
            b.classList.toggle("bg-teal-700", active);
            b.classList.toggle("text-white", active);
            b.classList.toggle("border-teal-700", active);
            b.classList.toggle("bg-white", !active);
            b.classList.toggle("text-slate-700", !active);
            b.classList.toggle("border-slate-300", !active);
          });
          renderDirectorsHub();
        });
      });
      renderDirectorsHub();

      // Global PD Workshops
      document.querySelectorAll("[data-pd-filter]").forEach(btn => {
        btn.addEventListener("click", () => {
          currentPdFilter = btn.getAttribute("data-pd-filter");
          document.querySelectorAll("[data-pd-filter]").forEach(b => {
            const active = b === btn;
            b.classList.toggle("bg-teal-700", active);
            b.classList.toggle("text-white", active);
            b.classList.toggle("border-teal-700", active);
            b.classList.toggle("bg-white", !active);
            b.classList.toggle("text-slate-700", !active);
            b.classList.toggle("border-slate-300", !active);
          });
          renderGlobalPD();
        });
      });
      renderGlobalPD();
        });
      });
      document.getElementById("ref-search").addEventListener("input", renderReferences);

      // Free library filter & search
      document.querySelectorAll("[data-lib-lang]").forEach(btn => {
        btn.addEventListener("click", () => {
          currentLibLang = btn.getAttribute("data-lib-lang");
          document.querySelectorAll("[data-lib-lang]").forEach(b => {
            const active = b === btn;
            b.classList.toggle("bg-teal-700", active);
            b.classList.toggle("text-white", active);
            b.classList.toggle("border-teal-700", active);
            b.classList.toggle("bg-white", !active);
            b.classList.toggle("text-slate-700", !active);
            b.classList.toggle("border-slate-300", !active);
          });
          renderFreeLibrary();
        });
      });
      document.getElementById("lib-topic").addEventListener("change", renderFreeLibrary);
      document.getElementById("lib-search").addEventListener("input", renderFreeLibrary);

      // Lesson prep
      document.getElementById("generate-lesson-btn").addEventListener("click", generateLessonPlan);
      document.getElementById("copy-lesson-btn").addEventListener("click", () => {
        const text = document.getElementById("lesson-output").innerText;
        copyTextSafe(text, "تم نسخ خطة الدرس التكيفية");
      });
      document.getElementById("print-lesson-btn").addEventListener("click", () => window.print());

      // Admin kit
      document.querySelectorAll(".admin-tpl-btn").forEach(btn => {
        btn.addEventListener("click", () => {
          currentAdminTpl = btn.getAttribute("data-admin-tpl");
          document.querySelectorAll(".admin-tpl-btn").forEach(b => {
            const active = b === btn;
            b.classList.toggle("bg-teal-700", active);
            b.classList.toggle("text-white", active);
            b.classList.toggle("border-teal-700", active);
            b.classList.toggle("bg-white", !active);
            b.classList.toggle("text-slate-700", !active);
            b.classList.toggle("border-slate-300", !active);
          });
          renderAdminPreview();
        });
      });
      ["adm-center", "adm-recipient", "adm-date", "adm-notes"].forEach(id => {
        document.getElementById(id).addEventListener("input", renderAdminPreview);
      });
      document.getElementById("copy-admin-btn").addEventListener("click", () => {
        const text = document.getElementById("admin-preview").textContent;
        copyTextSafe(text, "تم نسخ المستند الإداري");
      });

      // PPT & Events
      document.getElementById("ppt-type").addEventListener("change", renderPPT);
      document.getElementById("copy-ppt-btn").addEventListener("click", () => {
        const type = document.getElementById("ppt-type").value;
        const text = pptTemplates[type].map(s => `${s.title} (${s.layout})\n- ${s.bullets}`).join("\n\n");
        copyTextSafe(text, "تم نسخ هيكل عرض PowerPoint");
      });
      document.getElementById("event-type").addEventListener("change", renderEventPlanner);
      document.getElementById("event-checklist").addEventListener("change", (e) => {
        if (e.target.classList.contains("ev-check")) {
          const idx = e.target.getAttribute("data-ev-idx");
          if (e.target.checked) checkedEventItems.add(idx);
          else checkedEventItems.delete(idx);
          const type = document.getElementById("event-type").value;
          updateEventProgress(eventPlans[type].checklist.length);
        }
      });

      // Online-only connection check
      function checkConnection() {
        const gate = document.getElementById("offline-gate");
        if (!gate) return;
        const isOnline = navigator.onLine !== false;
        gate.classList.toggle("hidden", isOnline);
        gate.classList.toggle("flex", !isOnline);
      }
      window.addEventListener("online", checkConnection);
      window.addEventListener("offline", checkConnection);
      const retryOnlineBtn = document.getElementById("retry-online-btn");
      if (retryOnlineBtn) {
        retryOnlineBtn.addEventListener("click", () => {
          checkConnection();
          if (navigator.onLine !== false) showToast("تم التحقق: الاتصال بالإنترنت نشط");
        });
      }
      checkConnection();

      // Initial renders
      renderWorkshops();
      initChart();
      renderReferences();
      generateLessonPlan();
      renderAdminPreview();
      renderPPT();
      renderEventPlanner();
      if (window.lucide) lucide.createIcons();
    });
  </script>
</body>
</html>
