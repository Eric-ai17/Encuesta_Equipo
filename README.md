<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>¿Compras local o global?</title>
<style>
  :root{
    --manglar:#1F4D3A; --hoja:#3E7D5A; --salvia:#EAF1E8; --mango:#F2B33D;
    --tinta:#17301F; --papel:#FFFFFF; --borde:#C9D9C6; --error:#A33A2B;
  }
  *{box-sizing:border-box}
  body{margin:0;font-family:system-ui,-apple-system,"Segoe UI",Roboto,sans-serif;
    background:var(--salvia);color:var(--tinta);line-height:1.5}
  header{background:var(--manglar);color:#fff;padding:2.2rem 1.2rem 2.6rem}
  header .wrap{max-width:640px;margin:0 auto}
  h1{font-size:clamp(1.8rem,6vw,2.6rem);line-height:1.1;margin:0 0 .6rem}
  header p{margin:0;opacity:.9;max-width:52ch}
  main{max-width:640px;margin:-1.2rem auto 2rem;padding:0 1rem}
  .pregunta{background:var(--papel);border:1px solid var(--borde);border-radius:14px;
    padding:1rem 1.1rem;margin-bottom:.9rem}
  .pregunta.falta{border-color:var(--error);box-shadow:0 0 0 2px #a33a2b33}
  .pregunta h2{font-size:1.05rem;margin:0 0 .7rem}
  .opciones{display:flex;flex-wrap:wrap;gap:.5rem}
  .opciones label{cursor:pointer}
  .opciones input{position:absolute;opacity:0;pointer-events:none}
  .opciones span{display:inline-block;padding:.5rem .9rem;border:1.5px solid var(--borde);
    border-radius:999px;background:#fff;transition:background .15s,border-color .15s}
  .opciones input:checked + span{background:var(--hoja);border-color:var(--hoja);color:#fff}
  .opciones input:focus-visible + span{outline:3px solid var(--mango);outline-offset:2px}
  .acciones{display:flex;flex-wrap:wrap;gap:.7rem;margin:1.2rem 0}
  button{font:inherit;font-weight:600;border:0;border-radius:10px;padding:.85rem 1.3rem;cursor:pointer}
  #btnEnviar{background:var(--manglar);color:#fff;flex:1 1 200px}
  #btnReporte{background:var(--mango);color:var(--tinta);flex:1 1 160px}
  button:disabled{opacity:.55;cursor:wait}
  button:focus-visible{outline:3px solid var(--mango);outline-offset:2px}
  #salida{display:none;background:var(--papel);border-left:5px solid var(--hoja);border-radius:10px;
    padding:1rem 1.1rem;white-space:pre-line;font-size:.95rem}
  #salida.error{border-left-color:var(--error);color:var(--error)}
  footer{text-align:center;font-size:.85rem;opacity:.7;padding-bottom:2rem}
</style>
</head>
<body>
<header>
  <div class="wrap">
    <h1>¿Compras local o global?</h1>
    <p>Encuesta anónima sobre hábitos de compra para la materia de Desarrollo Sustentable (TecNM Mazatlán). No pedimos tu nombre y toma menos de un minuto.</p>
  </div>
</header>

<main>
  <form id="encuesta" onsubmit="return false">
    <div class="pregunta" data-campo="comida">
      <h2>¿Dónde compras la mayor parte de tu comida?</h2>
      <div class="opciones">
        <label><input type="radio" name="comida" value="Mercado o tianguis"><span>Mercado o tianguis</span></label>
        <label><input type="radio" name="comida" value="Tienda de barrio"><span>Tienda de barrio</span></label>
        <label><input type="radio" name="comida" value="Supermercado"><span>Supermercado</span></label>
        <label><input type="radio" name="comida" value="En línea"><span>En línea</span></label>
      </div>
    </div>

    <div class="pregunta" data-campo="ropa">
      <h2>¿Dónde compras tu ropa?</h2>
      <div class="opciones">
        <label><input type="radio" name="ropa" value="Negocio local"><span>Negocio local</span></label>
        <label><input type="radio" name="ropa" value="Tienda departamental"><span>Tienda departamental</span></label>
        <label><input type="radio" name="ropa" value="App internacional"><span>App internacional</span></label>
        <label><input type="radio" name="ropa" value="Segunda mano"><span>Segunda mano</span></label>
      </div>
    </div>

    <div class="pregunta" data-campo="apps">
      <h2>¿Con qué frecuencia compras en apps internacionales?</h2>
      <div class="opciones">
        <label><input type="radio" name="apps" value="Nunca"><span>Nunca</span></label>
        <label><input type="radio" name="apps" value="Una vez al mes"><span>Una vez al mes</span></label>
        <label><input type="radio" name="apps" value="Varias veces al mes"><span>Varias veces al mes</span></label>
        <label><input type="radio" name="apps" value="Cada semana"><span>Cada semana</span></label>
      </div>
    </div>

    <div class="pregunta" data-campo="criterio">
      <h2>¿Qué pesa más al comprar?</h2>
      <div class="opciones">
        <label><input type="radio" name="criterio" value="Precio"><span>Precio</span></label>
        <label><input type="radio" name="criterio" value="Calidad"><span>Calidad</span></label>
        <label><input type="radio" name="criterio" value="Cercanía"><span>Cercanía</span></label>
        <label><input type="radio" name="criterio" value="Apoyar lo local"><span>Apoyar lo local</span></label>
        <label><input type="radio" name="criterio" value="Marca"><span>Marca</span></label>
      </div>
    </div>

    <div class="pregunta" data-campo="origen">
      <h2>¿Sabes de dónde viene lo que compras?</h2>
      <div class="opciones">
        <label><input type="radio" name="origen" value="Sí"><span>Sí</span></label>
        <label><input type="radio" name="origen" value="A veces"><span>A veces</span></label>
        <label><input type="radio" name="origen" value="No"><span>No</span></label>
      </div>
    </div>

    <div class="pregunta" data-campo="edad">
      <h2>Rango de edad</h2>
      <div class="opciones">
        <label><input type="radio" name="edad" value="Menos de 18"><span>Menos de 18</span></label>
        <label><input type="radio" name="edad" value="18 a 29"><span>18 a 29</span></label>
        <label><input type="radio" name="edad" value="30 a 49"><span>30 a 49</span></label>
        <label><input type="radio" name="edad" value="50 o más"><span>50 o más</span></label>
      </div>
    </div>

    <div class="acciones">
      <button type="button" id="btnEnviar">Enviar respuesta</button>
      <button type="button" id="btnReporte">Generar reporte</button>
    </div>
  </form>

  <div id="salida" role="status" aria-live="polite"></div>
</main>

<footer>Desarrollo Sustentable · Práctica 4.2</footer>

<script>
  // PEGA AQUÍ LA URL DE TU WEBHOOK DE MAKE (entre las comillas)
  const WEBHOOK_URL = "PEGA_AQUI_TU_URL_DE_MAKE";

  const CAMPOS = ["comida","ropa","apps","criterio","origen","edad"];
  const form = document.getElementById("encuesta");
  const salida = document.getElementById("salida");
  const btnEnviar = document.getElementById("btnEnviar");
  const btnReporte = document.getElementById("btnReporte");

  function mostrar(texto, esError){
    salida.style.display = "block";
    salida.classList.toggle("error", !!esError);
    salida.textContent = texto;
  }
  function bloquear(si){ btnEnviar.disabled = si; btnReporte.disabled = si; }

  async function enviar(params){
    bloquear(true);
    mostrar("Procesando...");
    try{
      const resp = await fetch(WEBHOOK_URL, { method:"POST", body: params });
      if(!resp.ok) throw new Error(resp.status);
      const texto = await resp.text();
      mostrar(texto);
      return true;
    }catch(e){
      mostrar("No se pudo conectar, intenta de nuevo.", true);
      return false;
    }finally{
      bloquear(false);
    }
  }

  btnEnviar.addEventListener("click", async () => {
    const params = new URLSearchParams();
    params.append("accion","respuesta");
    let faltan = 0;
    CAMPOS.forEach(c => {
      const marcada = form.querySelector('input[name="'+c+'"]:checked');
      const bloque = form.querySelector('[data-campo="'+c+'"]');
      bloque.classList.toggle("falta", !marcada);
      if(marcada) params.append(c, marcada.value); else faltan++;
    });
    if(faltan){
      mostrar("Falta contestar " + faltan + (faltan === 1 ? " pregunta." : " preguntas."), true);
      return;
    }
    const ok = await enviar(params);
    if(ok) form.reset();
  });

  btnReporte.addEventListener("click", () => {
    const params = new URLSearchParams();
    params.append("accion","reporte");
    enviar(params);
  });
</script>
</body>
</html>
