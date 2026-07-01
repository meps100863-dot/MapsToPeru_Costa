<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Perú 2026 - La Costa y Más</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --fb-blue: #1877f2;
            --fb-dark: #1c1e21;
            --fb-gray: #f0f2f5;
            --fb-text: #050505;
        }

        body {
            background-color: var(--fb-gray);
        }

        /* Header estilo Facebook 2026 */
        .header {
            background: white;
            height: 56px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 20px;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        .logo-section {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo {
            width: 40px;
            height: 40px;
            background: var(--fb-blue);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 24px;
            font-weight: bold;
        }

        .search-box {
            background: var(--fb-gray);
            border-radius: 20px;
            padding: 8px 15px;
            width: 240px;
            border: none;
            outline: none;
        }

        .nav-icons {
            display: flex;
            gap: 30px;
            font-size: 24px;
        }

        .nav-icons span {
            cursor: pointer;
            padding: 10px;
            border-radius: 10px;
            transition: 0.3s;
        }

        .nav-icons span:hover {
            background: var(--fb-gray);
        }

        .profile-section {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .profile-pic {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(45deg, #d4af37, #c41e3a);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 20px;
        }

        /* Layout principal */
        .container {
            display: flex;
            max-width: 1200px;
            margin: 76px auto 0;
            gap: 20px;
            padding: 0 20px;
        }

        .sidebar-left, .sidebar-right {
            width: 250px;
            position: sticky;
            top: 76px;
            height: fit-content;
        }

        .feed {
            flex: 1;
            max-width: 680px;
        }

        /* Tarjetas */
        .card {
            background: white;
            border-radius: 8px;
            box-shadow: 0 1px 2px rgba(0,0,0,0.1);
            margin-bottom: 15px;
            padding: 15px;
        }

        .post-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
        }

        .post-header img, .post-header .page-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
        }

        .page-avatar {
            background: linear-gradient(135deg, #d4af37 0%, #c41e3a 50%, #e6be8a 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 20px;
        }

        .post-info h4 {
            color: var(--fb-blue);
            cursor: pointer;
        }

        .post-info p {
            font-size: 12px;
            color: #65676b;
        }

        .post-content {
            margin: 10px 0;
            line-height: 1.5;
            color: var(--fb-text);
        }

        .post-content h2 {
            color: #c41e3a;
            margin-bottom: 10px;
            font-size: 20px;
        }

        .post-content h3 {
            color: #d4af37;
            margin: 15px 0 8px 0;
            font-size: 16px;
        }

        .post-content ul {
            margin-left: 20px;
            margin-bottom: 10px;
        }

        .post-content li {
            margin-bottom: 5px;
        }

        .post-image {
            width: 100%;
            border-radius: 8px;
            margin-top: 10px;
        }

        .post-actions {
            display: flex;
            justify-content: space-around;
            padding-top: 10px;
            border-top: 1px solid #e4e6eb;
            margin-top: 10px;
            color: #65676b;
            font-weight: 600;
        }

        .post-actions span {
            cursor: pointer;
            padding: 5px 20px;
            border-radius: 5px;
            transition: 0.3s;
        }

        .post-actions span:hover {
            background: var(--fb-gray);
        }

        /* Mapa Container */
        .map-container {
            background: white;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 15px;
            box-shadow: 0 1px 2px rgba(0,0,0,0.1);
        }

        .map-container h2 {
            color: #c41e3a;
            margin-bottom: 15px;
            text-align: center;
        }

        .map-svg {
            width: 100%;
            height: auto;
            filter: drop-shadow(0 4px 6px rgba(0,0,0,0.1));
        }

        .region {
            cursor: pointer;
            transition: 0.3s;
        }

        .region:hover {
            opacity: 0.8;
            transform: scale(1.01);
        }

        .costa { fill: #e6be8a; }
        .sierra { fill: #8fbc8f; }
        .selva { fill: #228b22; }

        .legend {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 15px;
            flex-wrap: wrap;
        }

        .legend-item {
            display: flex;
            align-items: center;
            gap: 5px;
            font-size: 14px;
        }

        .legend-color {
            width: 20px;
            height: 20px;
            border-radius: 3px;
        }

        /* Sidebar items */
        .menu-item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
            transition: 0.3s;
        }

        .menu-item:hover {
            background: #e4e6eb;
        }

        .menu-icon {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
        }

        .trending {
            background: white;
            border-radius: 8px;
            padding: 15px;
            box-shadow: 0 1px 2px rgba(0,0,0,0.1);
        }

        .trending h4 {
            color: #65676b;
            margin-bottom: 10px;
        }

        .trend-item {
            display: flex;
            justify-content: space-between;
            padding: 8px 0;
            border-bottom: 1px solid #e4e6eb;
        }

        .trend-item:last-child {
            border-bottom: none;
        }

        /* Responsive */
        @media (max-width: 900px) {
            .sidebar-left, .sidebar-right {
                display: none;
            }
            .container {
                justify-content: center;
            }
        }

        /* Animaciones */
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .live-badge {
            background: #e41e3f;
            color: white;
            padding: 2px 8px;
            border-radius: 4px;
            font-size: 12px;
            animation: pulse 2s infinite;
        }
    </style>
</head>
<body>

    <!-- Header -->
    <div class="header">
        <div class="logo-section">
            <div class="logo">P</div>
            <input type="text" class="search-box" placeholder="Buscar en Perú 2026...">
        </div>
        <div class="nav-icons">
            <span>🏠</span>
            <span>📺</span>
            <span>🏪</span>
            <span>👥</span>
            <span>🎮</span>
        </div>
        <div class="profile-section">
            <span>🔔</span>
            <span>💬</span>
            <div class="profile-pic">🇵🇪</div>
        </div>
    </div>

    <div class="container">
        <!-- Sidebar Izquierda -->
        <div class="sidebar-left">
            <div class="card">
                <div class="menu-item">
                    <div class="menu-icon" style="background: linear-gradient(45deg, #d4af37, #c41e3a);">🇵🇪</div>
                    <span><strong>Perú Oficial 2026</strong></span>
                </div>
                <div class="menu-item">
                    <div class="menu-icon" style="background: #e4e6eb;">🌊</div>
                    <span>Costa Peruana</span>
                </div>
                <div class="menu-item">
                    <div class="menu-icon" style="background: #e4e6eb;">⛰️</div>
                    <span>Región Andina</span>
                </div>
                <div class="menu-item">
                    <div class="menu-icon" style="background: #e4e6eb;">🌴</div>
                    <span>Amazonía</span>
                </div>
                <div class="menu-item">
                    <div class="menu-icon" style="background: #e4e6eb;">🏛️</div>
                    <span>Cultura Inca</span>
                </div>
                <div class="menu-item">
                    <div class="menu-icon" style="background: #e4e6eb;">🍽️</div>
                    <span>Gastronomía</span>
                </div>
            </div>
        </div>

        <!-- Feed Principal -->
        <div class="feed">
            
            <!-- Post Informativo -->
            <div class="card">
                <div class="post-header">
                    <div class="page-avatar">🇵🇪</div>
                    <div class="post-info">
                        <h4>Perú - Descubre el País de los Incas</h4>
                        <p>2026 · 🌎 Información actualizada <span class="live-badge">EN VIVO</span></p>
                    </div>
                </div>
                <div class="post-content">
                    <h2>🌊 La Costa Peruana - 2026</h2>
                    <p>La región costera del Perú se extiende a lo largo de <strong>2,414 kilómetros</strong> bordeando el Océano Pacífico. Es una franja desértica interrumpida por valles fértiles formados por ríos que descienden de los Andes.</p>
                    
                    <h3>📍 Departamentos de la Costa:</h3>
                    <ul>
                        <li><strong>Tumbes</strong> - Playas tropicales, manglares, frontera con Ecuador</li>
                        <li><strong>Piura</strong> - Piura, Chiclayo al norte, surf en Máncora</li>
                        <li><strong>Lambayeque</strong> - Cultura Chimú, Tumbas Reales de Sipán</li>
                        <li><strong>La Libertad</strong> - Chan Chan, Huanchaco, capital del ceviche</li>
                        <li><strong>Ancash</strong> - Cordillera Blanca, Huaraz, playas de Huarmey</li>
                        <li><strong>Lima</strong> - Capital gastronómica, 10+ millones de habitantes</li>
                        <li><strong>Ica</strong> - Líneas de Nazca, oasis de Huacachina, vinos y pisco</li>
                        <li><strong>Arequipa</strong> - Ciudad blanca, Colca, puerto de Matarani</li>
                        <li><strong>Moquegua</strong> - Valle fertilísimo, producción de pisco</li>
                        <li><strong>Tacna</strong> - El balcón de Chile, zona franca</li>
                    </ul>

                    <h3>🌡️ Clima 2026:</h3>
                    <p>La costa peruana tiene un clima <strong>desértico subtropical</strong> con alta humedad atmosférica pero casi sin lluvias (excepto en Tumbes y Piura con precipitaciones esporádicas). La Corriente de Humboldt mantiene temperaturas moderadas todo el año (15°C - 28°C).</p>

                    <h3>🐟 Recursos Económicos:</h3>
                    <ul>
                        <li>La corriente de Humboldt hace del Perú una potencia pesquera</li>
                        <li>Principal productor mundial de harina y aceite de pescado</li>
                        <li>Exportación de arándanos, espárragos, palta, mango</li>
                        <li>Industria petroquímica en Talara y Pisco</li>
                        <li>Turismo costero: Paracas, Máncora, Punta Sal, Asia</li>
                    </ul>

                    <h3>🏖️ Playas Destacadas 2026:</h3>
                    <p>🏝️ <strong>Máncora</strong> - Surf eterno, vida nocturna<br>
                    🏝️ <strong>Punta Sal</strong> - Agua tibia todo el año<br>
                    🏝️ <strong>Paracas</strong> - Biodiversidad, Islas Ballestas<br>
                    🏝️ <strong>Huanchaco</strong> - Caballitos de totora, tradición milenaria<br>
                    🏝️ <strong>Asia</strong> - Playa exclusiva cerca de Lima</p>
                </div>
                <div class="post-actions">
                    <span>👍 Me gusta</span>
                    <span>💬 Comentar</span>
                    <span>↗️ Compartir</span>
                </div>
            </div>

            <!-- Mapa del Perú -->
            <div class="map-container">
                <h2>🗺️ Mapa Interactivo del Perú 2026</h2>
                <svg class="map-svg" viewBox="0 0 400 600" xmlns="http://www.w3.org/2000/svg">
                    <!-- Silueta simplificada del Perú -->
                    <path class="region costa" d="M 50 50 
                        Q 30 100 40 150
                        Q 35 200 45 250
                        Q 40 300 50 350
                        Q 45 400 55 450
                        Q 50 500 60 550
                        L 120 540
                        Q 130 500 125 450
                        Q 135 400 130 350
                        Q 140 300 135 250
                        Q 145 200 140 150
                        Q 150 100 140 50
                        Z" 
                        onclick="showInfo('costa')"
                        title="Costa - Haz clic"/>
                    
                    <path class="region sierra" d="M 140 50
                        Q 150 100 160 150
                        Q 155 200 165 250
                        Q 160 300 170 350
                        Q 165 400 175 450
                        Q 170 500 180 540
                        L 120 540
                        Q 130 500 125 450
                        Q 135 400 130 350
                        Q 140 300 135 250
                        Q 145 200 140 150
                        Z"
                        onclick="showInfo('sierra')"
                        title="Sierra - Haz clic"/>
                    
                    <path class="region selva" d="M 160 150
                        Q 170 100 200 80
                        Q 250 60 300 70
                        Q 350 90 380 120
                        Q 390 200 370 280
                        Q 380 360 360 440
                        Q 340 500 300 540
                        L 180 540
                        Q 170 500 175 450
                        Q 165 400 170 350
                        Q 160 300 165 250
                        Z"
                        onclick="showInfo('selva')"
                        title="Selva - Haz clic"/>
                    
                    <!-- Ciudades principales -->
                    <circle cx="70" cy="200" r="4" fill="red" title="Lima"/>
                    <text x="75" y="205" font-size="10" fill="#333">Lima</text>
                    
                    <circle cx="160" cy="180" r="4" fill="red" title="Cusco"/>
                    <text x="165" y="185" font-size="10" fill="#333">Cusco</text>
                    
                    <circle cx="300" cy="300" r="4" fill="red" title="Iquitos"/>
                    <text x="305" y="305" font-size="10" fill="#333">Iquitos</text>
                    
                    <circle cx="100" cy="100" r="4" fill="red" title="Piura"/>
                    <text x="105" y="105" font-size="10" fill="#333">Piura</text>
                    
                    <circle cx="140" cy="350" r="4" fill="red" title="Arequipa"/>
                    <text x="145" y="355" font-size="10" fill="#333">Arequipa</text>
                </svg>
                
                <div class="legend">
                    <div class="legend-item">
                        <div class="legend-color" style="background: #e6be8a;"></div>
                        <span>Costa (Desértica)</span>
                    </div>
                    <div class="legend-item">
                        <div class="legend-color" style="background: #8fbc8f;"></div>
                        <span>Sierra (Andes)</span>
                    </div>
                    <div class="legend-item">
                        <div class="legend-color" style="background: #228b22;"></div>
                        <span>Selva (Amazonía)</span>
                    </div>
                </div>
                
                <div id="region-info" style="margin-top: 15px; padding: 10px; background: #f0f2f5; border-radius: 8px; display: none;">
                    <p id="region-text"></p>
                </div>
            </div>

            <!-- Post de datos curiosos -->
            <div class="card">
                <div class="post-header">
                    <div class="page-avatar">📊</div>
                    <div class="post-info">
                        <h4>Datos del Perú 2026</h4>
                        <p>Hace 2 horas · 📈 Actualidad</p>
                    </div>
                </div>
                <div class="post-content">
                    <h3>📈 Perú en Números (2026):</h3>
                    <ul>
                        <li><strong>Población:</strong> ~34 millones de habitantes</li>
                        <li><strong>Capital:</strong> Lima (mayor ciudad de Sudamérica después de São Paulo)</li>
                        <li><strong>Idiomas:</strong> Español, Quechua, Aymara y 47 lenguas amazónicas</li>
                        <li><strong>Moneda:</strong> Sol (PEN)</li>
                        <li><strong>PIB 2026:</strong> ~$280 mil millones USD</li>
                        <li><strong>Exportaciones:</strong> Cobre, oro, zinc, plata, café, paltas, arándanos</li>
                        <li><strong>Patrimonios UNESCO:</strong> 12 (Machu Picchu, Líneas de Nazca, Cusco, etc.)</li>
                        <li><strong>Mar peruano:</strong> Zona económica exclusiva de 906,000 km²</li>
                    </ul>
                    
                    <h3>🍽️ Gastronomía Costeña:</h3>
                    <p>La costa es cuna de la gastronomía peruana:<br>
                    🥘 <strong>Ceviche</strong> - Plato bandera, pescado marinado en limón<br>
                    🍤 <strong>Lomo Saltado</strong> - Fusión chino-peruana (chifa)<br>
                    🥑 <strong>Causa Limeña</strong> - Puré de papa amarilla relleno<br>
                    🍹 <strong>Pisco Sour</strong> - Destilado de uva, bebida nacional<br>
                    🦐 <strong>Chupe de camarones</strong> - Sopa arequipeña</p>
                </div>
                <div class="post-actions">
                    <span>👍 15K</span>
                    <span>💬 342</span>
                    <span>↗️ 89</span>
                </div>
            </div>

        </div>

        <!-- Sidebar Derecha -->
        <div class="sidebar-right">
            <div class="trending">
                <h4>🔥 Tendencias en Perú 2026</h4>
                <div class="trend-item">
                    <div>
                        <small>Turismo · Tendencia</small><br>
                        <strong>Machu Picchu</strong>
                    </div>
                    <span>🔥</span>
                </div>
                <div class="trend-item">
                    <div>
                        <small>Deportes · Tendencia</small><br>
                        <strong>Selección Peruana</strong>
                    </div>
                    <span>⚽</span>
                </div>
                <div class="trend-item">
                    <div>
                        <small>Cultura · Tendencia</small><br>
                        <strong>Inti Raymi 2026</strong>
                    </div>
                    <span>☀️</span>
                </div>
                <div class="trend-item">
                    <div>
                        <small>Economía · Tendencia</small><br>
                        <strong>Mega Puerto de Corío</strong>
                    </div>
                    <span>🚢</span>
                </div>
                <div class="trend-item">
                    <div>
                        <small>Naturaleza · Tendencia</small><br>
                        <strong>El Niño Costero</strong>
                    </div>
                    <span>🌊</span>
                </div>
            </div>
        </div>
    </div>

    <script>
        function showInfo(region) {
            const infoDiv = document.getElementById('region-info');
            const textDiv = document.getElementById('region-text');
            
            const info = {
                'costa': {
                    title: '🌊 Región Costa',
                    content: 'Ocup el 11% del territorio (140,000 km²). Clima desértico subtropical. Principales ciudades: Lima, Trujillo, Chiclayo, Arequipa, Piura. Economía basada en pesca, agricultura de exportación y manufactura.'
                },
                'sierra': {
                    title: '⛰️ Región Sierra',
                    content: 'Ocup el 30% del territorio. Incluye la Cordillera de los Andes. Altitudes entre 1,000 y 6,768 msnm (Huascarán). Principales ciudades: Cusco, Arequipa, Huancayo, Cajamarca. Economía: minería, agricultura andina, turismo.'
                },
                'selva': {
                    title: '🌴 Región Selva',
                    content: 'Ocup el 59% del territorio (más de 700,000 km²). Amazonía peruana, la segunda selva tropical más grande del mundo. Principales ciudades: Iquitos, Pucallpa, Puerto Maldonado. Economía: petróleo, gas natural, madera, turismo ecológico, biodiversidad.'
                }
            };
            
            textDiv.innerHTML = `<strong>${info[region].title}</strong><br><br>${info[region].content}`;
            infoDiv.style.display = 'block';
        }

        // Efecto de "Me gusta"
        document.querySelectorAll('.post-actions span').forEach(btn => {
            btn.addEventListener('click', function() {
                if(this.textContent.includes('Me gusta')) {
                    this.style.color = '#1877f2';
                    this.innerHTML = '👍 ¡Te gusta!';
                }
            });
        });
    </script>

</body>
</html>
