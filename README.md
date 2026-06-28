<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Acolhimento | Santa Sé do Minecraft</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      padding: 40px 20px;
      margin: 0;
    }

    /* FORMULÁRIO MAIS ALTO E ESPAÇADO */
    .card {
      max-width: 650px;
      margin: 0 auto;
      background: #fff;
      padding: 80px 50px; /* Aumentado para dar mais altura interna */
      border-radius: 20px;
      box-shadow: 0 10px 40px rgba(0,0,0,.15);
      min-height: 600px; /* Altura mínima garantida */
      display: flex;
      flex-direction: column;
    }

    .progress {
      height: 12px;
      background: #ddd;
      border-radius: 30px;
      overflow: hidden;
      margin-bottom: 50px; /* Mais espaço abaixo da barra */
    }

    .bar {
      height: 100%;
      width: 7.6%;
      background: #8b0000;
      transition: .4s ease;
    }

    .step {
      display: none;
      animation: fade .4s ease forwards;
    }

    .step.active {
      display: block;
    }

    /* CAMPOS MAIORES E MAIS ALTO */
    label {
      display: block;
      font-weight: bold;
      margin-bottom: 12px;
      color: #333;
      font-size: 18px;
    }

    input, select, textarea {
      width: 100%;
      padding: 20px; /* Campos mais altos */
      margin-bottom: 30px;
      border: 2px solid #ccc;
      border-radius: 12px;
      font-size: 17px;
      box-sizing: border-box;
    }

    textarea {
      height: 200px; /* Área de texto bem maior */
      resize: vertical;
    }

    .nav-buttons {
      margin-top: auto; /* Empurra os botões para baixo se necessário */
      display: flex;
      justify-content: space-between;
      padding-top: 30px;
    }

    button {
      background: #8b0000;
      color: #fff;
      padding: 18px 40px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      font-size: 18px;
      font-weight: bold;
    }

    button:hover { background: #6b0000; }
    button:disabled { background: #ccc; }

    @keyframes fade {
      from { opacity: 0; transform: translateX(15px); }
      to { opacity: 1; transform: translateX(0); }
    }
  </style>
</head>
<body>

<div class="card">
  <!-- LOGO (Substitua a URL abaixo) -->
  <div style="text-align: center; margin-bottom: 40px;">
    <img src="URL_DA_SUA_LOGO_AQUI" alt="Logo" style="max-width: 300px; height: auto;">
  </div>

  <div class="progress">
    <div class="bar" id="barra"></div>
  </div>

  <form id="meuForm" action="https://formspree.io/f/xdarzena" method="POST">
    
    <div class="step active">
      <h3>Bem-vindo(a) à Santa Sé!</h3>
      <p>Este formulário possui 13 etapas. Clique em Próximo.</p>
    </div>

    <div class="step">
      <label>Nome Completo</label>
      <input name="Nome" required type="text">
    </div>

    <div class="step">
      <label>Data de Nascimento</label>
      <input name="Nascimento" required type="date">
    </div>

    <div class="step">
      <label>Telefone</label>
      <input name="Telefone" type="tel">
    </div>

    <div class="step">
      <label>E-mail</label>
      <input name="Email" required type="email">
    </div>

    <div class="step">
      <label>É Católico?</label>
      <select name="Catolico"><option>Sim</option><option>Não</option></select>
    </div>

    <div class="step">
      <label>Objetivo no Apostolado</label>
      <textarea name="Objetivo"></textarea>
    </div>

    <div class="step">
      <label>Vocação desejada</label>
      <select name="Vocacao">
        <option>Leigo</option><option>Coroinha</option><option>Acólito</option>
        <option>Seminarista</option><option>Padre</option>
      </select>
    </div>

    <div class="step">
      <h3>Canais Oficiais</h3>
      <p>Entre nos links abaixo e clique em Próximo.</p>
      <div style="padding: 20px; border: 1px solid #ddd; margin: 20px 0;">
        <a href="https://chat.whatsapp.com/KvO7l2PFIqPJ59X7Xc4pLr" target="_blank">Comunidade dos Leigos</a>
      </div>
    </div>

    <div class="step">
      <label><input required type="checkbox" name="Regras"> Li e aceito as regras.</label>
    </div>

    <div class="step">
      <label><input required type="checkbox" name="LGPD"> Aceito os termos da LGPD.</label>
    </div>

    <div class="step">
      <label>Há quantos anos participa?</label>
      <input name="Experiencia" type="number">
    </div>

    <div class="step">
      <label>Limitações</label>
      <textarea name="Comentarios"></textarea>
    </div>

    <div class="nav-buttons">
      <button type="button" id="prevBtn" onclick="mudarStep(-1)">Anterior</button>
      <button type="button" id="nextBtn" onclick="mudarStep(1)">Próximo</button>
      <button type="submit" id="submitBtn" style="display:none;">Enviar Agora</button>
    </div>
  </form>
</div>

<script>
  let atual = 0;
  const steps = document.querySelectorAll(".step");
  function mudarStep(n) {
    if (n === 1 && !steps[atual].querySelector('input, select, textarea').checkValidity()) {
      steps[atual].querySelector('input, select, textarea').reportValidity();
      return;
    }
    steps[atual].classList.remove("active");
    atual += n;
    steps[atual].classList.add("active");
    document.getElementById("barra").style.width = ((atual + 1) / steps.length * 100) + "%";
    document.getElementById("prevBtn").style.visibility = (atual === 0) ? "hidden" : "visible";
    document.getElementById("nextBtn").style.display = (atual === steps.length - 1) ? "none" : "inline-block";
    document.getElementById("submitBtn").style.display = (atual === steps.length - 1) ? "inline-block" : "none";
  }
</script>
</body>
</html>
