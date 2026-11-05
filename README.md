<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Para Naomi ❤️</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  html, body {
    height: 100%;
    overflow: hidden;
    font-family: 'Georgia', 'Segoe UI', serif;
  }

  body {
    background: radial-gradient(circle at 30% 20%, #2b0a1a, #4a0e2a, #1a020c);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    color: #fff;
  }

  /* Corazones de fondo animados */
  .fondo-corazones {
    position: fixed;
    inset: 0;
    pointer-events: none;
    overflow: hidden;
    z-index: 1;
  }
  .fondo-corazones span {
    position: absolute;
    bottom: -10%;
    font-size: 1.5rem;
    color: rgba(255, 100, 150, 0.3);
    animation: subir 15s linear infinite;
    filter: drop-shadow(0 0 10px #ff3366);
  }
  @keyframes subir {
    0% { transform: translateY(0) rotate(0deg); opacity: 0; }
    10% { opacity: 0.8; }
    90% { opacity: 0.8; }
    100% { transform: translateY(-110vh) rotate(360deg); opacity: 0; }
  }

  /* Contenedor principal */
  .escena {
    position: relative;
    z-index: 10;
    width: 100%;
    max-width: 900px;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1.5rem;
    text-align: center;
    overflow-y: auto;
    scrollbar-width: none;
  }
  .escena::-webkit-scrollbar { display: none; }

  /* Tarjeta de mensaje */
  .tarjeta-mensaje {
    background: rgba(255, 255, 255, 0.05);
    backdrop-filter: blur(15px);
    -webkit-backdrop-filter: blur(15px);
    border: 1px solid rgba(255, 150, 180, 0.3);
    border-radius: 30px;
    padding: 3rem 2.5rem;
    box-shadow: 0 20px 50px rgba(255, 0, 80, 0.25), inset 0 0 60px rgba(255, 100, 150, 0.1);
    max-width: 750px;
    width: 100%;
    position: relative;
    transition: all 0.5s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
  }

  .tarjeta-mensaje::before {
    content: '❝';
    position: absolute;
    top: -20px;
    left: 25px;
    font-size: 5rem;
    color: rgba(255, 120, 160, 0.4);
    font-family: Georgia, serif;
    line-height: 1;
  }

  /* Texto de los poemas */
  .linea-texto {
    font-size: 1.6rem;
    line-height: 2.3rem;
    color: #ffe4ec;
    font-weight: 400;
    letter-spacing: 0.5px;
    text-shadow: 0 0 20px #ff3366;
    word-break: break-word;
    transition: all 0.4s;
    animation: fadeInText 0.8s ease;
  }

  @keyframes fadeInText {
    from { opacity: 0; transform: translateY(15px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* Puntos de progreso */
  .progreso {
    display: flex;
    gap: 10px;
    justify-content: center;
  }
  .progreso span {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background: rgba(255, 150, 180, 0.3);
    transition: all 0.3s;
  }
  .progreso span.activo {
    background: #ff4d6d;
    box-shadow: 0 0 12px #ff1e4f, 0 0 25px #ff5e7e;
    transform: scale(1.3);
  }

  /* Botón siguiente */
  .btn-siguiente {
    background: linear-gradient(135deg, #ff4d6d, #c9184a);
    color: white;
    border: none;
    padding: 0.9rem 2.5rem;
    font-size: 1.1rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    border-radius: 50px;
    cursor: pointer;
    font-family: inherit;
    box-shadow: 0 10px 25px rgba(255, 30, 79, 0.5), 0 0 30px rgba(255, 100, 150, 0.3);
    transition: all 0.3s;
    display: inline-flex;
    align-items: center;
    gap: 10px;
    margin-top: 0.5rem;
  }
  .btn-siguiente:hover {
    transform: translateY(-3px) scale(1.03);
    box-shadow: 0 15px 35px rgba(255, 30, 79, 0.7), 0 0 45px rgba(255, 100, 150, 0.6);
  }
  .btn-siguiente:active { transform: scale(0.97); }

  /* Estilos para el mensaje final y la foto */
  .final {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1.5rem;
    animation: fadeInText 1s ease;
  }
  .final .nombre {
    font-size: 3.2rem;
    font-weight: 700;
    background: linear-gradient(135deg, #fff5f8, #ff8da1, #ff1e4f);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    filter: drop-shadow(0 0 25px #ff1e4f) drop-shadow(0 0 50px #ff5e7e);
    letter-spacing: 2px;
    animation: latirNombre 2s infinite ease-in-out;
  }
  @keyframes latirNombre {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.06); }
  }
  .final .mensaje-final {
    font-size: 1.3rem;
    color: #ffd9e6;
    font-style: italic;
    letter-spacing: 1px;
    text-shadow: 0 0 15px #ff3366;
  }

  .contenedor-foto {
    margin-top: 1rem;
    position: relative;
    display: inline-block;
    padding: 8px;
    background: linear-gradient(45deg, #ff4d6d, #ff8da1, #fff, #ff4d6d);
    background-size: 300% 300%;
    border-radius: 20px;
    box-shadow: 0 10px 30px rgba(255, 30, 79, 0.6), 0 0 40px rgba(255, 100, 150, 0.4);
    animation: bordeBrillante 3s ease infinite;
  }
  @keyframes bordeBrillante {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }
  .foto-final {
    display: block;
    max-width: 100%;
    width: 320px;
    height: auto;
    border-radius: 14px;
    border: 3px solid rgba(255, 255, 255, 0.8);
    object-fit: cover;
  }

  /* Responsive */
  @media (max-width: 600px) {
    .linea-texto { font-size: 1.2rem; line-height: 1.8rem; }
    .tarjeta-mensaje { padding: 2rem 1.5rem; }
    .final .nombre { font-size: 2.2rem; }
    .btn-siguiente { padding: 0.7rem 1.8rem; font-size: 0.9rem; }
    .foto-final { width: 250px; }
  }
</style>
</head>
<body>

  <!-- Corazones de fondo -->
  <div class="fondo-corazones" id="fondoCorazones"></div>

  <div class="escena">
    <!-- Tarjeta principal -->
    <div class="tarjeta-mensaje">
      <div class="linea-texto" id="lineaTexto"></div>
      
      <div class="progreso" id="progreso"></div>
      
      <button class="btn-siguiente" id="btnSiguiente">
        <span id="textoBoton">Siguiente</span> <span>➤</span>
      </button>
    </div>
  </div>

<script>
  // ====== CONFIGURACIÓN DE LOS POEMAS ======
  const poemas = [
    "Me acuerdo la primera vez que fui a verte. Yo estaba nervioso y tú hermosísima...",
    "No siempre tengo algo interesante que contarte, pero siempre tengo ganas de hablar contigo.",
    "Contigo soy cursi, gracioso, romántico, infantil y no es que sea así. Tú te ganaste esa parte de mí.",
    "Te besé en la frente, te acomodé el pelo y me quedé mirándote fijamente a los ojos, es por que te convertiste en mi mayor debilidad.",
    "Yo no busco ocupar el primer lugar, tiene que ser tu familia, tus sueños, tus estudios, tu paz mental. Yo solo quiero estar a tu lado mientras construyes todo aquello que te hace bien."
  ];

  const mensajeFinal = {
    nombre: "Naomi",
    frase: "Eres la mujer más maravillosa y hermosa."
  };

  // ====== ESTADO ======
  let pasoActual = 0; 
  const totalPasos = poemas.length + 1; // Poemas + Final

  // ====== ELEMENTOS ======
  const lineaTexto = document.getElementById('lineaTexto');
  const progreso = document.getElementById('progreso');
  const btnSiguiente = document.getElementById('btnSiguiente');
  const textoBoton = document.getElementById('textoBoton');
  const fondoCorazones = document.getElementById('fondoCorazones');

  // ====== CORAZONES DE FONDO ======
  function crearCorazonesFondo() {
    const emojis = ['❤️', '💖', '💗', '💓', '💕', '💘', '💝'];
    const cantidad = 25;
    for (let i = 0; i < cantidad; i++) {
      const span = document.createElement('span');
      span.textContent = emojis[Math.floor(Math.random() * emojis.length)];
      span.style.left = Math.random() * 100 + '%';
      span.style.animationDuration = (10 + Math.random() * 15) + 's';
      span.style.animationDelay = (Math.random() * 15) + 's';
      span.style.fontSize = (1 + Math.random() * 2) + 'rem';
      fondoCorazones.appendChild(span);
    }
  }
  crearCorazonesFondo();

  // ====== PUNTOS DE PROGRESO ======
  function renderProgreso() {
    progreso.innerHTML = '';
    for (let i = 0; i < totalPasos; i++) {
      const dot = document.createElement('span');
      // Marcamos el activo (pasoActual empieza en 1, los indices en 0)
      if (i === pasoActual - 1) dot.classList.add('activo');
      progreso.appendChild(dot);
    }
  }

  // ====== MOSTRAR PASO ======
  function mostrarPaso(n) {
    if (n <= poemas.length) {
      // Mostrar poema
      lineaTexto.innerHTML = poemas[n - 1];
      textoBoton.textContent = (n === poemas.length) ? 'Ver final' : 'Siguiente';
    } else {
      // Mostrar final con la foto
      lineaTexto.innerHTML = `
        <div class="final">
          <div class="nombre">${mensajeFinal.nombre}</div>
          <div class="mensaje-final">${mensajeFinal.frase}</div>
          
          <div class="contenedor-foto">
            <!-- Asegúrate de que la imagen esté en la misma carpeta -->
            <img src="naomi.jpg" alt="Nuestro recuerdo" class="foto-final">
          </div>
        </div>
      `;
      textoBoton.textContent = 'Volver a empezar';
    }
    
    // Efecto visual al cambiar
    lineaTexto.style.animation = 'none';
    lineaTexto.offsetHeight; // Trigger reflow
    lineaTexto.style.animation = 'fadeInText 0.8s ease';
    
    renderProgreso();
  }

  // ====== AVANZAR ======
  function avanzar() {
    if (pasoActual < totalPasos) {
      pasoActual++;
      mostrarPaso(pasoActual);
    } else {
      // Si ya está en el final, reiniciar
      pasoActual = 1;
      mostrarPaso(pasoActual);
    }
    
    // Pequeño efecto de corazones al avanzar
    lluviaCorazones();
  }

  // ====== LLUVIA DE CORAZONES ======
  function lluviaCorazones() {
    const emojis = ['❤️', '💖', '💗', '💓', '💕', '💘'];
    for (let i = 0; i < 8; i++) {
      const c = document.createElement('div');
      c.textContent = emojis[Math.floor(Math.random() * emojis.length)];
      c.style.position = 'fixed';
      c.style.left = Math.random() * 100 + '%';
      c.style.top = '-5%';
      c.style.fontSize = (1.2 + Math.random() * 2) + 'rem';
      c.style.pointerEvents = 'none';
      c.style.zIndex = '9999';
      c.style.transition = 'all 2.5s ease-in';
      c.style.filter = 'drop-shadow(0 0 12px #ff1e4f)';
      document.body.appendChild(c);

      requestAnimationFrame(() => {
        c.style.top = '110%';
        c.style.opacity = '0';
        c.style.transform = `rotate(${Math.random() * 360}deg)`;
      });

      setTimeout(() => c.remove(), 2600);
    }
  }

  // ====== EVENTOS ======
  btnSiguiente.addEventListener('click', avanzar);

  // Permitir avanzar con teclado (Enter o flecha derecha)
  document.addEventListener('keydown', (e) => {
    if (e.key === 'ArrowRight' || e.key === 'Enter') {
      avanzar();
    }
  });

  // Iniciar mostrando el primer poema
  pasoActual = 1;
  mostrarPaso(pasoActual);

</script>
</body>
</html>
