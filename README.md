<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Acolhimento | Santa Sé do Minecraft</title>
  <style>
    body { font-family: sans-serif; background: #f5f5f5; padding: 20px; }
    .card { background: #fff; padding: 20px; border-radius: 10px; max-width: 500px; margin: auto; }
    .step { display: none; }
    .step.active { display: block; }
    input, select, textarea { width: 100%; padding: 8px; margin: 10px 0; }
    .nav { margin-top: 20px; }
  </style>
</head>
<body>

<div class="card">
  <form id="meuForm" action="https://formspree.io/f/xdarzena" method="POST">
    
    <fieldset class="step active">
      <label>Nome:</label>
      <input type="text" name="nome" required>
    </fieldset>

    <fieldset class="step">
      <label>E-mail:</label>
      <input type="email" name="email" required>
    </fieldset>

    <div class="nav">
      <button type="button" id="prevBtn" onclick="mudarStep(-1)" disabled>Anterior</button>
      <button type="button" id="nextBtn" onclick="mudarStep(1)">Próximo</button>
      <button type="submit" id="submitBtn" style="display:none;">Enviar Agora</button>
    </div>
  </form>
</div>

<script>
  let atual = 0;
  const steps = document.querySelectorAll(".step");

  function mudarStep(n) {
    // Validação básica
    if (n === 1 && !steps[atual].querySelector('input').checkValidity()) {
      steps[atual].querySelector('input').reportValidity();
      return;
    }

    steps[atual].classList.remove("active");
    atual += n;
    steps[atual].classList.add("active");

    // Lógica dos botões
    document.getElementById("prevBtn").disabled = (atual === 0);
    document.getElementById("nextBtn").style.display = (atual === steps.length - 1) ? "none" : "inline";
    document.getElementById("submitBtn").style.display = (atual === steps.length - 1) ? "inline" : "none";
  }
</script>

</body>
</html>
