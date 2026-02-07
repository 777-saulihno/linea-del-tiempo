<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Línea del Tiempo: Teorías de la Arquitectura</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Merriweather:wght@300;400;700;900&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-color: #f4eadd; /* Beige claro estilo papiro */
            --text-color: #2b1d14; /* Marrón café muy oscuro */
            --accent-color: #8b5a2b; /* Bronce/Marrón */
            --card-bg: #fffbf0; /* Blanco hueso */
            --border-color: #d4b483;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Merriweather', serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.8;
            background-image: url('image_0.png'); /* Asegúrate de que la imagen esté en el repo */
            background-repeat: repeat;
            background-attachment: fixed;
        }

        h1, h2, h3, h4 {
            font-family: 'Cinzel', serif;
            color: #4a332a;
        }

        /* --- PORTADA --- */
        #cover {
            text-align: center;
            padding: 6rem 1rem;
            background-color: rgba(244, 234, 221, 0.95);
            border-bottom: 8px double var(--accent-color);
            margin-bottom: 4rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        #cover h1 {
            font-size: 3.5rem;
            margin-bottom: 2rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 2px 2px 0px rgba(0,0,0,0.1);
        }

        .author-list {
            list-style: none;
            padding: 0;
            font-size: 1.2rem;
            font-weight: 700;
            color: #3d2b1f;
        }

        .author-list li {
            margin-bottom: 0.8rem;
        }

        .info-materia {
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 2px solid var(--accent-color);
            display: inline-block;
            width: 80%;
        }

        /* --- CONTENEDOR DE LÍNEA DEL TIEMPO --- */
        .timeline-section {
            position: relative;
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 0;
        }

        /* Línea central */
        .timeline-section::after {
            content: '';
            position: absolute;
            width: 6px;
            background-color: var(--accent-color);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -3px;
            border-radius: 3px;
        }

        /* Contenedor de tarjeta */
        .container {
            padding: 10px 50px;
            position: relative;
            background-color: transparent;
            width: 50%;
        }

        .left { left: 0; }
        .right { left: 50%; }

        /* Puntos en la línea */
        .container::after {
            content: '';
            position: absolute;
            width: 24px;
            height: 24px;
            right: -12px;
            background-color: var(--card-bg);
            border: 5px solid var(--accent-color);
            top: 35px;
            border-radius: 50%;
            z-index: 10;
        }

        .right::after { left: -12px; }

        /* Tarjeta de contenido */
        .content {
            padding: 30px;
            background-color: var(--card-bg);
            position: relative;
            border-radius: 4px;
            border: 1px solid var(--border-color);
            border-left: 8px solid var(--accent-color);
            box-shadow: 5px 5px 15px rgba(0,0,0,0.1);
        }

        .content h3 {
            font-size: 1.6rem;
            margin-bottom: 0.5rem;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 10px;
        }

        .date-badge {
            display: inline-block;
            background-color: var(--accent-color);
            color: #fff;
            padding: 5px 15px;
            border-radius: 4px;
            font-family: 'Cinzel', serif;
            font-weight: bold;
            font-size: 0.9rem;
            margin-bottom: 15px;
        }

        .content p, .content li {
            font-size: 1rem;
            margin-bottom: 10px;
            text-align: justify;
        }

        .content ul {
            padding-left: 20px;
            margin-top: 10px;
        }

        /* SEPARADOR DE AUTOR */
        .author-separator {
            grid-column: 1 / -1;
            text-align: center;
            margin: 6rem 0 3rem 0;
            z-index: 20;
            position: relative;
            clear: both;
        }

        .author-title {
            background-color: #4a332a;
            color: #fff;
            padding: 20px 60px;
            font-family: 'Cinzel', serif;
            font-size: 2rem;
            border: 4px solid var(--accent-color);
            display: inline-block;
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
            position: relative;
        }

        /* --- SECCIÓN DE ANÁLISIS --- */
        .analysis-section {
            max-width: 1000px;
            margin: 5rem auto;
            background-color: rgba(255, 251, 240, 0.95);
            padding: 4rem;
            border: 2px solid var(--accent-color);
            box-shadow: 0 0 30px rgba(0,0,0,0.1);
        }

        .analysis-section h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            border-bottom: 2px solid var(--accent-color);
            padding-bottom: 1rem;
        }

        .qa-block {
            margin-bottom: 3rem;
        }

        .qa-block h3 {
            color: var(--accent-color);
            margin-bottom: 1.5rem;
        }

        /* --- BIBLIOGRAFÍA --- */
        .biblio-section {
            max-width: 1000px;
            margin: 0 auto 5rem auto;
            padding: 2rem;
            background-color: #fff;
            border-left: 10px solid #4a332a;
        }

        .biblio-item {
            padding: 10px 0;
            padding-left: 20px;
            text-indent: -20px;
            border-bottom: 1px dashed #ccc;
        }

        /* FOOTER */
        footer {
            background-color: #2b1d14;
            color: #d4b483;
            text-align: center;
            padding: 3rem;
            margin-top: 4rem;
        }

        /* RESPONSIVE */
        @media screen and (max-width: 900px) {
            .timeline-section::after { left: 31px; }
            .container { width: 100%; padding-left: 70px; padding-right: 25px; }
            .container::after { left: 18px; }
            .left::after, .right::after { left: 18px; }
            .right { left: 0%; }
            .cover-image { display: none; } /* Ocultar decoración en móvil */
            #cover h1 { font-size: 2rem; }
        }
    </style>
</head>
<body>

    <section id="cover">
        <h1>Línea del Tiempo<br><span style="font-size: 0.6em; color: var(--accent-color);">Teoría Arquitectónica</span></h1>
        
        <ul class="author-list">
            <li>Cruz Hernández Marian Cristel 2137688</li>
            <li>Cazares Ruiz Keira Samantha 2111035</li>
            <li>Vázquez Hernández Danna Mitzary 2150199</li>
            <li>Rubio Alemán Héctor Saúl 2161962</li>
        </ul>

        <div class="info-materia">
            <p><strong>Materia:</strong> Teorías de la arquitectura</p>
            <p><strong>Grupo:</strong> 006</p>
            <p><strong>Docente:</strong> Rivera Guzman Luz Isela</p>
        </div>
    </section>

    <div class="timeline-section">

        <div class="author-separator">
            <div class="author-title">MARCO VITRUVIO POLIÓN</div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">c. 80–70 a.C.</span>
                <h3>Nacimiento</h3>
                <p>Nace Marco Vitruvio Polión en el contexto de la Roma republicana, una época de expansión militar y desarrollo técnico que influiría en su formación como ingeniero y teórico de la arquitectura.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">58–51 a.C.</span>
                <h3>Arquitecto e Ingeniero Militar</h3>
                <p>Trabaja como arquitecto e ingeniero militar de Julio César.</p>
                <ul>
                    <li>Participa en la construcción de máquinas de guerra, fortificaciones, campamentos y obras hidráulicas.</li>
                    <li>Aquí adquiere el conocimiento técnico que luego sistematiza en su teoría arquitectónica.</li>
                </ul>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">30–20 a.C.</span>
                <h3>Período de Augusto</h3>
                <p>Se retira del servicio militar y de arquitecto civil. Sirve bajo el emperador Augusto, en un momento de estabilidad política y gran impulso constructivo en Roma.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">30–20 a.C.</span>
                <h3>Escritura de "De Architectura"</h3>
                <p>Escribe <em>Los Diez Libros de Arquitectura</em>. Algunas de sus aportaciones teóricas principales fueron:</p>
                <ul>
                    <li>El primer tratado arquitectónico completo de la historia.</li>
                    <li>Integra arquitectura, ingeniería, urbanismo, materiales, máquinas y estética.</li>
                    <li>Recupera saberes griegos (como Hermógenes de Alabanda, s. II a.C.) y los adapta al mundo romano.</li>
                </ul>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">Siglos III–IV d.C.</span>
                <h3>Reconocimiento Póstumo</h3>
                <p>Empieza a ser citado como la máxima autoridad de la arquitectura antigua.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">Siglo V d.C.</span>
                <h3>Mención por Sidonio Apolinar</h3>
                <p>Confirma la vigencia de su pensamiento en la Antigüedad tardía.</p>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">Siglo IX</span>
                <h3>Salvaguarda de la Obra</h3>
                <p>Copia manuscrita en un monasterio de Suiza. Gracias a esta copia su obra no se pierde.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">Siglo XV | Renacimiento</span>
                <h3>Redescubrimiento en Florencia</h3>
                <ul>
                    <li>Su tratado llega a intelectuales y arquitectos renacentistas. Influye directamente en: Brunelleschi y Leon Battista Alberti.</li>
                    <li>Se consolida la arquitectura basada en proporción, simetría y razón.</li>
                </ul>
            </div>
        </div>


        <div class="author-separator">
            <div class="author-title">LEON BATTISTA ALBERTI</div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">14 de febrero de 1404</span>
                <h3>Nacimiento</h3>
                <p>Nace en Génova, Italia.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1428 – 1432</span>
                <h3>Formación y Traslado</h3>
                <ul>
                    <li><strong>1428:</strong> Se gradúa en Derecho Canónico en la Universidad de Bolonia.</li>
                    <li><strong>1432:</strong> Se establece en Florencia, donde entra en contacto con el humanismo y la arquitectura renacentista.</li>
                </ul>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">1435 – 1436</span>
                <h3>Teoría de la Perspectiva</h3>
                <p>Publica <em>De pictura</em> (1435 en latín, 1436 en italiano).</p>
                <ul>
                    <li>Establece las bases matemáticas de la perspectiva lineal.</li>
                    <li>Introduce el concepto del cuadro como una “ventana abierta” al espacio.</li>
                    <li>Influye directamente en arquitectos y artistas del Renacimiento, al vincular geometría, visión y representación espacial.</li>
                </ul>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">ca. 1440–1450</span>
                <h3>Concepto: Arquitectura como Arte Intelectual</h3>
                <p>Alberti sostiene que la arquitectura no es solo construcción, sino una actividad intelectual basada en el diseño previo, la razón y el conocimiento teórico. El arquitecto concibe el edificio antes de ejecutarlo, separando así el pensamiento arquitectónico del trabajo manual.</p>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">1443</span>
                <h3>De Statua</h3>
                <p>Redacta <em>De statua</em>. Aplica principios matemáticos a la proporción del cuerpo humano y refuerza la idea de que el diseño arquitectónico debe basarse en medidas racionales y científicas.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1446 – 1451</span>
                <h3>Fachada del Palacio Rucellai (Florencia)</h3>
                <p><strong>Ideas representadas:</strong></p>
                <ul>
                    <li>Uso racional de los órdenes clásicos superpuestos.</li>
                    <li>Fachada organizada mediante proporciones matemáticas.</li>
                    <li>Aplicación del concepto de concinnitas (armonía entre partes).</li>
                </ul>
                <p>Este edificio expresa su visión de la arquitectura civil renacentista, donde la belleza surge del orden, la simetría y la medida, no del ornamento excesivo.</p>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">1450 – 1452</span>
                <h3>De Re Aedificatoria</h3>
                <p>Concluye su tratado más importante (1452). Es el primer tratado arquitectónico del Renacimiento moderno. Define la arquitectura como una ciencia basada en: Proporción, orden, armonía y belleza objetiva.</p>
                <p><strong>Conceptos clave introducidos:</strong></p>
                <ul>
                    <li><strong>Concinnitas (Armonía perfecta):</strong> Armonía matemática entre todas las partes del edificio; cada elemento debe guardar una relación proporcional exacta con el conjunto.</li>
                    <li><strong>Belleza Objetiva:</strong> Rechaza la belleza como percepción subjetiva. La belleza resulta de la concinnitas.</li>
                    <li><strong>Reinterpretación de Vitruvio:</strong> Retoma Firmitas, Utilitas y Venustas. Otorga a la venustas (belleza) un papel central, siempre subordinado a la razón.</li>
                </ul>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1450 – 1460</span>
                <h3>Templo Malatestiano (Rímini)</h3>
                <ul>
                    <li>Reinterpretación del arco triunfal romano.</li>
                    <li>Integración del lenguaje clásico en un edificio religioso cristiano.</li>
                    <li>Fachada monumental con estructura racional.</li>
                </ul>
                <p>Demuestra cómo Alberti adapta el clasicismo a nuevas funciones, aplicando la belleza como resultado de la proporción y no de la tradición medieval.</p>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">1450 – 1470</span>
                <h3>Teoría Urbana y Monumentalidad</h3>
                <p>Plantea la arquitectura como un instrumento de orden urbano y político. Defiende fachadas armónicas, plazas regulares y edificios públicos monumentales. Influye en el desarrollo de la ciudad renacentista italiana.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1456 – 1470</span>
                <h3>Fachada de Santa María Novella (Florencia)</h3>
                <ul>
                    <li>Integración de una iglesia gótica previa mediante proporción clásica.</li>
                    <li>Uso de figuras geométricas (cuadrado y círculo).</li>
                    <li>Orden visual claro y simétrico.</li>
                </ul>
                <p>Refleja su idea de que la arquitectura debe unificar lo existente mediante reglas racionales, logrando armonía y belleza objetiva.</p>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">1460 – 1470</span>
                <h3>Iglesia de San Sebastiano (Mantua)</h3>
                <ul>
                    <li>Planta centralizada, inspirada en la Antigüedad clásica.</li>
                    <li>Simetría estricta y geometría pura.</li>
                    <li>Claridad formal sin ornamento excesivo.</li>
                </ul>
                <p>Ejemplo del ideal renacentista de perfección geométrica y equilibrio formal, donde la razón domina el diseño.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1470</span>
                <h3>Diseño Basílica de San Andrés (Mantua)</h3>
                <ul>
                    <li>Monumentalidad inspirada en la arquitectura romana.</li>
                    <li>Uso de una nave única con gran arco central.</li>
                    <li>Claridad espacial y unidad formal.</li>
                </ul>
                <p>Es la síntesis de su teoría: equilibrio entre firmitas, utilitas y venustas, con una fuerte carga simbólica y urbana.</p>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">25 de abril de 1472</span>
                <h3>Fallecimiento</h3>
                <p>Muere en Roma, Italia.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1485</span>
                <h3>Publicación Póstuma</h3>
                <p>Publicación de <em>De re aedificatoria</em> en Florencia.</p>
            </div>
        </div>


        <div class="author-separator">
            <div class="author-title">ANDREA PALLADIO</div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">1508</span>
                <h3>Nacimiento</h3>
                <p>Nacimiento de Andrea Palladio en Padua, República de Venecia.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1537 – 1538</span>
                <h3>Inicio de Carrera</h3>
                <ul>
                    <li>Comienza a trabajar bajo la tutela de Gian Giorgio Trissino, noble humanista.</li>
                    <li>Trissino lo introduce al estudio de la arquitectura clásica y tratados como los de Sebastiano Serlio.</li>
                    <li>Le da el nombre de “Palladio”, inspirado en Palas Atenea, diosa de la sabiduría.</li>
                </ul>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">Década de 1540</span>
                <h3>Primeras Villas</h3>
                <p>Diseña villas rurales para la aristocracia veneciana en el entorno de Vicenza. Aplica a edificios agrícolas principios antes reservados a templos y palacios.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1549</span>
                <h3>Basílica de Vicenza</h3>
                <ul>
                    <li>Primera gran obra civil.</li>
                    <li>Intervención sobre un edificio existente mediante una logia de dos niveles.</li>
                </ul>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">1550 – 1566</span>
                <h3>Consolidación Urbana</h3>
                <p>Consolidación urbana en Vicenza: Amplía su trabajo a palacios urbanos y grandes villas.</p>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1560 – 1577</span>
                <h3>Etapa Veneciana</h3>
                <p>Arquitectura religiosa en Venecia. Aplica el lenguaje clásico a templos cristianos.</p>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">1566 – 1570</span>
                <h3>Villa Rotonda</h3>
                <ul>
                    <li>Obra maestra del clasicismo renacentista.</li>
                    <li>Planta centralizada, simetría total y referencia directa al Panteón romano.</li>
                </ul>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1570</span>
                <h3>Publicación de "Los Cuatro Libros"</h3>
                <p>Publicación de <em>Los cuatro libros de la arquitectura</em> (Venecia).</p>
                <ul>
                    <li>Difunde reglas de proporción, órdenes y tipologías.</li>
                    <li>Une teoría y práctica mediante dibujos y ejemplos construidos.</li>
                </ul>
            </div>
        </div>

        <div class="container left">
            <div class="content">
                <span class="date-badge">1579</span>
                <h3>Teatro Olímpico (Vicenza)</h3>
                <ul>
                    <li>Inspirado en el teatro romano antiguo.</li>
                    <li>Basado en los principios de Vitruvio.</li>
                </ul>
            </div>
        </div>

        <div class="container right">
            <div class="content">
                <span class="date-badge">1580</span>
                <h3>Muerte y Legado</h3>
                <ul>
                    <li>Fallece en Vicenza dejando inconcluso el Teatro Olímpico.</li>
                    <li>Su legado se consolida como base del Palladianismo, influyendo en Europa y América durante siglos.</li>
                </ul>
            </div>
        </div>

    </div>

    <section class="analysis-section">
        <h2>ANÁLISIS COMPARATIVO Y CONCLUSIONES</h2>

        <div class="qa-block">
            <h3>1. Similitudes y diferencias entre sus conceptos arquitectónicos</h3>
            <h4>Similitudes</h4>
            <p>Los tres comparten una visión racional y clásica de la arquitectura, heredada del mundo grecorromano:</p>
            <ul>
                <li>La arquitectura se basa en principios universales, no en el gusto personal.</li>
                <li>Uso de la proporción, la simetría y la geometría como base del diseño.</li>
                <li>Consideran la arquitectura como una disciplina intelectual, no solo constructiva.</li>
                <li>Retoman y reinterpretan la tradición clásica: Vitruvio la formula, Alberti la reinterpreta desde el humanismo y Palladio la sistematiza y la lleva a la práctica.</li>
            </ul>
            <p>Además, los tres entienden que la arquitectura debe servir a la sociedad, ya sea desde lo técnico (Vitruvio), lo urbano y político (Alberti) o lo habitacional y territorial (Palladio).</p>
            
            <h4 style="margin-top: 1rem;">Diferencias</h4>
            <ul>
                <li><strong>Vitruvio</strong> establece las bases.</li>
                <li><strong>Alberti</strong> las teoriza y eleva intelectualmente.</li>
                <li><strong>Palladio</strong> las materializa y difunde.</li>
            </ul>
        </div>

        <div class="qa-block">
            <h3>2. ¿Qué principios siguen vigentes hoy en día y por qué?</h3>
            
            <p><strong>Firmitas, Utilitas y Venustas:</strong> Siguen siendo la base del pensamiento arquitectónico actual porque toda arquitectura debe ser estructuralmente estable (firmitas), debe responder a su función y al usuario (utilitas), y debe producir calidad espacial y estética (venustas). Aunque hoy se expresen con nuevos lenguajes, estos principios siguen guiando el diseño contemporáneo.</p>

            <p><strong>Proporción y geometría:</strong> Siguen vigentes porque ayudan a crear espacios legibles, equilibrados y comprensibles. Se aplican tanto en arquitectura clásica como moderna, minimalista o contemporánea. La geometría sigue siendo una herramienta racional de orden.</p>

            <p><strong>Arquitectura como disciplina intelectual:</strong> De Alberti a hoy, el arquitecto piensa, proyecta y diseña antes de construir. El proyecto arquitectónico se basa en análisis, contexto, concepto y razón. Esto es fundamental en la práctica profesional contemporánea.</p>

            <p><strong>Relación arquitectura–ciudad:</strong> Muy vigente porque la arquitectura actual sigue entendiendo al edificio como parte del entorno urbano, social y político. Conceptos como espacio público, monumentalidad, escala y orden urbano vienen directamente de Alberti y del clasicismo.</p>

            <p><strong>Teoría + práctica:</strong> Gracias a Palladio, hoy se sigue buscando que la arquitectura sea replicable, comprensible y enseñable. Sus ideas influyen incluso en la arquitectura moderna y en sistemas modulares.</p>
        </div>
    </section>

    <section class="biblio-section">
        <h2 style="text-align: center; font-family: 'Cinzel', serif; margin-bottom: 2rem;">Referencias Bibliográficas</h2>
        
        <div class="biblio-item">Alberti, L. B. (1988). <em>De re aedificatoria</em> (J. Rykwert, N. Leach & R. Tavernor, Trads.). MIT Press. (Obra original escrita ca. 1452 y publicada póstumamente en 1485).</div>
        
        <div class="biblio-item">Alberti, L. B. (1972). <em>On painting and on sculpture: The Latin texts of De pictura and De statua</em> (C. Grayson, Trad.). Phaidon Press. (Obras originales publicadas en 1435 y 1443).</div>
        
        <div class="biblio-item">Benevolo, L. (1994). <em>Historia de la arquitectura del Renacimiento</em>. Gustavo Gili.</div>
        
        <div class="biblio-item">Kruft, H.-W. (1994). <em>Historia de la teoría de la arquitectura (Vol. 1)</em>. Alianza Editorial.</div>
        
        <div class="biblio-item">Wittkower, R. (1998). <em>La arquitectura en la edad del humanismo</em>. Alianza Editorial.</div>
        
        <div class="biblio-item">https://www.urbipedia.org/hoja/Andrea_Palladio</div>
        
        <div class="biblio-item">https://www.descubrirelarte.es/2018/04/08/el-legado-de-palladio-inmortalizado-por-el-septimo-arte.html</div>
        
        <div class="biblio-item">Cartwright, M., & Cartwright, M. (2023). <em>Vitruvio</em>. Enciclopedia de la Historia del Mundo. https://www.worldhistory.org/trans/es/1-12057/vitruvio/</div>
        
        <div class="biblio-item">Redacción - BBC News Mundo. (2022, 30 julio). <em>Quién fue Vitruvio, el genial arquitecto militar que inspiró el famoso dibujo de Leonardo da Vinci</em>. Yahoo News. https://es-us.noticias.yahoo.com/vitruvio-genial-arquitecto-militar-inspir%C3%B3-095927862.html</div>
    </section>

    <footer>
        <p>FACULTAD DE ARQUITECTURA UANL &copy; 2026 | Equipo: Cruz, Cazares, Vázquez, Rubio</p>
    </footer>

</body>
</html>
