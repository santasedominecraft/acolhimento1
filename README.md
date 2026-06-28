<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Acolhimento | Santa Sé do Minecraft</title>
  <link rel="shortcut icon" type="image/png" href="assets/images/logo.png" />
  <style>
    body { margin: 0; font-family: 'Arial', sans-serif; background: linear-gradient(135deg, #f5f5f5, #eaeaea); }
    .page-wrapper { min-height: 100vh; display: flex; justify-content: center; align-items: center; padding: 20px; position: relative; }
    .card { background: #fff; padding: 30px; border-radius: 18px; box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2); max-width: 520px; width: 100%; transition: all 0.3s ease; }
    .card img { max-width: 100px; margin-bottom: 10px; display: block; margin-left: auto; margin-right: auto; }
    h2 { color: #a51400; text-align: center; margin-bottom: 15px; }
    .progress { display: flex; justify-content: center; gap: 8px; margin-bottom: 25px; }
    .progress span { width: 16px; height: 16px; border-radius: 50%; background: #ccc; transition: background 0.3s; }
    .progress .on { background: #a51400; }
    fieldset { display: none; border: none; padding: 0; margin: 0; opacity: 0; transform: translateY(20px); transition: opacity 0.5s, transform 0.5s; }
    fieldset.active { display: block; opacity: 1; transform: translateY(0); }
    label { display: block; margin-top: 12px; font-weight: bold; }
    input, select, textarea { width: 100%; padding: 10px; margin-top: 6px; border-radius: 10px; border: 1px solid #ccc; box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.05); }
    .btn-canal { display: block; width: 100%; text-align: center; padding: 12px; margin: 8px 0; background: linear-gradient(90deg, #a51400, #f5c518); color: #fff; font-weight: bold; border-radius: 14px; text-decoration: none; }
    .nav-btns { display: flex; justify-content: space-between; margin-top: 20px; }
    .nav-btns button { padding: 12px 22px; border-radius: 14px; border: none; background: #a51400; color: white; cursor: pointer; font-weight: bold; }
    .nav-btns button:disabled { background: #ccc; }
    .extra-field { max-height: 0; overflow: hidden; transition: max-height 0.5s, opacity 0.5s; opacity:0; }
    .extra-field.show { max-height: 200px; opacity: 1; margin-top: 10px; }
  </style>
</head>
<body>
  <div class="page-wrapper">
    <div class="card">
      <div class="text-center">
        <img src="https://acolhimento.santaigreja-minecraft.com/assets/images/santase.png" alt="Logo">
        <h2>Acolhimento | Santa Sé do Minecraft</h2>
      </div>

      <div class="progress" id="progress">
        <span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span>
      </div>

      <form id="inscricaoForm" action="https://formspree.io/f/xdarzena" method="POST">
        <!-- O conteúdo dos fieldsets permanece o mesmo que você já tinha -->
        <fieldset class="step active">
          <p>Seja bem-vindo(a)! Responda tudo com atenção para prosseguirmos.</p>
        </fieldset>
        
        <!-- Adicione aqui os seus demais fieldsets originais -->
        
        <div class="nav-btns">
          <button type="button" id="prevBtn" onclick="nextPrev(-1)" disabled>Anterior</button>
          <button type="button" id="nextBtn" onclick="nextPrev(1)">Próximo</button>
        </div>
      </form>
    </div>
  </div>

  <script>
    const steps = document.querySelectorAll('.step');
    const progress = document.querySelectorAll('.progress span');
    let currentStep = 0;

    function showStep(n) {
      steps.forEach((step,i) => step.classList.toggle('active', i === n));
      progress.forEach((p,i) => p.classList.toggle('on', i <= n));
      document.getElementById('prevBtn').disabled = (n === 0);
      document.getElementById('nextBtn').innerText = (n === steps.length - 1) ? "Enviar" : "Próximo";
    }

    function nextPrev(n) {
      if(n === 1) {
        const inputs = steps[currentStep].querySelectorAll('input,select,textarea');
        for(const input of inputs) { if(!input.checkValidity()) { input.reportValidity(); return; } }
      }
      currentStep += n;
      if(currentStep >= steps.length) { document.getElementById('inscricaoForm').submit(); return; }
      showStep(currentStep);
    }
    
    // Inicializa a primeira bolinha
    showStep(0);
  </script>
</body>
</html>
