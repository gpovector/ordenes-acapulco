<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toroide Gestión - Panel de Control del Taller</title>
    <link rel="stylesheet" href="styles.css">
    <!-- html2pdf.js CDN for PDF generation -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
</head>
<body>
    <!-- Sidebar Menu -->
    <aside class="sidebar">
        <div class="sidebar-brand">
            <img src="assets/logo_toroide_herramientas.jpg" alt="Toroide Logo" id="sidebar-logo">
            <h2>Toroide<span>Herramientas</span></h2>
        </div>
        <ul class="sidebar-menu">
            <li class="sidebar-menu-item active" data-view="view-dashboard">
                <a href="#">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="7" height="9"/><rect x="14" y="3" width="7" height="5"/><rect x="14" y="12" width="7" height="9"/><rect x="3" y="16" width="7" height="5"/></svg>
                    Dashboard
                </a>
            </li>
            <li class="sidebar-menu-item" data-view="view-orders">
                <a href="#">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/><polyline points="10 9 9 9 8 9"/></svg>
                    Nueva Orden
                </a>
            </li>
            <li class="sidebar-menu-item" data-view="view-history">
                <a href="#">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
                    Historial de Clientes
                </a>
            </li>
            <li class="sidebar-menu-item" data-view="view-inventory">
                <a href="#">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"/><polyline points="3.27 6.96 12 12.01 20.73 6.96"/><line x1="12" y1="22.08" x2="12" y2="12"/></svg>
                    Inventario
                </a>
            </li>
            <li class="sidebar-menu-item" data-view="view-settings">
                <a href="#">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-4 0v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1 0-4h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 4 0v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1z"/></svg>
                    Configuración
                </a>
            </li>
        </ul>
        <div class="sidebar-footer">
            Toroide Control Panel v1.1
        </div>
    </aside>
    <!-- Main Content Container -->
    <main class="main-content">
        
        <!-- ================= VIEW 1: DASHBOARD ================= -->
        <section id="view-dashboard" class="app-view active-view">
            <div class="header-panel">
                <div class="header-title">
                    <h1>Grupo Toroide Herramientas</h1>
                    <p>Dashboard de Operaciones y Estatus de Servicios</p>
                </div>
                <div class="header-actions">
                    <button class="btn btn-primary" onclick="document.querySelector('[data-view=view-orders]').click()">
                        + Crear Orden
                    </button>
                </div>
            </div>
            <!-- Stats grid -->
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-info">
                        <h3>Servicios Totales</h3>
                        <p id="stat-total-orders">0</p>
                    </div>
                    <div class="stat-icon orange">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
                    </div>
                </div>
                <div class="stat-card">
                    <div class="stat-info">
                        <h3>En Diagnóstico</h3>
                        <p id="stat-active-reviews">0</p>
                    </div>
                    <div class="stat-icon cyan">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><line x1="12" y1="16" x2="12" y2="12"/><line x1="12" y1="8" x2="12.01" y2="8"/></svg>
                    </div>
                </div>
                <div class="stat-card">
                    <div class="stat-info">
                        <h3>Listos para Entrega</h3>
                        <p id="stat-ready-orders">0</p>
                    </div>
                    <div class="stat-icon green">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/><polyline points="22 4 12 14.01 9 11.01"/></svg>
                    </div>
                </div>
                <div class="stat-card">
                    <div class="stat-info">
                        <h3>Bajo Stock Refacción</h3>
                        <p id="stat-low-stock">0</p>
                    </div>
                    <div class="stat-icon red">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m21.73 18-8-14a2 2 0 0 0-3.48 0l-8 14A2 2 0 0 0 4 21h16a2 2 0 0 0 1.73-3Z"/></svg>
                    </div>
                </div>
            </div>
            <!-- Content Split: Recent services + status lookups -->
            <div class="dashboard-grid">
                <div class="panel-card">
                    <div class="panel-header">
                        <h2>Órdenes Recientes en Taller</h2>
                        <a href="#" onclick="document.querySelector('[data-view=view-history]').click(); return false;" style="color: var(--accent-orange); font-size: 0.9rem; text-decoration: none; font-weight: 500;">Ver Historial</a>
                    </div>
                    <div class="table-container">
                        <table class="table-responsive">
                            <thead>
                                <tr>
                                    <th>Folio</th>
                                    <th>Cliente</th>
                                    <th>Herramienta</th>
                                    <th>Estatus</th>
                                    <th>Saldo Pendiente</th>
                                    <th>Acciones</th>
                                </tr>
                            </thead>
                            <tbody id="recent-orders-table-body">
                                <!-- Loaded dynamically via app.js -->
                            </tbody>
                        </table>
                    </div>
                </div>
                <div class="panel-card" style="display: flex; flex-direction: column; gap: 15px;">
                    <div class="panel-header">
                        <h2>Acceso Rápido</h2>
                    </div>
                    <p style="color: var(--text-secondary); font-size: 0.85rem; line-height: 1.4;">Búsqueda instantánea de equipos por número de teléfono:</p>
                    
                    <button class="btn btn-cyan" onclick="document.querySelector('[data-view=view-history]').click(); document.getElementById('history-search').focus();" style="width: 100%;">
                        Buscar Historial de Cliente
                    </button>
                    
                    <button class="btn btn-secondary" onclick="document.querySelector('[data-view=view-inventory]').click();" style="width: 100%;">
                        Ver Stock de Refacciones
                    </button>
                    <div style="margin-top: 15px; border-top: 1px solid var(--border-color); padding-top: 15px;">
                        <h4 style="font-size: 0.9rem; font-weight: 600; margin-bottom: 8px;">Datos de Contacto Taller:</h4>
                        <ul style="list-style: none; font-size: 0.8rem; color: var(--text-secondary); display: flex; flex-direction: column; gap: 6px;">
                            <li>📍 Av. Cuauhtémoc No. 239, Local 4</li>
                            <li>📞 Tels: 7444861885 / 7774855087</li>
                            <li>💬 WhatsApp: 5518905798</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>
        <!-- ================= VIEW 2: NUEVA ORDEN ================= -->
        <section id="view-orders" class="app-view">
            <div class="header-panel">
                <div class="header-title">
                    <h1 id="order-form-title">Crear Orden de Servicio</h1>
                    <p id="order-form-desc">Registro de herramientas y asignación técnica</p>
                </div>
            </div>
            <div class="panel-card">
                <form id="new-order-form">
                    <!-- Hidden field to check if editing -->
                    <input type="hidden" id="editing-order-id" value="">
                    <div class="form-grid">
                        
                        <!-- Client Info -->
                        <h3 class="form-grid-full" style="font-size: 1rem; border-bottom: 1px solid var(--border-color); padding-bottom: 6px; margin-top: 10px; color: var(--accent-orange); display: flex; justify-content: space-between; align-items: center;">
                            <span>Datos del Cliente</span>
                            <span id="edit-client-warning" style="display:none; font-size: 0.75rem; font-weight:normal; color: var(--accent-cyan);">* Modo edición activo (guardará cambios sobre el cliente).</span>
                        </h3>
                        
                        <div class="form-group">
                            <label for="customer-phone">Teléfono Celular (WhatsApp) *</label>
                            <div class="input-with-button">
                                <input type="tel" id="customer-phone" placeholder="Ej. 7441234567" class="form-control" required>
                                <button type="button" class="btn btn-secondary" id="btn-autofill-client">Autocompletar</button>
                            </div>
                        </div>
                        <div class="form-group">
                            <label for="customer-name">Nombre Completo del Cliente *</label>
                            <input type="text" id="customer-name" placeholder="Ej. Juan Pérez" class="form-control" required>
                        </div>
                        <div class="form-group form-grid-full">
                            <label for="customer-email">Correo Electrónico (Opcional)</label>
                            <input type="email" id="customer-email" placeholder="cliente@correo.com" class="form-control">
                        </div>
                        <!-- Tool Info -->
                        <h3 class="form-grid-full" style="font-size: 1rem; border-bottom: 1px solid var(--border-color); padding-bottom: 6px; margin-top: 10px; color: var(--accent-orange); display: flex; justify-content: space-between; align-items: center;">
                            <span>Datos de la Herramienta</span>
                            <button type="button" class="btn btn-cyan btn-sm" id="btn-scan-ia" style="padding: 4px 12px; font-size: 0.78rem;">⚡ Escanear Placa con IA</button>
                        </h3>
                        
                        <div class="form-group form-grid-full">
                            <label for="tool-name">Nombre / Tipo de Herramienta *</label>
                            <input type="text" id="tool-name" placeholder="Ej. Amoladora Angular, Rotomartillo, Taladro" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="tool-brand">Marca de la Herramienta *</label>
                            <input type="text" id="tool-brand" placeholder="Ej. DeWalt, Bosch, Makita" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="tool-model">Modelo de la Herramienta *</label>
                            <input type="text" id="tool-model" placeholder="Ej. DWE575" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="tool-serial">Número de Serie (Opcional)</label>
                            <input type="text" id="tool-serial" placeholder="Ej. SN-987654" class="form-control">
                        </div>
                        <div class="form-group">
                            <label for="order-status">Estatus del Servicio *</label>
                            <select id="order-status" class="form-control">
                                <option value="review" selected>En revisión</option>
                                <option value="waiting_auth">En espera de autorización</option>
                                <option value="authorized">Autorizado</option>
                                <option value="parts">Esperando refacción</option>
                                <option value="ready">Listo para entrega</option>
                                <option value="waiting_payment">En espera de pago</option>
                                <option value="delivered">Entregado</option>
                                <option value="warranty">Garantía</option>
                            </select>
                        </div>
                        <div class="form-group form-grid-full">
                            <label for="tool-fault">Falla Reportada por el Cliente *</label>
                            <textarea id="tool-fault" placeholder="Detalle la falla reportada (ej. Se detiene a medio trabajo, chispazos en carbones)" class="form-control" required></textarea>
                        </div>
                        <div class="form-group form-grid-full">
                            <label for="tool-repair">Diagnóstico / Reparación Ejecutada (Técnico)</label>
                            <textarea id="tool-repair" placeholder="Detalle técnico de los componentes intervenidos o pruebas (opcional en el registro inicial)" class="form-control"></textarea>
                        </div>
                        <!-- 6 Photos evidence upload gallery -->
                        <div class="form-group form-grid-full">
                            <label>Evidencia Fotográfica / Estado de Recepción de Herramienta (Máximo 6 fotos)</label>
                            <div class="input-with-button">
                                <input type="file" id="tool-images-input" accept="image/*" multiple style="display:none;">
                                <button type="button" class="btn btn-secondary" id="btn-select-images" style="width: 100%;">📸 Seleccionar / Tomar Fotos de Herramienta</button>
                            </div>
                            <small style="color: var(--text-muted); display:block; margin-top:5px;">Se han seleccionado <strong id="images-count">0</strong> de 6 fotos.</small>
                            <div id="tool-images-gallery" class="parts-selected-list" style="margin-top: 10px; display: flex; gap: 10px; flex-wrap: wrap;">
                                <!-- Thumbnails loaded dynamically -->
                            </div>
                        </div>
                        <!-- Inventory selector -->
                        <h3 class="form-grid-full" style="font-size: 1rem; border-bottom: 1px solid var(--border-color); padding-bottom: 6px; margin-top: 10px; color: var(--accent-orange);">Control de Refacciones</h3>
                        
                        <div class="form-group form-grid-full">
                            <label>Vincular Refacciones del Inventario (Verifica disponibilidad)</label>
                            <div class="input-with-button">
                                <select id="order-parts-select" class="form-control">
                                    <!-- Loaded via app.js -->
                                </select>
                                <button type="button" class="btn btn-secondary" id="btn-add-part">+ Agregar</button>
                            </div>
                            <!-- Stock Out Notification -->
                            <div id="inventory-warning" class="inventory-warning-box" style="display: none; margin-top: 10px;">
                                <!-- Warnings rendered dynamically -->
                            </div>
                            <div id="selected-parts-container" class="parts-selected-list">
                                <!-- Tags rendered dynamically -->
                            </div>
                        </div>
                        <!-- Dates and Financials -->
                        <h3 class="form-grid-full" style="font-size: 1rem; border-bottom: 1px solid var(--border-color); padding-bottom: 6px; margin-top: 10px; color: var(--accent-orange);">Costos y Fechas de Entrega</h3>
                        
                        <div class="form-group">
                            <label for="date-entry">Fecha de Ingreso *</label>
                            <input type="date" id="date-entry" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="date-commitment">Fecha Compromiso de Entrega *</label>
                            <input type="date" id="date-commitment" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="order-budget">Presupuesto Total ($) *</label>
                            <input type="number" id="order-budget" value="0.00" step="0.01" min="0" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="order-advance">Anticipo Recibido ($)</label>
                            <input type="number" id="order-advance" value="0.00" step="0.01" min="0" class="form-control">
                        </div>
                        <div class="form-group form-grid-full">
                            <label for="order-pending">Saldo Pendiente a Liquidar ($)</label>
                            <input type="text" id="order-pending" value="0.00" class="form-control" readonly style="background-color: var(--bg-primary); border-color: var(--border-color); color: var(--accent-orange); font-weight: 700;">
                        </div>
                    </div>
                    <div style="margin-top: 30px; display: flex; justify-content: flex-end; gap: 15px;">
                        <button type="button" class="btn btn-secondary" id="btn-cancel-edit" style="display:none;">Cancelar Edición</button>
                        <button type="button" class="btn btn-secondary" id="btn-clear-form" onclick="resetNewOrderForm()">Limpiar Formulario</button>
                        <button type="submit" class="btn btn-primary" id="btn-submit-order">Registrar Orden y Generar Mensaje</button>
                    </div>
                </form>
            </div>
        </section>
        <!-- ================= VIEW 3: HISTORIAL DE CLIENTES ================= -->
        <section id="view-history" class="app-view">
            <div class="header-panel">
                <div class="header-title">
                    <h1>Historial de Servicios por Cliente</h1>
                    <p>Filtra por número de teléfono celular, nombre o folio de orden</p>
                </div>
            </div>
            <div class="panel-card" style="margin-bottom: 24px;">
                <div class="form-group">
                    <label for="history-search">Buscar por Celular / Nombre del Cliente / Folio de Orden</label>
                    <div style="position: relative;">
                        <input type="text" id="history-search" placeholder="Escriba el celular de 10 dígitos (ej. 7441234567) o el nombre..." class="form-control" style="padding-left: 45px;">
                        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="position: absolute; left: 16px; top: 12px; color: var(--text-muted);"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
                    </div>
                </div>
            </div>
            <div id="history-results-list" class="history-results">
                <!-- Cards will render here dynamically via app.js -->
            </div>
        </section>
        <!-- ================= VIEW 4: INVENTARIO ================= -->
        <section id="view-inventory" class="app-view">
            <div class="header-panel">
                <div class="header-title">
                    <h1>Módulo de Inventario de Refacciones</h1>
                    <p>Administración y reabastecimiento de piezas compatibles</p>
                </div>
                <div class="header-actions">
                    <button class="btn btn-primary" onclick="addNewPartForm()">
                        + Registrar Refacción
                    </button>
                </div>
            </div>
            <div class="panel-card">
                <div class="table-container">
                    <table class="table-responsive">
                        <thead>
                            <tr>
                                <th>SKU (Código)</th>
                                <th>Refacción</th>
                                <th>Compatibilidad / Modelos</th>
                                <th>Stock Físico</th>
                                <th>Precio Público ($)</th>
                                <th>Acciones</th>
                            </tr>
                        </thead>
                        <tbody id="inventory-table-body">
                            <!-- Loaded via app.js -->
                        </tbody>
                    </table>
                </div>
            </div>
        </section>
        <!-- ================= VIEW 5: CONFIGURACIÓN ================= -->
        <section id="view-settings" class="app-view">
            <div class="header-panel">
                <div class="header-title">
                    <h1>Configuración del Sistema</h1>
                    <p>Ajuste de datos de contacto del negocio y plantillas de WhatsApp</p>
                </div>
            </div>
            <div class="panel-card" style="display: flex; flex-direction: column; gap: 24px;">
                
                <div>
                    <h3 style="font-size: 1.1rem; font-weight: 600; margin-bottom: 12px; color: var(--accent-orange); border-bottom: 1px solid var(--border-color); padding-bottom: 6px;">Visualización y Logotipos</h3>
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
                        <div class="form-group">
                            <label for="settings-logo-select">Logotipo para Orden de Trabajo (PDF)</label>
                            <select id="settings-logo-select" class="form-control">
                                <option value="logo_toroide_herramientas.jpg">Grupo Toroide Herramientas (Estándar Red/Blue)</option>
                                <option value="logo_toroide_hilti.jpg">Grupo Toroide | Hilti Authorized (Crossover)</option>
                                <option value="logo_toroide_crescent.jpg">Grupo Toroide Circular Crest (Círculo)</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="settings-gemini-key">Clave API Google Gemini (IA Real OCR)</label>
                            <input type="password" id="settings-gemini-key" placeholder="AIzaSy..." class="form-control">
                            <small style="color: var(--text-muted);">Llave opcional para analizar imágenes reales de placas de herramientas.</small>
                        </div>
                        <div class="form-group">
                            <label for="settings-script-url">URL de API de Carga (Apps Script / Servidor Propio)</label>
                            <input type="url" id="settings-script-url" placeholder="https://script.google.com/macros/s/.../exec" class="form-control">
                            <small style="color: var(--text-muted);">Configure la URL para subir PDFs y fotos de evidencia automáticamente (ej. Apps Script, Node, PHP).</small>
                        </div>
                        <div class="form-group">
                            <label for="settings-public-prefix">Prefijo de URL Pública de Servidor (Netlify / Firebase / Apache)</label>
                            <input type="url" id="settings-public-prefix" placeholder="https://toroide-taller.netlify.app/ordenes/" class="form-control">
                            <small style="color: var(--text-muted);">Prefijo para generar enlaces directos de descarga (ej. si almacena archivos en Netlify/Firebase).</small>
                        </div>
                    </div>
                </div>
                <div>
                    <h3 style="font-size: 1.1rem; font-weight: 600; margin-bottom: 12px; color: var(--accent-orange); border-bottom: 1px solid var(--border-color); padding-bottom: 6px;">Automatización de WhatsApp (Mensajes del Estatus)</h3>
                    <p style="font-size: 0.8rem; color: var(--text-secondary); margin-bottom: 15px; line-height: 1.4;">
                        Puede personalizar las plantillas de mensaje. Use las siguientes etiquetas que se sustituirán automáticamente al generar el envío:<br>
                        <code>[Nombre Cliente]</code>, <code>[Herramienta]</code>, <code>[Modelo]</code>, <code>[No_Serie]</code>, <code>[ID_Orden]</code>, <code>[Fecha_Compromiso]</code>, <code>[Presupuesto]</code>, <code>[Anticipo]</code>, <code>[Saldo_Pendiente]</code>, <code>[Enlace_PDF]</code>
                    </p>
                    
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px;">
                        <div class="form-group">
                            <label>1. En revisión (review)</label>
                            <textarea id="template-review" class="form-control" style="min-height: 70px;"></textarea>
                        </div>
                        <div class="form-group">
                            <label>2. En espera de autorización (waiting_auth)</label>
                            <textarea id="template-waiting_auth" class="form-control" style="min-height: 70px;"></textarea>
                        </div>
                        <div class="form-group">
                            <label>3. Autorizado (authorized)</label>
                            <textarea id="template-authorized" class="form-control" style="min-height: 70px;"></textarea>
                        </div>
                        <div class="form-group">
                            <label>4. Esperando refacción (parts)</label>
                            <textarea id="template-parts" class="form-control" style="min-height: 70px;"></textarea>
                        </div>
                        <div class="form-group">
                            <label>5. Listo para entrega (ready)</label>
                            <textarea id="template-ready" class="form-control" style="min-height: 70px;"></textarea>
                        </div>
                        <div class="form-group">
                            <label>6. En espera de pago (waiting_payment)</label>
                            <textarea id="template-waiting_payment" class="form-control" style="min-height: 70px;"></textarea>
                        </div>
                        <div class="form-group">
                            <label>7. Entregado (delivered)</label>
                            <textarea id="template-delivered" class="form-control" style="min-height: 70px;"></textarea>
                        </div>
                        <div class="form-group">
                            <label>8. Garantía (warranty)</label>
                            <textarea id="template-warranty" class="form-control" style="min-height: 70px;"></textarea>
                        </div>
                    </div>
                </div>
                <div style="border-top: 1px solid var(--border-color); padding-top: 20px; display: flex; justify-content: space-between; align-items: center;">
                    <div>
                        <button class="btn btn-secondary" onclick="exportDatabaseJson()">Respaldar Base de Datos (JSON)</button>
                        <button class="btn btn-secondary" onclick="triggerDbReset()" style="color: var(--accent-red); border-color: rgba(239, 68, 68, 0.2);">Restablecer Valores de Fábrica</button>
                    </div>
                    <button id="btn-save-settings" class="btn btn-primary">Guardar Cambios</button>
                </div>
            </div>
        </section>
    </main>
    <!-- ================= SCANNERS IA MODAL (CAMERA FEED / OCR ANALYZER) ================= -->
    <div id="scanner-modal" class="whatsapp-modal" style="display: none;">
        <div class="whatsapp-modal-content" style="max-width: 650px;">
            <h3>Escáner Visual de Herramientas IA</h3>
            <p>Tome una foto de la placa de características de la herramienta o suba un archivo para extraer Marca, Modelo y Número de Serie por IA.</p>
            
            <div style="display: grid; grid-template-columns: 320px 1fr; gap: 20px; margin: 15px 0; text-align: left;">
                
                <!-- Camera and Canvas Block -->
                <div style="display: flex; flex-direction: column; gap: 10px;">
                    <div id="camera-container" style="width: 320px; height: 240px; background-color: #0b0f19; border: 2px solid var(--border-color); border-radius: 8px; position: relative; overflow: hidden; display: flex; align-items: center; justify-content: center;">
                        <video id="scanner-video" width="320" height="240" autoplay playsinline style="object-fit: cover; width: 100%; height: 100%;"></video>
                        <canvas id="scanner-canvas" width="320" height="240" style="display: none; position: absolute; left:0; top:0; width:100%; height:100%; object-fit: cover;"></canvas>
                        
                        <!-- Laser Animation Overlay -->
                        <div id="scanner-laser" class="laser-scanner" style="display:none;"></div>
                        
                        <div id="camera-fallback-msg" style="position: absolute; text-align: center; color: var(--text-muted); font-size: 0.8rem; padding: 20px;">
                            Cámara desactivada.<br>Use "Subir Foto" o las "Placas de Demostración".
                        </div>
                    </div>
                    
                    <div style="display: flex; gap: 8px; justify-content: center;">
                        <button type="button" class="btn btn-secondary btn-sm" id="btn-start-camera" style="font-size:0.75rem;">Iniciar Cámara</button>
                        <button type="button" class="btn btn-primary btn-sm" id="btn-capture-photo" style="display:none; font-size:0.75rem;">Capturar Foto</button>
                    </div>
                </div>
                <!-- Simulation and Upload Console Block -->
                <div style="display: flex; flex-direction: column; gap: 12px; justify-content: space-between;">
                    <div class="form-group">
                        <label>Subir Foto de Placa</label>
                        <input type="file" id="scanner-file-input" accept="image/*" class="form-control" style="padding: 6px 12px; font-size: 0.8rem;">
                    </div>
                    <!-- IA demo options -->
                    <div>
                        <label style="font-size: 0.78rem; font-weight:600; color: var(--text-secondary); display:block; margin-bottom: 6px;">Demostración rápida de IA (Placas Muestra):</label>
                        <div style="display: flex; gap: 6px; flex-wrap: wrap;">
                            <button type="button" class="btn btn-secondary btn-sm" onclick="triggerMockScan('dewalt')" style="font-size:0.7rem; padding: 4px 8px;">Muestra DeWalt</button>
                            <button type="button" class="btn btn-secondary btn-sm" onclick="triggerMockScan('bosch')" style="font-size:0.7rem; padding: 4px 8px;">Muestra Bosch</button>
                            <button type="button" class="btn btn-secondary btn-sm" onclick="triggerMockScan('makita')" style="font-size:0.7rem; padding: 4px 8px;">Muestra Makita</button>
                        </div>
                    </div>
                    <!-- OCR Output Text Console -->
                    <div style="background-color: var(--bg-tertiary); border: 1px solid var(--border-color); border-radius: 6px; padding: 10px; font-family: monospace; font-size: 0.72rem; min-height: 80px; max-height: 80px; overflow-y: auto; color: #34d399;" id="scanner-console">
                        [Scanner] Listo para recibir placa...
                    </div>
                </div>
            </div>
            <div class="whatsapp-modal-buttons" style="margin-top: 15px;">
                <button type="button" class="btn btn-secondary" id="btn-close-scanner">Cerrar Escáner</button>
                <button type="button" class="btn btn-cyan" id="btn-analyze-plate" style="display:none;">Procesar Placa con IA</button>
            </div>
        </div>
    </div>
    <!-- ================= WHATSAPP AUTOMATION MODAL ================= -->
    <div id="whatsapp-modal" class="whatsapp-modal" style="display: none;">
        <div class="whatsapp-modal-content">
            <div class="whatsapp-icon-circle">
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="currentColor" viewBox="0 0 16 16"><path d="M13.601 2.326A7.85 7.85 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.057 3.965L0 16l4.204-1.102a7.9 7.9 0 0 0 3.79.907h.004c4.368 0 7.926-3.558 7.93-7.93A7.9 7.9 0 0 0 13.6 2.326zM7.994 14.521a6.6 6.6 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.56 6.56 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592m3.69-4.98c-.202-.1-.1.195-.3.29-.59.29-1.03.485-1.74.19-.2-.08-.417-.186-.765-.366-1.34-.6-2.22-1.96-2.29-2.05-.073-.1-.6-1.1-.6-1.8 0-.69.36-1.02.49-1.15.13-.13.3-.2.39-.2.09 0 .18 0 .26.01.079.005.18.02.26.2.1.24.33.82.36.89.03.07.05.15.01.24-.04.09-.08.2-.15.3-.07.1-.15.22-.23.3-.09.09-.18.19-.08.36.1.17.47.78 1.01 1.26.69.62 1.27.82 1.45.92.18.1.29.08.4-.04.11-.13.49-.57.62-.77.13-.2.26-.17.4-.1.14.07.9.42 1.06.5.16.08.26.12.3.2.04.07.04.42-.1.77z"/></svg>
            </div>
            <h3>Enviar Notificación de WhatsApp</h3>
            <p>Estatus de orden actualizado. Se generará un enlace para abrir WhatsApp Web / App y enviar el mensaje:</p>
            <div id="whatsapp-preview" class="whatsapp-preview-box">
                <!-- Text loaded from template preview -->
            </div>
            <div class="whatsapp-modal-buttons">
                <button type="button" class="btn btn-secondary" id="btn-modal-close">Cancelar</button>
                <button type="button" class="btn btn-success" id="btn-modal-send">Abrir WhatsApp y Enviar</button>
            </div>
        </div>
    </div>
    <!-- ================= PRINT TICKETS CONTAINER (HIDDEN ON SCREEN, DISPLAYED IN PRINT) ================= -->
    <section id="printable-ticket-section">
        <div class="print-ticket-container">
            
            <div class="print-header">
                <div class="print-logo-container">
                    <img id="print-logo" src="assets/logo_toroide_herramientas.jpg" alt="Logo Impresión">
                </div>
                <div class="print-business-info">
                    <strong>Grupo Toroide Herramientas</strong><br>
                    Av. Cuauhtémoc No. 239, Local 4, Fracc. Marroquí<br>
                    Acapulco, Guerrero, CP 39640<br>
                    Tels: 7444861885 / 7774855087<br>
                    WhatsApp: 5518905798
                </div>
            </div>
            <div class="print-title-folio">
                <h3>ORDEN DE SERVICIO Y DIAGNÓSTICO</h3>
                <div>
                    <span>FOLIO:</span>
                    <span class="folio" id="print-folio">TH-XXXX</span>
                </div>
            </div>
            <div class="print-grid">
                
                <div class="print-section">
                    <h4>Datos del Cliente</h4>
                    <div class="print-data-row">
                        <span class="label">Nombre:</span>
                        <span class="val" id="print-client-name">---</span>
                    </div>
                    <div class="print-data-row">
                        <span class="label">Celular:</span>
                        <span class="val" id="print-client-phone">---</span>
                    </div>
                    <div class="print-data-row">
                        <span class="label">Email:</span>
                        <span class="val" id="print-client-email">---</span>
                    </div>
                </div>
                <div class="print-section">
                    <h4>Datos del Servicio</h4>
                    <div class="print-data-row">
                        <span class="label">Fecha Ingreso:</span>
                        <span class="val" id="print-date-entry">---</span>
                    </div>
                    <div class="print-data-row">
                        <span class="label">Fecha Compromiso:</span>
                        <span class="val" id="print-date-commitment">---</span>
                    </div>
                    <div class="print-data-row">
                        <span class="label">Garantía:</span>
                        <span class="val">30 Días Naturales</span>
                    </div>
                </div>
                <div class="print-section" style="grid-column: span 2;">
                    <h4>Especificaciones del Equipo</h4>
                    <div style="display: flex; gap: 40px; font-size: 0.85rem; margin-bottom: 8px;">
                        <div><strong>Equipo:</strong> <span id="print-tool-name">---</span></div>
                        <div><strong>Marca:</strong> <span id="print-tool-brand">---</span></div>
                        <div><strong>Modelo:</strong> <span id="print-tool-model">---</span></div>
                        <div><strong>No. Serie:</strong> <span id="print-tool-serial">---</span></div>
                    </div>
                </div>
            </div>
            <div class="print-fault-box">
                <h4>Falla Reportada por el Cliente</h4>
                <div class="print-fault-text" id="print-fault-reported">---</div>
            </div>
            <div class="print-fault-box">
                <h4>Diagnóstico y Reparaciones Realizadas</h4>
                <div class="print-fault-text" id="print-repair-details">---</div>
            </div>
            <div style="display: flex; justify-content: space-between; align-items: flex-start; margin-top: 15px;">
                <div style="font-size: 0.72rem; max-width: 450px; color: #444;">
                    * Este documento es un comprobante de recepción para diagnóstico y/o reparación.
                </div>
                <div class="print-financial-summary">
                    <table class="print-financial-table">
                        <tr>
                            <td class="label">Presupuesto:</td>
                            <td id="print-budget">$0.00</td>
                        </tr>
                        <tr>
                            <td class="label">Anticipo Recibido:</td>
                            <td id="print-advance">$0.00</td>
                        </tr>
                        <tr class="total-row">
                            <td class="label">Saldo Pendiente:</td>
                            <td id="print-balance">$0.00</td>
                        </tr>
                    </table>
                </div>
            </div>
            <!-- Cláusula de Garantía (Protección Legal) -->
            <div class="print-warranty-box">
                <h5>Términos y Cláusulas de Garantía de Reparación</h5>
                <ol>
                    <li>Toda reparación realizada en este taller cuenta con una garantía única de <strong>30 días naturales</strong> contados a partir de la fecha de entrega del equipo.</li>
                    <li>La garantía cubre <strong>exclusivamente la mano de obra y refacciones utilizadas</strong> que guarden relación directa con la falla originalmente intervenida descrita en esta orden. No cubre fallas distintas, sobrecargas eléctricas, mal uso por fuerza extrema o manipulación técnica ajena al personal de este establecimiento.</li>
                    <li>Para hacer válida la garantía o cualquier reclamación, es estrictamente obligatorio presentar esta orden de servicio en original.</li>
                    <li><strong>Cláusula de Abandono:</strong> Todo equipo no reclamado después de 90 días naturales contados a partir de la fecha compromiso de entrega causará abandono de manera irrevocable, autorizando a <strong>Grupo Toroide Herramientas</strong> a disponer del equipo para recuperar costos de diagnóstico, mano de obra y almacén.</li>
                </ol>
            </div>
            <div class="print-signatures">
                <div>
                    <div class="signature-line">Firma del Cliente</div>
                    <div class="signature-sub">Acepto los términos de esta orden</div>
                </div>
                <div>
                    <div class="signature-line">Grupo Toroide Herramientas</div>
                    <div class="signature-sub">Firma de Recepción / Técnico</div>
                </div>
            </div>
        </div>
    </section>
    <!-- Beautiful Glassmorphism Loading Overlay -->
    <div id="loading-overlay" class="loading-overlay" style="display: none;">
        <div class="loader-content">
            <div class="spinner"></div>
            <p id="loading-message">Sincronizando con Google Drive...</p>
        </div>
    </div>
    <!-- Script loading -->
    <script src="app.js"></script>
</body>
</html>
