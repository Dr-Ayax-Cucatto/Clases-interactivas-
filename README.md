<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guía Interactiva: Antipsicóticos Atípicos</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #1abc9c;
            --background: #f4f7f6;
            --card-bg: #ffffff;
            --text-main: #333333;
            --text-muted: #666666;
            --danger: #e74c3c;
            --warning: #f1c40f;
            --success: #2ecc71;
            --border: #e0e0e0;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Inter', sans-serif;
        }

        body {
            background-color: var(--background);
            color: var(--text-main);
            line-height: 1.6;
            padding-bottom: 50px;
        }

        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 40px 20px;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }

        header h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            letter-spacing: -0.5px;
        }

        header p {
            font-size: 1.1rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto;
        }

        .container {
            max-width: 1000px;
            margin: -30px auto 30px;
            padding: 0 20px;
            position: relative;
            z-index: 10;
        }

        /* Mechanism Section */
        .mechanism-box {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 25px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            margin-bottom: 30px;
            border-top: 5px solid var(--accent);
        }

        .mechanism-box h2 {
            color: var(--primary);
            margin-bottom: 15px;
            font-size: 1.5rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .mech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .mech-card {
            background: #f8fafc;
            padding: 15px;
            border-radius: 8px;
            border-left: 4px solid var(--secondary);
        }

        /* Tabs System */
        .tabs-header {
            display: flex;
            background: var(--card-bg);
            border-radius: 12px 12px 0 0;
            overflow: hidden;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }

        .tab-btn {
            flex: 1;
            padding: 18px;
            background: none;
            border: none;
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--text-muted);
            cursor: pointer;
            transition: all 0.3s ease;
            border-bottom: 3px solid transparent;
        }

        .tab-btn:hover {
            background: #f1f5f9;
            color: var(--primary);
        }

        .tab-btn.active {
            color: var(--secondary);
            border-bottom-color: var(--secondary);
            background: #f8fafc;
        }

        .tab-content {
            display: none;
            background: var(--card-bg);
            padding: 30px;
            border-radius: 0 0 12px 12px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            margin-bottom: 30px;
        }

        .tab-content.active {
            display: block;
            animation: fadeIn 0.4s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Accordion Cards */
        .accordion {
            margin-bottom: 15px;
            border: 1px solid var(--border);
            border-radius: 8px;
            overflow: hidden;
        }

        .accordion-header {
            width: 100%;
            text-align: left;
            padding: 18px 20px;
            background: #f8fafc;
            border: none;
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--primary);
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: background 0.3s ease;
        }

        .accordion-header:hover {
            background: #edf2f7;
        }

        .accordion-icon {
            transition: transform 0.3s ease;
        }

        .accordion.active .accordion-icon {
            transform: rotate(180deg);
        }

        .accordion-body {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
            background: var(--card-bg);
        }

        .accordion-content {
            padding: 20px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            border-top: 1px solid var(--border);
        }

        @media (max-width: 768px) {
            .accordion-content {
                grid-template-columns: 1fr;
            }
        }

        .detail-section h4 {
            color: var(--secondary);
            margin-bottom: 10px;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .detail-section ul {
            list-style: none;
        }

        .detail-section li {
            margin-bottom: 8px;
            padding-left: 20px;
            position: relative;
        }

        .detail-section li::before {
            content: "•";
            color: var(--secondary);
            font-weight: bold;
            position: absolute;
            left: 0;
        }

        .alert-danger { color: var(--danger); font-weight: 600; }
        .alert-warning { color: #d35400; font-weight: 600; }

        /* Comparison Table */
        .table-section {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            margin-bottom: 30px;
            overflow-x: auto;
        }

        .table-section h2 {
            color: var(--primary);
            margin-bottom: 20px;
            font-size: 1.5rem;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            text-align: center;
        }

        th, td {
            padding: 15px;
            border-bottom: 1px solid var(--border);
        }

        th {
            background: #f8fafc;
            color: var(--primary);
            font-weight: 600;
        }

        tr:hover {
            background-color: #fcfcfc;
        }

        td:first-child {
            text-align: left;
            font-weight: 600;
            color: var(--primary);
        }

        .badge {
            display: inline-block;
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 0.85rem;
            font-weight: bold;
        }

        .badge-red { background: #fadbd8; color: #c0392b; }
        .badge-orange { background: #fdebd0; color: #d35400; }
        .badge-green { background: #d5f5e3; color: #27ae60; }
        .badge-gray { background: #e5e8e8; color: #7f8c8d; }

        /* Quiz Section */
        .quiz-section {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border-top: 5px solid var(--warning);
        }

        .quiz-section h2 {
            color: var(--primary);
            margin-bottom: 20px;
        }

        .question {
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid var(--border);
        }

        .question h4 {
            font-size: 1.1rem;
            margin-bottom: 15px;
            color: var(--primary);
        }

        .options label {
            display: block;
            margin-bottom: 10px;
            padding: 10px 15px;
            background: #f8fafc;
            border-radius: 6px;
            cursor: pointer;
            border: 1px solid var(--border);
            transition: all 0.2s;
        }

        .options label:hover {
            background: #edf2f7;
            border-color: var(--secondary);
        }

        .options input {
            margin-right: 10px;
        }

        .btn-quiz {
            background: var(--secondary);
            color: white;
            border: none;
            padding: 12px 25px;
            font-size: 1.1rem;
            border-radius: 6px;
            cursor: pointer;
            transition: background 0.3s;
            font-weight: 600;
            display: block;
            margin: 20px 0 0 auto;
        }

        .btn-quiz:hover {
            background: #2980b9;
        }

        #quiz-result {
            margin-top: 20px;
            padding: 15px;
            border-radius: 8px;
            font-weight: bold;
            text-align: center;
            display: none;
        }

        .result-success { background: #d5f5e3; color: #27ae60; }
        .result-warning { background: #fadbd8; color: #c0392b; }

    </style>
</head>
<body>

    <header>
        <h1><i class="fas fa-brain"></i> Antipsicóticos Atípicos</h1>
        <p>Guía interactiva de estudio: Mecanismos, perfiles farmacológicos y efectos adversos de los antipsicóticos de segunda generación.</p>
    </header>

    <div class="container">
        
        <section class="mechanism-box">
            <h2><i class="fas fa-project-diagram"></i> La Base de la Atipicidad</h2>
            <p>Los antipsicóticos atípicos (AA) se diferencian de los típicos por su <strong>doble mecanismo de acción</strong> y su ventana terapéutica que permite eficacia sin los severos efectos motores extrapiramidales (SEP).</p>
            
            <div class="mech-grid">
                <div class="mech-card">
                    <h4><i class="fas fa-ban" style="color:var(--danger)"></i> Bloqueo D2 Selectivo</h4>
                    <p>Baja afinidad y rápida disociación de los receptores D2 en el estriado. Evita cruzar el umbral del 80% que genera SEP y aumento de prolactina, manteniendo eficacia mesolímbica.</p>
                </div>
                <div class="mech-card">
                    <h4><i class="fas fa-cut" style="color:var(--secondary)"></i> Antagonismo 5-HT2A</h4>
                    <p>En el cuerpo estriado, "corta el cable de freno". Al bloquear 5-HT2A, se estimula la liberación de dopamina en el estriado, contrarrestando el bloqueo D2 y evitando el parkinsonismo y la hiperprolactinemia.</p>
                </div>
                <div class="mech-card">
                    <h4><i class="fas fa-adjust" style="color:var(--accent)"></i> Agonismo Parcial (D2/5-HT1A)</h4>
                    <p>Algunas moléculas (Pips/Rips) actúan como antagonistas en hiperdopaminergia y como agonistas en hipodopaminergia, estabilizando el sistema.</p>
                </div>
            </div>
        </section>

        <div class="tabs-header">
            <button class="tab-btn active" onclick="openTab(event, 'pinas')">Las "Pinas"</button>
            <button class="tab-btn" onclick="openTab(event, 'donas')">Las "Donas"</button>
            <button class="tab-btn" onclick="openTab(event, 'pips')">Los "Pips / Rips"</button>
        </div>

        <div id="pinas" class="tab-content active">
            
            <div class="accordion">
                <button class="accordion-header">
                    <span>Clozapina (El Prototipo)</span>
                    <i class="fas fa-chevron-down accordion-icon"></i>
                </button>
                <div class="accordion-body">
                    <div class="accordion-content">
                        <div class="detail-section">
                            <h4><i class="fas fa-microscope"></i> Mecanismo y Cualidades</h4>
                            <ul>
                                <li>Primer AA descubierto, estándar de oro en atipicidad.</li>
                                <li>Doble bloqueo 5HT2A > D2 con perfil farmacodinámico muy complejo.</li>
                                <li><strong>Único que disminuye el riesgo suicida</strong> en esquizofrenia.</li>
                                <li>Mejora a nivel funcional de forma significativa.</li>
                            </ul>
                        </div>
                        <div class="detail-section">
                            <h4><i class="fas fa-exclamation-triangle"></i> Usos y Efectos Adversos</h4>
                            <ul>
                                <li><strong>Uso:</strong> Esquizofrenia Resistente al Tratamiento (ERT).</li>
                                <li class="alert-danger">Riesgo de Agranulocitosis (1-3%): Potencialmente mortal. Requiere hemogramas estrictos semanales/mensuales.</li>
                                <li class="alert-warning">Riesgo Metabólico ALTO: Gran aumento de peso, glucemia y lípidos.</li>
                                <li>Disminuye umbral convulsivo (dosis dependiente).</li>
                                <li>Alta sedación.</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

            <div class="accordion">
                <button class="accordion-header">
                    <span>Olanzapina</span>
                    <i class="fas fa-chevron-down accordion-icon"></i>
                </button>
                <div class="accordion-body">
                    <div class="accordion-content">
                        <div class="detail-section">
                            <h4><i class="fas fa-microscope"></i> Mecanismo y Cualidades</h4>
                            <ul>
                                <li>Antagonista 5HT2A > D2. También bloquea D3, D4, 5HT2C, 5HT6, Alfa 1, H1 y M1-M5.</li>
                                <li>Alta disociación del receptor y selectividad límbica.</li>
                                <li>Es una molécula muy versátil con amplio espectro terapéutico.</li>
                                <li>Eficaz para ERT (después de clozapina).</li>
                            </ul>
                        </div>
                        <div class="detail-section">
                            <h4><i class="fas fa-exclamation-triangle"></i> Usos y Efectos Adversos</h4>
                            <ul>
                                <li><strong>Uso:</strong> Esquizofrenia, Trastorno Bipolar, agitación aguda (IM).</li>
                                <li class="alert-warning">Riesgo Metabólico ALTO ("Bomba metabólica"): Aumento de peso, hiperglucemia, dislipemia.</li>
                                <li>Efectos atropínicos/anticolinérgicos (midriasis, boca seca, constipación).</li>
                                <li>Aumento de transaminasas. Alta sedación.</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

            <div class="accordion">
                <button class="accordion-header">
                    <span>Quetiapina</span>
                    <i class="fas fa-chevron-down accordion-icon"></i>
                </button>
                <div class="accordion-body">
                    <div class="accordion-content">
                        <div class="detail-section">
                            <h4><i class="fas fa-microscope"></i> Mecanismo y Cualidades</h4>
                            <ul>
                                <li>"Molécula dúctil": Perfil varía según la dosis.</li>
                                <li>Bloqueo 5HT2A > D2 (débil antagonista). Agonista parcial 5HT1A.</li>
                                <li>Su metabolito activo (Norquetiapina) bloquea la recaptación de noradrenalina, dándole <strong>efecto antidepresivo</strong>.</li>
                                <li>Baja afinidad muscarínica: Útil en enf. de Parkinson.</li>
                            </ul>
                        </div>
                        <div class="detail-section">
                            <h4><i class="fas fa-exclamation-triangle"></i> Usos y Efectos Adversos</h4>
                            <ul>
                                <li><strong>Dosis bajas (50mg):</strong> Hipnótico/Sedante (bloqueo H1/M1).</li>
                                <li><strong>Dosis medias (300mg):</strong> Antidepresivo (T. Bipolar y TDM).</li>
                                <li><strong>Dosis altas (800mg):</strong> Antipsicótico (Esquizofrenia, Manía).</li>
                                <li>Riesgo metabólico moderado. Alta sedación. Hipotensión ortostática.</li>
                                <li>Muy baja frecuencia de SEP.</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

            <div class="accordion">
                <button class="accordion-header">
                    <span>Asenapina</span>
                    <i class="fas fa-chevron-down accordion-icon"></i>
                </button>
                <div class="accordion-body">
                    <div class="accordion-content">
                        <div class="detail-section">
                            <h4><i class="fas fa-microscope"></i> Mecanismo y Cualidades</h4>
                            <ul>
                                <li>Bloquea D2, 5HT2A, 5HT7. Agonista parcial 5HT1A.</li>
                                <li>Único con afinidad por H2. Bloquea Alfa 1/2. Sin afinidad M.</li>
                                <li>Estructura química relacionada con el antidepresivo Mirtazapina.</li>
                                <li><strong>Administración sublingual exclusiva</strong> (poca absorción GI).</li>
                            </ul>
                        </div>
                        <div class="detail-section">
                            <h4><i class="fas fa-exclamation-triangle"></i> Usos y Efectos Adversos</h4>
                            <ul>
                                <li><strong>Uso:</strong> Esquizofrenia aguda y Manía.</li>
                                <li><span class="alert-warning">Importante:</span> No comer ni beber 10 min tras administración sublingual.</li>
                                <li>Sedación inicial. Posible insomnio. Hipotensión ortostática.</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

        </div>

        <div id="donas" class="tab-content">
            
            <div class="accordion">
                <button class="accordion-header">
                    <span>Risperidona</span>
                    <i class="fas fa-chevron-down accordion-icon"></i>
                </button>
                <div class="accordion-body">
                    <div class="accordion-content">
                        <div class="detail-section">
                            <h4><i class="fas fa-microscope"></i> Mecanismo y Cualidades</h4>
                            <ul>
                                <li>Alta afinidad 5HT2A y D2. Bloqueo Alfa y H1.</li>
                                <li>No presenta rápida disociación D2 (Contraindicado en Parkinson).</li>
                                <li><# Clases-interactivas-
