<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Acolhimento | Santa Sé do Minecraft</title>
  <style>
    /* Seus estilos originais mantidos */
    body { margin: 0; font-family: 'Arial', sans-serif; background: linear-gradient(135deg, #f5f5f5, #eaeaea); }
    .page-wrapper { min-height: 100vh; display: flex; justify-content: center; align-items: center; padding: 20px; }
    .card { background: #fff; padding: 30px; border-radius: 18px; box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2); max-width: 520px; width: 100%; }
    h2 { color: #a51400; text-align: center; }
    fieldset { display: none; border: none; padding: 0; margin: 0; }
    fieldset.active { display: block; }
    input, select, textarea { width: 100%; padding: 10px; margin-top: 6px; border-radius: 10px; border: 1px solid #ccc; box-sizing: border-box; }
    .nav-btns { display: flex; justify-content: space-between; margin-top: 20px; }
    button { padding: 12px 22px; border-radius: 14px; border: none; background: #a51400; color: white; cursor: pointer; }
  </style>
</head>
<body>
  <div class="page-wrapper">
    <div class="card">
      <h2>Acolhimento | Santa Sé do Minecraft</h2>
      
      <form id="inscricaoForm" action="https://formspree.io/f/xdarzena" method="POST">
        
        <fieldset class="step active">
          <p>Seja bem-vindo(a)! Preencha os dados abaixo.</p>
          <label>Nome Completo</label><input type="text" name="nome" required>
        </fieldset>

        <fieldset class="step">
          <label>E-mail</label><input type="email" name="email" required>
          <label>Telefone</label><input type="text" name="telefone" required>
        </fieldset>

        <div class="nav-btns">
          <button type="button" id="prevBtn" onclick="nextPrev(-1)" disabled>Anterior</button>
          <button type="button" id="nextBtn" onclick="nextPrev(1)">Próximo</button>
        </div>
      </form>
    </div>
  </div>

  <script>
    let currentStep = 0;
    const steps = document.querySelectorAll('.step');

    function nextPrev(n) {
      if (n == 1 && !validateForm()) return false;
      
      steps[currentStep].classList.remove('active');
      currentStep += n;

      if (currentStep >= steps.length) {
        // Envia o formulário da forma padrão (sem erro JSON)
        document.getElementById("inscricaoForm").submit();
        return false;
      }
      
      steps[currentStep].classList.add('active');
      document.getElementById('prevBtn').disabled = (currentStep == 0);
      document.getElementById('nextBtn').innerText = (currentStep == steps.length - 1) ? "Enviar" : "Próximo";
    }

    function validateForm() {
      let inputs = steps[currentStep].querySelectorAll('input, select, textarea');
      for (let i = 0; i < inputs.length; i++) {
        if (!inputs[i].checkValidity()) { inputs[i].reportValidity(); return false; }
      }
      return true;
    }
  </script>
</body>
</html>
