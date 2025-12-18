<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YCUN DESIGN | Portafolio Multimedia</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;900&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #141414;
            color: #f1eaf5;
        }
        .neo-brutalism {
            border-bottom: 12px solid #fac459;
            border-right: 12px solid #fac459;
            transition: all 0.3s ease;
        }
        .neo-brutalism:hover {
            border-color: #f18ccc;
            transform: translate(-4px, -4px);
        }
        .no-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .no-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
        @keyframes slideIn {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        .toast-animate {
            animation: slideIn 0.3s ease-out forwards;
        }
    </style>
</head>
<body class="selection:bg-[#fac459] selection:text-black">

    <!-- NOTIFICACIÓN DE COMPARTIR -->
    <div id="shareToast" class="fixed top-20 right-6 z-[100] bg-[#a6e3eb] text-[#141414] px-6 py-3 border-4 border-[#141414] font-black uppercase text-[10px] hidden items-center gap-3 toast-animate">
        <span>✅ Enlace de lectura copiado</span>
    </div>

    <!-- HEADER / NAV -->
    <header class="border-b border-[#f1eaf5]/10 py-4 px-6 flex flex-wrap gap-4 justify-between items-center sticky top-0 z-50 bg-[#141414]/90 backdrop-blur-md">
        <div class="flex gap-4 md:gap-6 items-center overflow-x-auto no-scrollbar">
            <div class="flex items-center gap-2 text-[10px] font-black uppercase text-[#a6e3eb] whitespace-nowrap">
                ycundesing0@gmail.com
            </div>
            <a href="https://instagram.com/Ycun_desing" target="_blank" class="flex items-center gap-2 text-[10px] font-black uppercase text-[#f18ccc] hover:underline whitespace-nowrap">
                @Ycun_desing
            </a>
            <a href="https://tiktok.com/@Ycundesing_" target="_blank" class="flex items-center gap-2 text-[10px] font-black uppercase text-white hover:underline whitespace-nowrap">
                @Ycundesing_
            </a>
        </div>
        
        <div class="flex items-center gap-3">
            <button id="btnShare" class="bg-[#f1eaf5] text-[#141414] px-4 py-2 text-[11px] font-black uppercase flex items-center gap-2 border-b-4 border-r-4 border-[#fac459] active:translate-y-1 transition-all">
                Compartir
            </button>
            <button id="toggleAdmin" class="bg-[#fac459] text-[#141414] px-5 py-2 text-[11px] font-black uppercase flex items-center gap-2 border-b-4 border-r-4 border-white active:translate-y-1 transition-all">
                Subir Proyecto
            </button>
        </div>
    </header>

    <!-- HERO -->
    <section class="pt-24 pb-20 px-6 border-b-8 border-[#f1eaf5]">
        <div class="max-w-7xl mx-auto">
            <div class="flex items-center gap-2 mb-6 text-[#f18ccc] font-black tracking-[0.4em] uppercase text-xs">
                ✨ PORTAFOLIO MULTIMEDIA
            </div>
            <h1 class="text-8xl md:text-[12rem] font-black uppercase tracking-tighter leading-[0.75] mb-10">
                YCUN<br><span class="text-[#fac459]">DESIGN</span>
            </h1>
            <div class="flex flex-col md:flex-row md:items-center gap-8">
                <p class="text-2xl font-black uppercase italic border-l-8 border-[#a6e3eb] pl-6 max-w-xl">
                    Diseñadora gráfica, Community Manager y Editora de video.
                </p>
            </div>
        </div>
    </section>

    <!-- FILTROS -->
    <nav class="sticky top-[65px] z-40 bg-[#141414] border-b-2 border-[#f1eaf5]/10">
        <div class="max-w-7xl mx-auto px-6 overflow-x-auto no-scrollbar">
            <div id="filterContainer" class="flex gap-4 py-6">
                <!-- Botones de filtro inyectados por JS -->
            </div>
        </div>
    </nav>

    <!-- PANEL DE ADMINISTRACIÓN -->
    <section id="adminPanel" class="bg-[#f1eaf5] text-[#141414] py-16 px-6 border-b-8 border-[#a6e3eb] hidden">
        <div class="max-w-4xl mx-auto">
            <div class="flex items-center gap-3 mb-8">
                <h2 class="text-4xl font-black uppercase italic tracking-tighter">Subir Nuevo Proyecto</h2>
            </div>
            
            <form id="projectForm" class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="space-y-4">
                    <label class="block text-[10px] font-black uppercase italic text-[#141414]/60">1. Datos Básicos</label>
                    <input id="projTitle" required placeholder="Título del trabajo" class="w-full bg-white border-2 border-[#141414] text-[#141414] p-4 outline-none focus:ring-4 ring-[#fac459]">
                    
                    <select id="projCategory" class="w-full bg-white border-2 border-[#141414] text-[#141414] p-4 outline-none focus:ring-4 ring-[#fac459]">
                        <option value="Logos">Logos</option>
                        <option value="Videos">Videos</option>
                        <option value="Post">Post</option>
                        <option value="Portadas">Portadas</option>
                        <option value="Miniaturas">Miniaturas</option>
                        <option value="Presentaciones">Presentaciones</option>
                        <option value="Plantillas Canva">Plantillas Canva</option>
                    </select>
                </div>

                <div class="space-y-4">
                    <label class="block text-[10px] font-black uppercase italic text-[#141414]/60">2. Link de Imagen o Video</label>
                    <input id="projUrl" required placeholder="URL de la imagen (Unsplash, etc.)" class="w-full bg-white border-2 border-[#141414] text-[#141414] p-4 outline-none focus:ring-4 ring-[#fac459]">
                    <input id="projLink" placeholder="URL externa opcional" class="w-full bg-white border-2 border-[#141414] text-[#141414] p-2 text-xs outline-none">
                </div>

                <div class="md:col-span-2 space-y-4">
                    <label class="block text-[10px] font-black uppercase italic text-[#141414]/60">3. Descripción</label>
                    <textarea id="projDesc" placeholder="Explica brevemente tu proceso creativo..." class="w-full bg-white border-2 border-[#141414] text-[#141414] p-4 outline-none focus:ring-4 ring-[#fac459] h-24"></textarea>
                </div>

                <button type="submit" class="md:col-span-2 bg-[#141414] text-[#fac459] py-5 font-black uppercase text-sm border-b-8 border-r-8 border-[#f18ccc] hover:scale-[1.01] active:scale-95 transition-all">
                    Publicar en mi Portafolio
                </button>
            </form>
        </div>
    </section>

    <!-- GRID DE PROYECTOS -->
    <main class="max-w-7xl mx-auto px-6 py-24">
        <div id="projectsGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-12">
            <!-- Cargando... -->
        </div>
    </main>

    <!-- FOOTER -->
    <footer class="bg-[#f1eaf5] text-[#141414] py-32 px-6">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-center gap-16">
            <div class="text-center md:text-left">
                <h4 class="text-6xl font-black uppercase tracking-tighter leading-[0.8] mb-4">
                    YCUN<br><span class="text-[#f18ccc]">STUDIO</span>
                </h4>
            </div>
            
            <div class="flex gap-4">
                <div class="w-16 h-16 bg-[#fac459] border-4 border-[#141414] rotate-3"></div>
                <div class="w-16 h-16 bg-[#f18ccc] border-4 border-[#141414] -rotate-6"></div>
                <div class="w-16 h-16 bg-[#a6e3eb] border-4 border-[#141414] rotate-12"></div>
            </div>

            <div class="md:text-right text-[10px] font-black uppercase">
                <p>© 2025 • HECHO PARA DISEÑADORES</p>
            </div>
        </div>
    </footer>

    <!-- Firebase Scripts -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, collection, addDoc, onSnapshot, serverTimestamp, deleteDoc, doc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        // Obtener configuración del entorno
        const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : {
            apiKey: "",
            authDomain: "",
            projectId: "",
            appId: ""
        };

        const app = initializeApp(firebaseConfig);
        const auth = getAuth(app);
        const db = getFirestore(app);
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app';

        let projects = [];
        let currentFilter = 'Todos';
        let currentUser = null;

        const categories = ['Todos', 'Logos', 'Videos', 'Post', 'Portadas', 'Miniaturas', 'Presentaciones', 'Plantillas Canva'];

        // Inicialización siguiendo la Regla 3: Autenticación ANTES de Consultas
        const init = async () => {
            try {
                // Priorizar token personalizado si existe
                if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
                    await signInWithCustomToken(auth, __initial_auth_token);
                } else {
                    await signInAnonymously(auth);
                }
            } catch (error) {
                console.error("Error en la autenticación inicial:", error);
            }

            // Escuchar cambios de estado de autenticación
            onAuthStateChanged(auth, (user) => {
                currentUser = user;
                if (user) {
                    initFilters();
                    listenToProjects();
                } else {
                    console.log("No hay usuario autenticado.");
                }
            });
        };

        init();

        // Escuchar proyectos (Ruta estricta: Regla 1)
        function listenToProjects() {
            if (!currentUser) return;
            
            const collectionPath = `artifacts/${appId}/public/data/portfolio_projects`;
            const q = collection(db, collectionPath);
            
            onSnapshot(q, (snapshot) => {
                projects = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                // Ordenar en memoria (Regla 2: Evitar queries complejas)
                projects.sort((a, b) => {
                    const timeA = a.createdAt?.seconds || 0;
                    const timeB = b.createdAt?.seconds || 0;
                    return timeB - timeA;
                });
                renderProjects();
            }, (error) => {
                console.error("Error en el snapshot de Firestore:", error);
            });
        }

        // Renderizar proyectos
        function renderProjects() {
            const grid = document.getElementById('projectsGrid');
            const filtered = currentFilter === 'Todos' ? projects : projects.filter(p => p.category === currentFilter);
            
            if (filtered.length === 0) {
                grid.innerHTML = `<div class="col-span-full text-center py-20 opacity-20 text-4xl font-black uppercase italic">Vacío</div>`;
                return;
            }

            grid.innerHTML = filtered.map(p => `
                <div class="group bg-[#f1eaf5] text-[#141414] border-b-[12px] border-r-[12px] border-[#fac459] hover:border-[#f18ccc] transition-all duration-300 hover:-translate-y-2">
                    <div class="aspect-video bg-black relative overflow-hidden">
                        <img src="${p.imageUrl || 'https://via.placeholder.com/800x450'}" class="w-full h-full object-cover opacity-90 group-hover:scale-110 transition-all duration-700" onerror="this.src='https://via.placeholder.com/800x450?text=Error+Cargando+Imagen'">
                        <div class="absolute top-4 left-4">
                            <span class="bg-[#141414] text-white px-3 py-1 text-[9px] font-black uppercase tracking-widest">${p.category}</span>
                        </div>
                        <button onclick="window.deleteProject('${p.id}')" class="absolute top-4 right-4 bg-red-600 text-white p-2 opacity-0 group-hover:opacity-100 transition-opacity">
                            🗑️
                        </button>
                    </div>
                    <div class="p-8">
                        <h3 class="text-3xl font-black uppercase tracking-tighter mb-4 line-clamp-2 leading-none">${p.title}</h3>
                        <p class="text-xs font-bold opacity-70 uppercase leading-relaxed mb-8 line-clamp-3">${p.description || ''}</p>
                        ${p.link ? `<a href="${p.link}" target="_blank" class="inline-flex items-center gap-2 bg-[#141414] text-white px-6 py-3 text-[10px] font-black uppercase hover:bg-[#a6e3eb] hover:text-[#141414] transition-all">Ver Proyecto</a>` : ''}
                    </div>
                </div>
            `).join('');
        }

        // Filtros
        function initFilters() {
            const container = document.getElementById('filterContainer');
            container.innerHTML = categories.map(cat => `
                <button onclick="window.setFilter('${cat}')" class="filter-btn px-6 py-2 text-[11px] font-black uppercase tracking-widest whitespace-nowrap transition-all ${cat === currentFilter ? 'bg-[#f18ccc] text-[#141414] border-b-4 border-r-4 border-white' : 'text-[#f1eaf5]/40'}">
                    ${cat}
                </button>
            `).join('');
        }

        window.setFilter = (cat) => {
            currentFilter = cat;
            initFilters();
            renderProjects();
        };

        // Formulario
        document.getElementById('projectForm').onsubmit = async (e) => {
            e.preventDefault();
            if (!currentUser) return;

            try {
                const newItem = {
                    title: document.getElementById('projTitle').value,
                    category: document.getElementById('projCategory').value,
                    imageUrl: document.getElementById('projUrl').value,
                    description: document.getElementById('projDesc').value,
                    link: document.getElementById('projLink').value,
                    createdAt: serverTimestamp(),
                    uid: currentUser.uid
                };

                const collectionPath = `artifacts/${appId}/public/data/portfolio_projects`;
                await addDoc(collection(db, collectionPath), newItem);
                
                document.getElementById('projectForm').reset();
                document.getElementById('adminPanel').classList.add('hidden');
            } catch (error) {
                console.error("Error al añadir documento:", error);
            }
        };

        // Compartir
        document.getElementById('btnShare').onclick = () => {
            const url = window.location.href;
            const temp = document.createElement('textarea');
            temp.value = url;
            document.body.appendChild(temp);
            temp.select();
            document.execCommand('copy');
            document.body.removeChild(temp);

            const toast = document.getElementById('shareToast');
            toast.classList.remove('hidden');
            toast.classList.add('flex');
            setTimeout(() => {
                toast.classList.add('hidden');
                toast.classList.remove('flex');
            }, 3000);
        };

        // Toggle Admin
        document.getElementById('toggleAdmin').onclick = () => {
            document.getElementById('adminPanel').classList.toggle('hidden');
        };

        window.deleteProject = async (id) => {
            if (!currentUser) return;
            if(confirm('¿Eliminar proyecto?')) {
                try {
                    const docPath = `artifacts/${appId}/public/data/portfolio_projects/${id}`;
                    await deleteDoc(doc(db, docPath));
                } catch (error) {
                    console.error("Error al eliminar documento:", error);
                }
            }
        };

    </script>
</body>
</html>
