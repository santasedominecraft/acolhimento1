<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Acolhimento | Santa Sé do Minecraft</title>
  <link rel="shortcut icon" type="image/png" href="assets/images/logo.png" />
  <style>
    body {
      margin: 0;
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #f5f5f5, #eaeaea);
    }
    .page-wrapper {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
      position: relative;
    }
    .card {
      background: #fff;
      padding: 30px;
      border-radius: 18px;
      box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
      max-width: 520px;
      width: 100%;
      transition: all 0.3s ease;
    }
    .card img {
      max-width: 100px;
      margin-bottom: 10px;
    }
    h2 {
      color: #a51400;
      text-align: center;
      margin-bottom: 15px;
    }
    .progress {
      display: flex;
      justify-content: center;
      gap: 8px;
      margin-bottom: 25px;
    }
    .progress span {
      width: 16px;
      height: 16px;
      border-radius: 50%;
      background: #ccc;
      position: relative;
      transition: background 0.3s;
    }
    .progress .on { background: #a51400; }
    fieldset {
      display: none;
      border: none;
      padding: 0;
      margin: 0;
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.5s, transform 0.5s;
    }
    fieldset.active {
      display: block;
      opacity: 1;
      transform: translateY(0);
    }
    label { display: block; margin-top: 12px; font-weight: bold; }
    input, select, textarea {
      width: 100%;
      padding: 10px;
      margin-top: 6px;
      border-radius: 10px;
      border: 1px solid #ccc;
      box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.05);
      transition: 0.3s;
    }
    input:focus, select:focus, textarea:focus {
      outline: none;
      border-color: #a51400;
      box-shadow: 0 0 6px rgba(165, 20, 0, 0.5);
    }
    .btn-canal {
      display: block;
      width: 100%;
      text-align: center;
      padding: 12px;
      margin: 8px 0;
      background: linear-gradient(90deg, #a51400, #f5c518);
      color: #fff;
      font-weight: bold;
      border-radius: 14px;
      text-decoration: none;
      box-shadow: 0 5px 12px rgba(0, 0, 0, 0.2);
      transition: transform 0.15s, filter 0.2s;
    }
    .btn-canal:hover {
      filter: brightness(1.15);
      transform: translateY(-2px);
    }
    .nav-btns {
      display: flex;
      justify-content: space-between;
      margin-top: 20px;
    }
    .nav-btns button {
      padding: 12px 22px;
      border-radius: 14px;
      border: none;
      background: #a51400;
      color: white;
      cursor: pointer;
      font-weight: bold;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      transition: filter 0.2s, transform 0.1s;
    }
    .nav-btns button:hover {
      filter: brightness(1.15);
      transform: translateY(-2px);
    }
    .nav-btns button:disabled { background: #ccc; cursor: not-allowed; }
    .extra-field { max-height: 0; overflow: hidden; transition: max-height 0.5s, opacity 0.5s; opacity:0; margin-top:10px; }
    .extra-field.show { max-height:200px; opacity:1; }
    /* LGPD Badge */
    .lgpd-badge {
      position: absolute;
      top: 10px;
      right: 10px;
      display: flex;
      align-items: center;
      background: #a51400;
      color: #fff;
      padding: 5px 10px;
      border-radius: 14px;
      font-weight: bold;
      text-decoration: none;
      gap: 5px;
    }
    .lgpd-badge svg { fill: #fff; }
  </style>
</head>
<body>
  <div class="page-wrapper">
    <a class="lgpd-badge" href="politica_privacidade.html" target="_blank" title="Saiba como seus dados são protegidos">
      <svg viewBox="0 0 24 24" width="18" height="18" fill="currentColor">
        <path d="M12 2l7 3v6c0 5.55-3.84 10.74-7 12-3.16-1.26-7-6.45-7-12V5l7-3z" />
      </svg>
      <span>LGPD</span>
    </a>

    <div class="card">
      <div class="text-center">
        <img src="https://acolhimento.santaigreja-minecraft.com/assets/images/santase.png" <h2></></></> <h2>Acolhimento | Santa Sé do Minecraft</h2>
      </div>

      <div class="progress">
        <span class="on"></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span>
      </div>

      <form id="inscricaoForm" action="#" method="post">
        <!-- PASSO 1 -->
        <fieldset class="step active">
          <p>⭐| Seja bem-vindo(a)! Você está entrando na Santa Sé do Minecraft! Olha que Legal! Você sabia que no Minecraft você pode ser: Padre, Diácono, Coroinha, Ministro extraordinário da Comunhão, Leitor, Guarda Suiça no Vaticano, Irmã missionária da caridade e até mesmo ocupar cargos políticos! Um máximo, né?

          </p>Este formulário é o primeiro passo para você fazer parte do nosso Apostolado em Minecraft. Queremos conhecer você melhor e ajudá-lo(a). Por isso, é MUITO importante que você responda TUDO e faça tudo direitinho. Tenho certeza que se você fizer tudo certinho, não irá ter dificuldades em participar com a gente!</p>
        </fieldset>
        <!-- PASSO 2 -->
        <fieldset class="step">
          <legend><strong>Dados Pessoais</strong></legend>
          <label>Nome Completo</label><input type="text" name="nome" required>
          <label>Data de Nascimento</label><input type="date" name="nascimento" required>
          <label>Telefone (+55 83 98229-9356)</label><input type="tel" name="telefone" pattern="^\+\d{1,3}\d{2}\d{8,9}$" required>
          <label>E-mail</label><input type="email" name="email" required>
          <label>Você é Católico?</label>
          <select name="catolico" required>
            <option value="">Selecione</option>
            <option>Sim</option>
            <option>Não</option>
          </select>
          <label>Objetivo no Apostolado</label>
          <textarea name="objetivo" rows="4" required></textarea>
        </fieldset>
        <!-- PASSO 3 -->
        <fieldset class="step">
          <legend><strong>Escolha sua vocação</strong></legend>
          <label>Vocação desejada</label>
          <select id="vocacao" name="vocacao" required onchange="showExtraFields(this.value)">
            <option value="">Selecione</option>
            <option value="Leigo">Leigo(a)</option>
            <option value="Diacono">Diácono</option>
            <option value="Padre">Padre</option>
            <option value="Religioso">Religioso(a)</option>
            <option value="Irma">Irmã da Caridade</option>
          </select>
          <div id="extraDiocese" class="extra-field">
            <label>Sua Diocese</label>
            <select name="diocese">
              <option value="">Selecione</option>
              <option>Diocese de Roma</option>
            </select>
          </div>
        </fieldset>
        <!-- PASSO 4: Canais -->
        <fieldset class="step">
          <legend><strong>Grupos e Canais</strong></legend>
          <p>Participe de nossos canais oficiais:</p>
          <a class="btn-canal" href="https://whatsapp.com/channel/0029Vb2twt41iUxdwcnL6I1S" target="_blank">Canal Oficial WhatsApp</a>
          <a class="btn-canal" href="https://chat.whatsapp.com/IlmqgzaeZxVFSYN7R9gaG8?mode=ems_copy_c" target="_blank">Papinho da Comunidade</a>
          <a class="btn-canal" href="https://discord.gg/h9Kasu5t" target="_blank">Servidor Discord</a>
        </fieldset>
        <!-- PASSO 5: Regras -->
        <fieldset class="step">
          <legend><strong>📜 Regras da Comunidade</strong></legend>
          <p>Antes de entrar nos canais, é importante que você conheça e aceite nossas regras:</p>
          <ul>
            <li>Respeitar todos os membros da comunidade.</li>
            <li>Não compartilhar conteúdos ofensivos ou impróprios.</li>
            <li>Participar dos grupos de forma construtiva e religiosa.</li>
            <li>Seguir orientações dos líderes e do Papa da comunidade.</li>
          </ul>
          <label><input type="checkbox" id="aceiteRegras" required> Li e aceito todas as regras da comunidade.</label>
        </fieldset>
        <!-- PASSO 6: Confirmação LGPD -->
        <fieldset class="step">
          <legend><strong>🔒 Confirmação de Política de Privacidade</strong></legend>
          <p>Confirme que leu e concorda com a política de privacidade da comunidade.</p>
          <label><input type="checkbox" id="lgpdConsent" required> Li e concordo com a política de privacidade conforme a LGPD.</label>
        </fieldset>
        <!-- PASSOS 7 a 13 -->
        <fieldset class="step">
          <legend><strong>Atividades e Experiência</strong></legend>
          <label>Você já participou de algum apostolado virtual?</label>
          <select name="experiencia" required>
            <option value="">Selecione</option>
            <option>Sim</option>
            <option>Não</option>
          </select>
          <label>Tempo de experiência em atividades religiosas (anos)</label>
          <input type="number" name="tempoExperiencia" min="0" required>
          <label>Qual sua disponibilidade semanal (horas)?</label>
          <input type="text" name="disponibilidade" placeholder="Ex: 10 horas/semana" required>
          <label>Você possui alguma habilidade ou função específica?</label>
          <textarea name="habilidade" rows="3"></textarea>
        </fieldset>
        <fieldset class="step">
          <legend><strong>Redes Sociais</strong></legend>
          <label>Instagram (opcional)</label>
          <input type="url" name="instagram" placeholder="https://instagram.com/seuperfil">
          <label>Facebook (opcional)</label>
          <input type="url" name="facebook" placeholder="https://facebook.com/seuperfil">
          <label>Discord (opcional)</label>
          <input type="url" name="discord" placeholder="https://discord.gg/seuservidor">
        </fieldset>
        <fieldset class="step">
          <legend><strong>Referências</strong></legend>
          <label>Indique algum membro da comunidade que você conheça</label>
          <input type="text" name="referencia">
          <label>Referência adicional (opcional)</label>
          <input type="text" name="referenciaOpcional">
        </fieldset>
        <fieldset class="step">
          <legend><strong>Confirmação de Participação</strong></legend>
          <label>Deseja receber notícias e atualizações da comunidade?</label>
          <select name="noticias" required>
            <option value="">Selecione</option>
            <option>Sim</option>
            <option>Não</option>
          </select>
          <label>Comentários adicionais</label>
          <textarea name="comentarios" rows="3"></textarea>
        </fieldset>

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
      steps.forEach((step,i)=>step.classList.toggle('active', i===n));
      progress.forEach((p,i)=>p.classList.toggle('on', i<=n));
      document.getElementById('prevBtn').disabled = n===0;
      document.getElementById('nextBtn').innerText = n===steps.length-1 ? "Enviar" : "Próximo";
    }

    function nextPrev(n){
      if(n===1){
        const inputs = steps[currentStep].querySelectorAll('input,select,textarea');
        for(const input of inputs){ if(!input.checkValidity()){ input.reportValidity(); return; } }
      }
      currentStep+=n;
      if(currentStep>=steps.length){ document.getElementById('inscricaoForm').submit(); return; }
      showStep(currentStep);
    }

    function showExtraFields(vocacao){
      const div = document.getElementById('extraDiocese');
      if(vocacao==='Padre' || vocacao==='Diacono' || vocacao==='Religioso' || vocacao==='Irma'){ div.classList.add('show'); }
      else{ div.classList.remove('show'); }
    }
  </script>
</body>
</html>
