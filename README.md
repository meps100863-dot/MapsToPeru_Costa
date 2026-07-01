
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
