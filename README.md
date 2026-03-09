<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <meta name="theme-color" content="#0077FF">
    <meta name="description" content="Образовательный медицинский дашборд по реабилитации при эпилепсии для студентов-медиков и специалистов">
    <meta name="keywords" content="эпилепсия, реабилитация, психиатрия, неврология, МКБ-11, образование">
    
    <title>Эпилепсия: Реабилитация</title>
    
    <!-- VK Web App SDK -->
    <script src="https://unpkg.com/@vkontakte/vk-bridge/dist/browser.min.js"></script>
    
    <!-- VK UI Kit (опционально, для нативных компонентов) -->
    <link rel="stylesheet" href="https://unpkg.com/@vkontakte/vkui/dist/vkui.css">
    
    <style>
        /* ===== Базовые стили ===== */
        :root {
            --vkui--color_background: #FFFFFF;
            --vkui--color_text_primary: #000000;
            --vkui--color_text_secondary: #818C99;
            --vkui--color_accent_blue: #0077FF;
            --vkui--color_background_secondary: #F5F5F7;
            --safe-area-top: env(safe-area-inset-top, 0px);
            --safe-area-bottom: env(safe-area-inset-bottom, 0px);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            background-color: var(--vkui--color_background);
            color: var(--vkui--color_text_primary);
            line-height: 1.5;
            padding-top: calc(var(--safe-area-top) + 10px);
            padding-bottom: calc(var(--safe-area-bottom) + 10px);
            -webkit-tap-highlight-color: transparent;
        }

        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 0 16px;
        }

        /* ===== Навигация ===== */
        .nav-tabs {
            display: flex;
            overflow-x: auto;
            background: var(--vkui--color_background_secondary);
            padding: 8px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            -webkit-overflow-scrolling: touch;
        }

        .nav-tabs::-webkit-scrollbar {
            display: none;
        }

        .nav-tab {
            flex: 0 0 auto;
            padding: 8px 16px;
            margin: 0 4px;
            background: white;
            border: none;
            border-radius: 8px;
            font-size: 14px;
            font-weight: 500;
            color: var(--vkui--color_text_primary);
            cursor: pointer;
            transition: all 0.2s;
        }

        .nav-tab.active {
            background: var(--vkui--color_accent_blue);
            color: white;
        }

        .nav-tab:hover {
            opacity: 0.8;
        }

        /* ===== Секции ===== */
        .section {
            display: none;
            padding: 20px 0;
            animation: fadeIn 0.3s ease;
        }

        .section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* ===== Карточки ===== */
        .card {
            background: white;
            border-radius: 12px;
            padding: 16px;
            margin-bottom: 16px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
            border: 1px solid rgba(0,0,0,0.05);
        }

        .card-header {
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 12px;
            color: var(--vkui--color_accent_blue);
        }

        .card-content {
            font-size: 15px;
            line-height: 1.6;
        }

        /* ===== Статистика ===== */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
            margin-bottom: 20px;
        }

        .stat-item {
            background: linear-gradient(135deg, #0077FF 0%, #0055CC 100%);
            color: white;
            padding: 16px;
            border-radius: 12px;
            text-align: center;
        }

        .stat-value {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 4px;
        }

        .stat-label {
            font-size: 12px;
            opacity: 0.9;
        }

        /* ===== Таблицы ===== */
        .table-container {
            overflow-x: auto;
            margin: 16px 0;
            -webkit-overflow-scrolling: touch;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            font-size: 14px;
            min-width: 500px;
        }

        th, td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid rgba(0,0,0,0.1);
        }

        th {
            background: var(--vkui--color_background_secondary);
            font-weight: 600;
            position: sticky;
            top: 0;
        }

        tr:last-child td {
            border-bottom: none;
        }

        /* ===== Кнопки ===== */
        .btn {
            display: inline-block;
            width: 100%;
            padding: 14px 20px;
            background: var(--vkui--color_accent_blue);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
            text-align: center;
            margin-bottom: 12px;
        }

        .btn:hover {
            opacity: 0.9;
            transform: translateY(-1px);
        }

        .btn:active {
            transform: translateY(0);
        }

        .btn-secondary {
            background: var(--vkui--color_background_secondary);
            color: var(--vkui--color_text_primary);
        }

        /* ===== Селектор реабилитации ===== */
        .rehab-selector {
            margin: 20px 0;
        }

        .rehab-options {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 16px;
        }

        .rehab-option {
            flex: 1 1 auto;
            min-width: 140px;
            padding: 12px;
            background: var(--vkui--color_background_secondary);
            border: 2px solid transparent;
            border-radius: 8px;
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.2s;
            text-align: center;
        }

        .rehab-option.selected {
            border-color: var(--vkui--color_accent_blue);
            background: rgba(0, 119, 255, 0.1);
            color: var(--vkui--color_accent_blue);
        }

        .rehab-result {
            background: var(--vkui--color_background_secondary);
            padding: 16px;
            border-radius: 12px;
            margin-top: 16px;
            display: none;
        }

        .rehab-result.active {
            display: block;
            animation: slideIn 0.3s ease;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* ===== Списки ===== */
        .info-list {
            list-style: none;
            padding: 0;
        }

        .info-list li {
            padding: 10px 0;
            border-bottom: 1px solid rgba(0,0,0,0.05);
            display: flex;
            align-items: flex-start;
        }

        .info-list li:last-child {
            border-bottom: none;
        }

        .info-list li::before {
            content: "•";
            color: var(--vkui--color_accent_blue);
            font-weight: bold;
            margin-right: 10px;
            font-size: 18px;
        }

        /* ===== Уведомления ===== */
        .notification {
            position: fixed;
            bottom: calc(var(--safe-area-bottom) + 20px);
            left: 50%;
            transform: translateX(-50%) translateY(100px);
            background: #333;
            color: white;
            padding: 12px 24px;
            border-radius: 8px;
            font-size: 14px;
            opacity: 0;
            transition: all 0.3s;
            z-index: 1000;
            max-width: 90%;
            text-align: center;
        }

        .notification.show {
            transform: translateX(-50%) translateY(0);
            opacity: 1;
        }

        /* ===== Футер ===== */
        .footer {
            text-align: center;
            padding: 20px 16px;
            font-size: 12px;
            color: var(--vkui--color_text_secondary);
            border-top: 1px solid rgba(0,0,0,0.1);
            margin-top: 20px;
        }

        .disclaimer {
            background: #FFF3CD;
            border: 1px solid #FFE69C;
            padding: 12px;
            border-radius: 8px;
            font-size: 13px;
            margin-bottom: 16px;
            color: #856404;
        }

        /* ===== Адаптивность ===== */
        @media (max-width: 360px) {
            .stat-value {
                font-size: 20px;
            }
            
            .nav-tab {
                padding: 6px 12px;
                font-size: 13px;
            }
            
            .card-header {
                font-size: 16px;
            }
        }

        /* ===== Тёмная тема (автоматически от VK) ===== */
        @media (prefers-color-scheme: dark) {
            :root {
                --vkui--color_background: #191919;
                --vkui--color_text_primary: #FFFFFF;
                --vkui--color_text_secondary: #AAAAAA;
                --vkui--color_background_secondary: #2D2D2D;
            }
            
            .card {
                background: #2D2D2D;
                border-color: rgba(255,255,255,0.1);
            }
            
            .nav-tab {
                background: #2D2D2D;
            }
            
            table th {
                background: #2D2D2D;
            }
            
            .disclaimer {
                background: #3D3D2D;
                border-color: #5D5D3D;
                color: #DDDD99;
            }
        }

        /* ===== Индикатор загрузки ===== */
        .loading {
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 40px;
        }

        .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid var(--vkui--color_background_secondary);
            border-top-color: var(--vkui--color_accent_blue);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <!-- Индикатор загрузки -->
    <div id="loading" class="loading">
        <div class="spinner"></div>
    </div>

    <!-- Основной контент (скрыт до инициализации VK Bridge) -->
    <div id="app" style="display: none;">
        <div class="container">
            <!-- Дисклеймер -->
            <div class="disclaimer">
                ⚠️ Информация предназначена для специалистов. Не является заменой очной консультации врача.
            </div>

            <!-- Статистика -->
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-value">2,5 млн</div>
                    <div class="stat-label">Больных эпилепсией в СНГ</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">75%</div>
                    <div class="stat-label">Имеют психические расстройства</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">68,5%</div>
                    <div class="stat-label">Нарушений в межприступный период</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">90%</div>
                    <div class="stat-label">Достигают длительной ремиссии</div>
                </div>
            </div>

            <!-- Навигация -->
            <nav class="nav-tabs">
                <button class="nav-tab active" data-section="overview">Обзор</button>
                <button class="nav-tab" data-section="classification">Классификация</button>
                <button class="nav-tab" data-section="psychotic">Психотические формы</button>
                <button class="nav-tab" data-section="medication">Терапия</button>
                <button class="nav-tab" data-section="rehab">Реабилитация</button>
                <button class="nav-tab" data-section="selector">Подбор методов</button>
            </nav>

            <!-- Секция: Обзор -->
            <section id="overview" class="section active">
                <div class="card">
                    <div class="card-header">📋 Типы психических расстройств</div>
                    <ul class="info-list card-content">
                        <li><strong>Пароксизмальные:</strong> психические припадки, дисфории, сумеречные состояния</li>
                        <li><strong>Перманентные:</strong> изменения личности, деменция</li>
                        <li><strong>По отношению к припадку:</strong> продромальные, иктальные, постиктальные, интериктальные</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">🏷️ Коды по МКБ-10</div>
                    <ul class="info-list card-content">
                        <li><strong>G40.0–G40.9:</strong> Эпилепсия различных форм</li>
                        <li><strong>F07.02:</strong> Расстройства личности при эпилепсии</li>
                        <li><strong>F06.811:</strong> Расстройства поведения</li>
                        <li><strong>F06.3:</strong> Органическое аффективное расстройство</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">🎯 Ключевые принципы реабилитации</div>
                    <ul class="info-list card-content">
                        <li>Мультидисциплинарный подход</li>
                        <li>Контроль над припадками как основа</li>
                        <li>Индивидуальная психофармакотерапия</li>
                        <li>Психотерапия и нейропсихологическая коррекция</li>
                        <li>Социально-трудовая реабилитация</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">📈 Прогноз реабилитации</div>
                    <ul class="info-list card-content">
                        <li><strong>70%:</strong> Эффективность лечебно-реабилитационных мероприятий</li>
                        <li><strong>30-50%:</strong> Компенсация болезненного процесса</li>
                        <li><strong>3-5 лет:</strong> Период регресса изменений личности при ремиссии</li>
                    </ul>
                </div>
            </section>

            <!-- Секция: Классификация -->
            <section id="classification" class="section">
                <div class="card">
                    <div class="card-header">📊 Классификация психических расстройств при эпилепсии</div>
                    <div class="table-container">
                        <table>
                            <thead>
                                <tr>
                                    <th>Категория</th>
                                    <th>Подтип</th>
                                    <th>Характеристика</th>
                                    <th>Тип</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td rowspan="4">По отношению к припадку</td>
                                    <td>Продромальные</td>
                                    <td>Психические нарушения перед припадком (у 10% больных)</td>
                                    <td>Непсихотические</td>
                                </tr>
                                <tr>
                                    <td>Иктальные</td>
                                    <td>Психические расстройства как компонент припадка</td>
                                    <td>Оба типа</td>
                                </tr>
                                <tr>
                                    <td>Постиктальные</td>
                                    <td>После припадка (через 12-120 часов)</td>
                                    <td>Психотические</td>
                                </tr>
                                <tr>
                                    <td>Интериктальные</td>
                                    <td>В межприступный периоде</td>
                                    <td>Оба типа</td>
                                </tr>
                                <tr>
                                    <td rowspan="2">По длительности</td>
                                    <td>Пароксизмальные</td>
                                    <td>Психические припадки (1-2 с — 10 мин), транзиторные расстройства (часы-сутки)</td>
                                    <td>Оба типа</td>
                                </tr>
                                <tr>
                                    <td>Перманентные</td>
                                    <td>Изменения личности, деменция</td>
                                    <td>Непсихотические</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

                <div class="card">
                    <div class="card-header">🌍 Коды МКБ-11 и DSM-5</div>
                    <div class="card-content">
                        <p><strong>МКБ-11:</strong></p>
                        <ul class="info-list">
                            <li>8A60–8A6Z: Эпилепсия или припадки</li>
                            <li>Блок 6E: Вторичные психические синдромы, связанные с заболеваниями нервной системы</li>
                            <li>Психотические расстройства при эпилепсии кодируются как вторичные синдромы</li>
                        </ul>
                        <p style="margin-top: 16px;"><strong>DSM-5:</strong></p>
                        <ul class="info-list">
                            <li>Психотическое расстройство вследствие другого медицинского состояния (с уточнением бреда/галлюцинаций)</li>
                            <li>Депрессивное расстройство вследствие другого медицинского состояния</li>
                            <li>Требуется документирование связи с эпилепсией</li>
                        </ul>
                    </div>
                </div>
            </section>

            <!-- Секция: Психотические формы -->
            <section id="psychotic" class="section">
                <div class="card">
                    <div class="card-header">⚡ Иктальные психозы</div>
                    <ul class="info-list card-content">
                        <li><strong>Тип:</strong> простые и сложные парциальные припадки</li>
                        <li><strong>Проявления:</strong> аффективные, поведенческие нарушения, расстройства восприятия</li>
                        <li><strong>Особенность:</strong> бессудорожный эпилептический статус может протекать под маской шизофрении</li>
                        <li><strong>Сознание:</strong> помрачение с автоматизмами</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">🔄 Постиктальные психозы</div>
                    <ul class="info-list card-content">
                        <li><strong>Начало:</strong> через 12-120 часов после серии припадков</li>
                        <li><strong>Проявления:</strong> помрачение сознания, острый полиморфный бред</li>
                        <li><strong>Аффект:</strong> гипоманиакальное состояние с сексуальной расторможенностью</li>
                        <li><strong>Длительность:</strong> от нескольких дней до 1-2 недель</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">🧠 Интериктальные психозы</div>
                    <div class="card-content">
                        <p>Возникают при уменьшении частоты припадков у больных с височной эпилепсией (длительность заболевания > 15 лет)</p>
                        <h4 style="margin: 16px 0 8px 0; color: var(--vkui--color_accent_blue);">Острый параноид</h4>
                        <p>Чувственный бред с иллюзорным восприятием, устрашающие галлюцинации, возбуждение, агрессивность</p>
                        <h4 style="margin: 16px 0 8px 0; color: var(--vkui--color_accent_blue);">Острые аффективные (дисфорические) психозы</h4>
                        <p>Тоскливо-злобное настроение, депрессивные состояния, маниакально-экстатические состояния</p>
                        <h4 style="margin: 16px 0 8px 0; color: var(--vkui--color_accent_blue);">Синдром Ландольта</h4>
                        <p>Галлюцинаторно-бредовая картина при «насильственной нормализации» ЭЭГ (8% интериктальных психозов). Лучший прогноз, требует пересмотра противоэпилептической терапии</p>
                    </div>
                </div>

                <div class="card">
                    <div class="card-header">📋 Хронические эпилептические психозы (шизофреноподобные)</div>
                    <div class="table-container">
                        <table>
                            <thead>
                                <tr>
                                    <th>Форма</th>
                                    <th>Характеристика</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>Паранояльная</td>
                                    <td>Бред обыденного содержания (отношения, отравления, ущерба, ипохондрический, религиозный)</td>
                                </tr>
                                <tr>
                                    <td>Галлюцинаторно-параноидная</td>
                                    <td>Синдром Кандинского–Клерамбо, «галлюцинаторный бред»</td>
                                </tr>
                                <tr>
                                    <td>Парафренная</td>
                                    <td>Вербальные галлюцинации, мегаломанический бред фантастического содержания</td>
                                </tr>
                                <tr>
                                    <td>Кататоническая</td>
                                    <td>Субступор с негативизмом, мутизмом, импульсивным возбуждением, эхолалиями</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </section>

            <!-- Секция: Медикаментозная терапия -->
            <section id="medication" class="section">
                <div class="card">
                    <div class="card-header">💊 Антиэпилептические препараты (основа)</div>
                    <ul class="info-list card-content">
                        <li><strong>Вальпроаты:</strong> нейропротективный эффект</li>
                        <li><strong>Ламотриджин:</strong> нейропротекция + стабилизация настроения</li>
                        <li><strong>Леветирацетам:</strong> нейропротекция</li>
                        <li><strong>Карбамазепин:</strong> противоэпилептическое + нормотимическое действие</li>
                        <li style="color: #DC3545;"><strong>Избегать:</strong> барбитураты, полипрагмазия (риск «насильственной нормализации»)</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">🧪 Антипсихотики (первая линия)</div>
                    <ul class="info-list card-content">
                        <li><strong>Арипипразол:</strong> 5-10 мг/день → 15-20 мг/день</li>
                        <li><strong>Рисперидон:</strong> 2 мг/день → 4 мг/день (при тяжёлой симптоматике)</li>
                        <li><strong>Галоперидол:</strong> 2-10 мг/день (при недоступности атипичных)</li>
                        <li><strong>Принцип:</strong> начинать с низких доз (25-50% от целевой), повышать каждые 2-5 дней</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">🔬 Другие атипичные антипсихотики</div>
                    <ul class="info-list card-content">
                        <li><strong>Оланзапин:</strong> эффективен при негативной симптоматике</li>
                        <li><strong>Кветиапин:</strong> при коморбидной тревоге</li>
                        <li>Труксал, Солиан, Клопиксол-акуфаз, Флуанксол</li>
                        <li><strong>Преимущества:</strong> меньше экстрапирамидных эффектов, улучшение когнитивных функций</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">😔 Антидепрессанты (при коморбидной депрессии)</div>
                    <ul class="info-list card-content">
                        <li><strong>Пароксетин:</strong> 20-40 мг/день (СИОЗС)</li>
                        <li><strong>Сертралин:</strong> 50-100 мг/день (СИОЗС)</li>
                        <li><strong>Феварин:</strong> 50-100 мг/день</li>
                        <li style="color: #DC3545;"><strong>Осторожно:</strong> трициклические антидепрессанты (проконвульсивный эффект у 0,3-15%)</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">💤 Транквилизаторы</div>
                    <ul class="info-list card-content">
                        <li>Диазепам, нитразепам, феназепам</li>
                        <li>Грандаксин: дневной транквилизатор</li>
                        <li><strong>Режим:</strong> курсы 3-4 недели или разово</li>
                        <li style="color: #DC3545;"><strong>Не применять</strong> как монотерапию при длительных психотических состояниях</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">🧬 Нейрометаболические средства</div>
                    <ul class="info-list card-content">
                        <li><strong>Пантогам:</strong> ноотроп с противосудорожным эффектом</li>
                        <li><strong>Ноофен (Фенибут):</strong> транквилизирующий + ноотропный эффект</li>
                        <li><strong>Блокаторы кальциевых каналов:</strong> профилактика повторных психозов, замедление прогрессирования энцефалопатии</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">⚠️ Специфика синдрома Ландольта</div>
                    <div class="card-content">
                        <p><strong>Психоз «насильственной нормализации» требует особого подхода:</strong></p>
                        <ul class="info-list">
                            <li><strong>Провоцирующие факторы:</strong> барбитураты, бензодиазепины, сукцинимиды, высокие дозы топирамата и леветирацетама</li>
                            <li><strong>Тактика:</strong> пересмотр противоэпилептической терапии, снижение доз или отмена провоцирующих препаратов</li>
                            <li><strong>Прогноз:</strong> более благоприятный исход по сравнению с другими формами</li>
                        </ul>
                    </div>
                </div>
            </section>

            <!-- Секция: Реабилитация -->
            <section id="rehab" class="section">
                <div class="card">
                    <div class="card-header">🧠 Когнитивно-поведенческая терапия (КПТ)</div>
                    <ul class="info-list card-content">
                        <li>Идентификация дезадаптивных мыслительных паттернов</li>
                        <li>Управление стрессом и триггерами приступов</li>
                        <li>Применение противодействующих стратегий</li>
                        <li><strong>Эффективность:</strong> 45-90% ответа</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">🧘 Майндфулнесс (программа UPLIFT)</div>
                    <ul class="info-list card-content">
                        <li>Основана на MBCT (mindfulness-based cognitive therapy)</li>
                        <li>Снижение частоты приступов</li>
                        <li>Уменьшение депрессивных эпизодов</li>
                        <li>Улучшение удовлетворённости жизнью</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">💬 Рациональная психотерапия</div>
                    <ul class="info-list card-content">
                        <li>Основной метод в стандартах стационарной помощи</li>
                        <li>Формирование адекватного отношения к болезни</li>
                        <li>Коррекция внутренней картины болезни</li>
                        <li>Снижение стигматизации</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">👨‍👩‍👧‍👦 Семейная системная терапия</div>
                    <ul class="info-list card-content">
                        <li>Рассмотрение пациента в контексте семьи</li>
                        <li>Работа с эмоциональными паттернами</li>
                        <li>Обучение членов семьи</li>
                        <li>Снижение семейного стресса</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">🔬 Нейропсихологическая реабилитация (программа CoRE)</div>
                    <div class="card-content">
                        <p><strong>Cognitive Rehabilitation for Epilepsy — 8-недельный курс для восстановления когнитивных функций</strong></p>
                        <h4 style="margin: 16px 0 8px 0; color: var(--vkui--color_accent_blue);">Психообразование</h4>
                        <p>Понимание механизмов когнитивных нарушений при эпилепсии</p>
                        <h4 style="margin: 16px 0 8px 0; color: var(--vkui--color_accent_blue);">Стратегии копинга</h4>
                        <p>Техники преодоления когнитивных трудностей в повседневной жизни</p>
                        <h4 style="margin: 16px 0 8px 0; color: var(--vkui--color_accent_blue);">Компенсаторные техники</h4>
                        <p>Использование внешних средств для компенсации дефицитов памяти и внимания</p>
                        <h4 style="margin: 16px 0 8px 0; color: var(--vkui--color_accent_blue);">Реституционные техники</h4>
                        <p>Упражнения для восстановления нарушенных когнитивных функций</p>
                        <p style="margin-top: 12px;"><strong>Формат:</strong> 6 индивидуальных + 2 групповых занятия</p>
                    </div>
                </div>

                <div class="card">
                    <div class="card-header">⚡ Транскраниальная магнитная стимуляция (ТМС)</div>
                    <ul class="info-list card-content">
                        <li><strong>Метод:</strong> низкочастотная ТМС (0,3-1 Гц)</li>
                        <li><strong>Показания:</strong> фармакорезистентные формы эпилепсии</li>
                        <li><strong>Результаты:</strong> снижение частоты приступов на 60% за 4 недели</li>
                        <li><strong>Дополнительный эффект:</strong> улучшение картины ЭЭГ</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">💼 Социально-трудовая реабилитация</div>
                    <ul class="info-list card-content">
                        <li>Трудотерапия: восстановление профессиональных навыков</li>
                        <li>Обучение навыкам поиска работы</li>
                        <li><strong>Эффективность:</strong> увеличение занятости в 3 раза после программы</li>
                        <li><strong>Борьба со стигматизацией — центральная задача</strong></li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-header">📊 Результаты психотерапии (Кокрановский обзор 2020)</div>
                    <div class="card-content">
                        <p><strong>Навыковые психологические интервенции улучшают качество жизни по всем шести подшкалам:</strong></p>
                        <ul class="info-list">
                            <li>Эмоциональное благополучие</li>
                            <li>Энергия и жизненная сила</li>
                            <li>Общее благополучие</li>
                            <li>Тревога по поводу приступов</li>
                            <li>Эффекты медикаментов</li>
                            <li>Социальное функционирование</li>
                        </ul>
                    </div>
                </div>

                <div class="card">
                    <div class="card-header">🏥 Стандарты стационарной помощи (НИПНИ им. В.М. Бехтерева)</div>
                    <div class="card-content">
                        <p><strong>Стационарное лечение больных эпилепсией с изменениями личности и расстройствами поведения (F07.02, F06.811, F06.922)</strong></p>
                        <ul class="info-list">
                            <li><strong>Длительность:</strong> 30-60 дней</li>
                            <li><strong>Консультации:</strong> Психолог и психиатр</li>
                            <li><strong>Диагностика:</strong> ЭЭГ, МРТ головного мозга, батарея из 12 психологических методик</li>
                            <li><strong>Подбор терапии:</strong> Моно- или политерапия индивидуально</li>
                            <li><strong>Психотерапия:</strong> Рациональная психотерапия как основной метод</li>
                            <li><strong>Реабилитация:</strong> Социально-трудовая реабилитация</li>
                            <li><strong>При неэффективности:</strong> Направление на психо-МСЭК</li>
                            <li><strong>Эффективность:</strong> 70% по данным института Бехтерева</li>
                        </ul>
                    </div>
                </div>
            </section>

            <!-- Секция: Интерактивный подбор методов -->
            <section id="selector" class="section">
                <div class="card">
                    <div class="card-header">🎯 Интерактивный подбор методов реабилитации</div>
                    <p class="card-content" style="margin-bottom: 16px;">Выберите тип психического расстройства:</p>
                    
                    <div class="rehab-options">
                        <div class="rehab-option" data-rehab="ictal">Иктальные психозы</div>
                        <div class="rehab-option" data-rehab="postictal">Постиктальные психозы</div>
                        <div class="rehab-option" data-rehab="interictal">Интериктальные психозы</div>
                        <div class="rehab-option" data-rehab="chronic">Хронические психозы</div>
                        <div class="rehab-option" data-rehab="landolt">Синдром Ландольта</div>
                        <div class="rehab-option" data-rehab="personality">Изменения личности</div>
                        <div class="rehab-option" data-rehab="depression">Коморбидная депрессия</div>
                    </div>

                    <div id="rehab-result" class="rehab-result">
                        <h4 id="rehab-title" style="color: var(--vkui--color_accent_blue); margin-bottom: 12px;"></h4>
                        <div id="rehab-content"></div>
                    </div>
                </div>
            </section>

            <!-- Футер -->
            <footer class="footer">
                <p>Дашборд основан на исследовании «Реабилитация при эпилепсии с выделением форм с психотическими нарушениями»</p>
                <p style="margin-top: 8px;">Источники: МКБ-10, МКБ-11, DSM-5, клинические рекомендации РФ, международные исследования</p>
                <p style="margin-top: 16px; font-size: 11px; opacity: 0.7;">© 2025 | VK Mini App ID: 54476393</p>
            </footer>
        </div>
    </div>

    <!-- Уведомления -->
    <div id="notification" class="notification"></div>

    <script>
        // ===== Данные для интерактивного подбора =====
        const rehabData = {
            ictal: {
                title: '🔄 Реабилитация при иктальных психозах',
                content: `
                    <ul class="info-list">
                        <li><strong>Медикаментозно:</strong> Оптимизация АЭП (вальпроаты, ламотриджин, леветирацетам)</li>
                        <li><strong>При бессудорожном статусе:</strong> Нейролептики в невысоких дозах краткосрочно</li>
                        <li><strong>Психотерапия:</strong> Рациональная психотерапия после купирования</li>
                        <li><strong>Мониторинг:</strong> ЭЭГ для контроля эпилептиформной активности</li>
                        <li><strong>Цель:</strong> Предотвращение повышения частоты приступов</li>
                    </ul>
                `
            },
            postictal: {
                title: '🔄 Реабилитация при постиктальных психозах',
                content: `
                    <ul class="info-list">
                        <li><strong>Медикаментозно:</strong> АЭП + нейролептики в малых/средних дозах (арипипразол 5-15 мг, рисперидон 2-4 мг)</li>
                        <li><strong>Дополнительно:</strong> Транквилизаторы (диазепам, феназепам) курсами 3-4 недели</li>
                        <li><strong>При затяжных формах без помрачения:</strong> + антидепрессанты (пароксетин, сертралин)</li>
                        <li><strong>Длительность:</strong> До полного разрешения симптоматики (1-2 недели)</li>
                        <li><strong>Нейропротекция:</strong> Пантогам, ноофен для профилактики рецидивов</li>
                    </ul>
                `
            },
            interictal: {
                title: '🧠 Реабилитация при интериктальных психозах',
                content: `
                    <ul class="info-list">
                        <li><strong>Медикаментозно:</strong> Базисная антипсихотическая терапия (арипипразол 15-20 мг или рисперидон 2-4 мг)</li>
                        <li><strong>Комбинация:</strong> АЭП + антипсихотики + антидепрессанты (при необходимости) + транквилизаторы</li>
                        <li><strong>КПТ:</strong> Идентификация триггеров, управление стрессом</li>
                        <li><strong>Нейропсихологическая реабилитация:</strong> Программа CoRE (8 недель)</li>
                        <li><strong>Семейная терапия:</strong> Работа с семейной системой</li>
                        <li><strong>Прогноз:</strong> Лучше, чем при первичных психозах; требует более низких доз антипсихотиков</li>
                    </ul>
                `
            },
            chronic: {
                title: '📋 Реабилитация при хронических (шизофреноподобных) психозах',
                content: `
                    <ul class="info-list">
                        <li><strong>Медикаментозно:</strong> Нейролептики как базисная терапия в комбинации с индивидуально подобранными АЭП</li>
                        <li><strong>Атипичные антипсихотики:</strong> Оланзапин, кветиапин, арипипразол, рисперидон</li>
                        <li><strong>При галлюцинаторно-параноидной форме:</strong> Галоперидол 2-10 мг + АЭП</li>
                        <li><strong>Длительная терапия:</strong> Антидепрессанты и транквилизаторы курсами</li>
                        <li><strong>Рациональная психотерапия:</strong> Коррекция внутренней картины болезни</li>
                        <li><strong>Социально-трудовая реабилитация:</strong> Трудотерапия, обучение навыкам</li>
                        <li><strong>Нейрометаболическая терапия:</strong> Замедление прогрессирования энцефалопатии</li>
                    </ul>
                `
            },
            landolt: {
                title: '⚠️ Реабилитация при синдроме Ландольта',
                content: `
                    <ul class="info-list">
                        <li><strong>Главное:</strong> Пересмотр противоэпилептической терапии</li>
                        <li><strong>Отмена провокаторов:</strong> Барбитураты, бензодиазепины, сукцинимиды</li>
                        <li><strong>Снижение доз:</strong> Топирамат, леветирацетам (при высоких дозах)</li>
                        <li><strong>Избегать полипрагмазии:</strong> Минимизация количества АЭП</li>
                        <li><strong>Антипсихотики:</strong> Арипипразол или рисперидон в низких дозах</li>
                        <li><strong>Прогноз:</strong> Более благоприятный исход по сравнению с другими психозами</li>
                        <li><strong>Мониторинг:</strong> Регулярный контроль ЭЭГ (отслеживание «нормализации»)</li>
                    </ul>
                `
            },
            personality: {
                title: '👤 Реабилитация при изменениях личности',
                content: `
                    <ul class="info-list">
                        <li><strong>Основа:</strong> Контроль над припадками (чем больше ремиссия, тем стабильнее результаты)</li>
                        <li><strong>Медикаментозно:</strong> Карбамазепин (противоэпилептический + нормотимический эффект)</li>
                        <li><strong>Рациональная психотерапия:</strong> Коррекция характерологических особенностей</li>
                        <li><strong>КПТ:</strong> Работа с вязкостью, обстоятельностью, вспыльчивостью</li>
                        <li><strong>Семейная терапия:</strong> Обучение родственников конструктивному взаимодействию</li>
                        <li><strong>Социальная реабилитация:</strong> Трудотерапия, профориентация</li>
                        <li><strong>Прогноз:</strong> Регресс изменений возможен в течение 3-5 лет при ремиссии</li>
                    </ul>
                `
            },
            depression: {
                title: '😔 Реабилитация при коморбидной депрессии',
                content: `
                    <ul class="info-list">
                        <li><strong>Медикаментозно:</strong> СИОЗС (пароксетин 20-40 мг, сертралин 50-100 мг, феварин 50-100 мг)</li>
                        <li><strong>Важно:</strong> Продолжение приёма АЭП на фоне антидепрессантов</li>
                        <li style="color: #DC3545;"><strong>Осторожно:</strong> Трициклические антидепрессанты (проконвульсивный эффект)</li>
                        <li><strong>КПТ:</strong> Работа с депрессивными мыслительными паттернами</li>
                        <li><strong>Майндфулнесс:</strong> Программа UPLIFT снижает депрессивные эпизоды</li>
                        <li><strong>Поведенческая активация:</strong> Структурирование дня, физическая активность</li>
                        <li><strong>Распространённость:</strong> Депрессия встречается у 25-50% больных эпилепсией</li>
                    </ul>
                `
            }
        };

        // ===== Инициализация VK Bridge =====
        document.addEventListener('DOMContentLoaded', function() {
            // Инициализация VK Bridge
            if (window.vkBridge) {
                vkBridge.send('VKWebAppInit')
                    .then(() => {
                        console.log('✅ VK Mini App initialized successfully');
                        showNotification('Приложение загружено');
                        
                        // Получение информации о пользователе (опционально)
                        return vkBridge.send('VKWebAppGetUserInfo');
                    })
                    .then(data => {
                        if (data && data.first_name) {
                            console.log(`👤 Пользователь: ${data.first_name} ${data.last_name}`);
                        }
                    })
                    .catch(err => {
                        console.error('❌ VK Init error:', err);
                        showNotification('Ошибка инициализации VK');
                    });

                // Подписка на события VK Bridge
                vkBridge.subscribe(event => {
                    console.log('📡 VK Bridge Event:', event.type, event.data);
                    
                    // Обработка события показа приложения
                    if (event.type === 'VKWebAppViewShow') {
                        console.log('👁 Приложение показано пользователю');
                    }
                    
                    // Обработка события клавиатуры
                    if (event.type === 'VKWebAppKeyboardShown') {
                        document.body.style.paddingBottom = `${event.data.height}px`;
                    }
                    
                    if (event.type === 'VKWebAppKeyboardHidden') {
                        document.body.style.paddingBottom = '';
                    }
                });

                // Настройка цветов схемы (для тёмной темы)
                vkBridge.send('VKWebAppGetViewInfo')
                    .then(data => {
                        if (data.scheme) {
                            document.documentElement.setAttribute('data-color-scheme', data.scheme);
                        }
                    })
                    .catch(() => {});
            } else {
                console.warn('⚠️ VK Bridge not available (running outside VK)');
                showNotification('Запущено вне VK');
            }

            // Скрытие индикатора загрузки и показ приложения
            setTimeout(() => {
                document.getElementById('loading').style.display = 'none';
                document.getElementById('app').style.display = 'block';
            }, 500);
        });

        // ===== Навигация по секциям =====
        document.querySelectorAll('.nav-tab').forEach(tab => {
            tab.addEventListener('click', function() {
                // Удаление активного класса у всех табов
                document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
                document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
                
                // Добавление активного класса текущему табу
                this.classList.add('active');
                const sectionId = this.getAttribute('data-section');
                document.getElementById(sectionId).classList.add('active');
                
                // Прокрутка к началу секции
                window.scrollTo({ top: 0, behavior: 'smooth' });
                
                // Haptic feedback (тактильная отдача через VK)
                if (window.vkBridge) {
                    vkBridge.send('VKWebAppTapticImpactOccurred', { style: 'light' });
                }
            });
        });

        // ===== Интерактивный подбор методов реабилитации =====
        document.querySelectorAll('.rehab-option').forEach(option => {
            option.addEventListener('click', function() {
                // Удаление выделения у всех опций
                document.querySelectorAll('.rehab-option').forEach(o => o.classList.remove('selected'));
                
                // Выделение текущей опции
                this.classList.add('selected');
                
                // Получение данных для выбранной опции
                const rehabType = this.getAttribute('data-rehab');
                const data = rehabData[rehabType];
                
                if (data) {
                    // Заполнение результата
                    document.getElementById('rehab-title').textContent = data.title;
                    document.getElementById('rehab-content').innerHTML = data.content;
                    
                    // Показ результата
                    document.getElementById('rehab-result').classList.add('active');
                    
                    // Прокрутка к результату
                    setTimeout(() => {
                        document.getElementById('rehab-result').scrollIntoView({ 
                            behavior: 'smooth', 
                            block: 'start' 
                        });
                    }, 100);
                    
                    // Haptic feedback
                    if (window.vkBridge) {
                        vkBridge.send('VKWebAppTapticImpactOccurred', { style: 'medium' });
                    }
                }
            });
        });

        // ===== Уведомления =====
        function showNotification(message) {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.classList.add('show');
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }

        // ===== Кнопка "Поделиться" (опционально) =====
        function shareApp() {
            if (window.vkBridge) {
                vkBridge.send('VKWebAppShare', { link: window.location.href })
                    .then(() => showNotification('Ссылка отправлена'))
                    .catch(() => showNotification('Ошибка отправки'));
            } else {
                showNotification('Функция доступна только в VK');
            }
        }

        // ===== Кнопка "Добавить на главный экран" (опционально) =====
        function addToHomeScreen() {
            if (window.vkBridge) {
                vkBridge.send('VKWebAppAddToHomeScreenInfo')
                    .then(() => {
                        vkBridge.send('VKWebAppShowStoryBox', {
                            background_type: 'gradient',
                            gradient: ['#0077FF', '#0055CC']
                        });
                        showNotification('Приложение добавлено');
                    })
                    .catch(() => showNotification('Не удалось добавить'));
            }
        }

        // ===== Обработка ошибок =====
        window.addEventListener('error', function(e) {
            console.error('Global error:', e.error);
            showNotification('Произошла ошибка');
        });

        // ===== Оптимизация производительности =====
        // Ленивая загрузка изображений (если добавите изображения)
        document.addEventListener('DOMContentLoaded', function() {
            const lazyImages = document.querySelectorAll('img[data-src]');
            
            if ('IntersectionObserver' in window) {
                const imageObserver = new IntersectionObserver((entries, observer) => {
                    entries.forEach(entry => {
                        if (entry.isIntersecting) {
                            const img = entry.target;
                            img.src = img.dataset.src;
                            img.removeAttribute('data-src');
                            observer.unobserve(img);
                        }
                    });
                });
                
                lazyImages.forEach(img => imageObserver.observe(img));
            }
        });

        // ===== Service Worker для офлайн-режима (опционально) =====
        if ('serviceWorker' in navigator) {
            window.addEventListener('load', () => {
                // navigator.serviceWorker.register('/sw.js')
                //     .then(reg => console.log('SW registered:', reg))
                //     .catch(err => console.log('SW registration failed:', err));
            });
        }
    </script>
</body>
</html>
