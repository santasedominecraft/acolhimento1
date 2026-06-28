<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Acolhimento | Santa Sé do Minecraft</title>
  <style>
    body { margin: 0; font-family: 'Arial', sans-serif; background: linear-gradient(135deg, #f5f5f5, #eaeaea); }
    .page-wrapper { min-height: 100vh; display: flex; justify-content: center; align-items: center; padding: 20px; }
    .card { background: #fff; padding: 30px; border-radius: 18px; box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2); max-width: 520px; width: 100%; }
    h2 { color: #a51400; text-align: center; }
    fieldset { display: none; border: none; padding: 0; margin: 0; }
    fieldset.active { display: block; }
    label { display: block; margin-top: 12px; font-weight: bold; }
    input, select, textarea { width: 100%; padding: 10px; margin-top: 6px; border-radius: 10px; border: 1px solid #ccc; box-sizing: border-box; }
    .btn-canal { display: block; text-align: center; padding: 12px; margin: 8px 0; background: #a51400; color: #fff; text-decoration: none; border-radius: 14px; }
    .nav-btns { display: flex; justify-content: space-between; margin-top: 20px; }
    button { padding: 12px 22px; border-radius: 14px; border: none; background: #a51400; color: white; cursor: pointer; font-weight: bold; }
    button:disabled { background: #ccc; }
  </style>
</head>
<body>
  <div class="page-wrapper">
    <div class="card">
      <h2>Acolhimento | Santa Sé do Minecraft</h2>
      <form id="inscricaoForm">
        
        <fieldset class="step active">
          <p>Seja bem-vindo(a)! Responda tudo com atenção para prosseguirmos.</p>
        </fieldset>

        <fieldset class="step">
          <label>Nome Completo</label><input type="text" name="nome" required>
          <label>Data de Nascimento</label><input type="date" name="nascimento" required>
          <label>Telefone</label><input type="tel" name="telefone" required>
          <label>E-mail</label><input type="email" name="email" required>
        </fieldset>

        <fieldset class="step">
          <label>Vocação desejada</label>
          <select name="vocacao" id="vocacao">
            <option value="Leigo">Leigo(a)</option>
            <option value="Diacono">Diácono</option>
            <option value="Padre">Padre</option>
          </select>
        </fieldset>

        <fieldset class="step">
          <p>Participe de nossos canais oficiais:</p>
          <a class="btn-canal" href="https://whatsapp.com/channel/0029Vb2twt41iUxdwcnL6I1S" target="_blank">Canal WhatsApp</a>
        </fieldset>

        <fieldset class="step">
          <label><input type="checkbox" name="regras" required> Li e aceito as regras.</label>
        </fieldset>

        <fieldset class="step">
          <label><input type="checkbox" name="lgpd" required> Aceito a política de privacidade.</label>
        </fieldset>

        <fieldset class="step">
          <label>Já participou de apostolado virtual?</label>
          <select name="experiencia"><option>Sim</option><option>Não</option></select>
        </fieldset>

        <fieldset class="step">
          <label>Tempo de experiência (anos)</label><input type="number" name="tempo">
        </fieldset>

        <fieldset class="step">
          <label>Disponibilidade semanal</label><input type="text" name="disponibilidade">
        </fieldset>

        <fieldset class="step">
          <label>Habilidades</label><textarea name="habilidade"></textarea>
        </fieldset>

        <fieldset class="step">
          <label>Instagram</label><input type="url" name="instagram">
        </fieldset>

        <fieldset class="step">
          <label>Referências</label><input type="text" name="referencia">
        </fieldset>

        <fieldset class="step">
          <label>Deseja receber notícias?</label>
          <select name="noticias"><option>Sim</option><option>Não</option></select>
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
      if (n == 1 && !steps[currentStep].querySelector('input,select,textarea').checkValidity()) { 
        steps[currentStep].querySelector('input,select,textarea').reportValidity(); 
        return; 
      }
      steps[currentStep].classList.remove('active');
      currentStep += n;
      if (currentStep >= steps.length) {
        enviarFormulario();
        return;
      }
      steps[currentStep].classList.add('active');
      document.getElementById('prevBtn').disabled = (currentStep == 0);
      document.getElementById('nextBtn').innerText = (currentStep == steps.length - 1) ? "Enviar" : "Próximo";
    }

    async function enviarFormulario() {
      const form = document.getElementById('inscricaoForm');
      const response = await fetch("https://formspree.io/f/xdarzena", {
        method: "POST",
        body: new FormData(form),
        headers: { 'Accept': 'application/json' }
      });
      if (response.ok) { alert("Enviado com sucesso!"); window.location.reload(); }
      else { alert("Erro ao enviar."); }
    }
  </script>
</body>
</html>
