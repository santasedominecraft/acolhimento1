<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Acolhimento | Santa Sé do Minecraft</title>
  <style>
    /* Estilização Geral e Fundo */
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      padding: 20px;
      margin: 0;
    }

    /* Container do Formulário (Card) */
    .card {
      max-width: 650px;
      margin: 30px auto;
      background: #fff;
      padding: 25px;
      border-radius: 15px;
      box-shadow: 0 5px 20px rgba(0,0,0,.15);
      box-sizing: border-box;
    }

    .card h2 {
      text-align: center;
      color: #7a0000;
      margin-bottom: 20px;
    }

    /* Barra de Progresso */
    .progress {
      height: 8px;
      background: #ddd;
      border-radius: 30px;
      overflow: hidden;
      margin-bottom: 25px;
    }

    .bar {
      height: 100%;
      width: 7.6%; /* Começo proporcional a 1/13 */
      background: #8b0000;
      transition: .3s ease;
    }

    /* Controle de Exibição das Etapas */
    .step {
      display: none;
      animation: fade .3s ease forwards;
    }

    .step.active {
      display: block;
    }

    /* Elementos do Formulário */
    .step h3 {
      color: #333;
      margin-top: 0;
    }

    .step p {
      color: #555;
      line-height: 1.5;
    }

    label {
      display: block;
      font-weight: bold;
      margin-bottom: 8px;
      color: #333;
    }

    input[type="text"],
    input[type="date"],
    input[type="tel"],
    input[type="email"],
    input[type="number"],
    select,
    textarea {
      width: 100%;
      padding: 12px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 15px;
      box-sizing: border-box;
      margin-bottom: 10px;
    }

    textarea {
      height: 120px;
      resize: vertical;
    }

    /* Checkbox centralizado com o texto */
    .checkbox-label {
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: bold;
      cursor: pointer;
    }

    .checkbox-label input {
      width: 18px;
      height: 18px;
      cursor: pointer;
    }

    /* Canais Oficiais */
    .canal-box {
      border-radius: 10px;
      border: 1px solid rgb(221, 221, 221);
      margin: 20px 0px;
      padding: 15px;
      background: #fafafa;
    }

    .canal-box p {
      margin: 0 0 10px 0;
    }

    .canal-box a {
      color: #8b0000;
      text-decoration: none;
      font-weight: bold;
    }

    .canal-box a:hover {
      text-decoration: underline;
    }

    /* Botões de Navegação */
    .nav-buttons {
      display: flex;
      justify-content: space-between;
      margin-top: 25px;
    }

    button {
      background: #8b0000;
      color: #fff;
      padding: 12px 25px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 15px;
      transition: background 0.2s;
    }

    button:hover {
      background: #6b0000;
    }

    button:disabled {
      background: #ccc;
      cursor: not-allowed;
    }

    /* Animação de transição suave lateral */
    @keyframes fade {
      from { opacity: 0; transform: translateX(15px); }
      to { opacity: 1; transform: translateX(0); }
    }
  </style>
</head>
<body>

<div class="card">
  <h2>Acolhimento | Santa Sé</h2>

  <!-- Barra de progresso baseada nas 13 etapas -->
  <div class="progress">
    <div class="bar" id="barra"></div>
  </div>

  <form id="meuForm" action="https://formspree.io/f/xdarzena" method="POST">
    
    <!-- Etapa 1 -->
    <div class="step active">
      <h3>Bem-vindo(a) à Santa Sé do Minecraft!</h3>
      <p>Este formulário possui 13 etapas para garantir o seu correto acolhimento em nossa comunidade.</p>
      <p>Clique em <b>Próximo</b> para começar.</p>
    </div>

    <!-- Etapa 2 -->
    <div class="step">
      <label for="nome">Nome Completo</label>
      <input id="nome" name="Nome" required type="text" placeholder="Seu nome completo" />
    </div>

    <!-- Etapa 3 -->
    <div class="step">
      <label for="nascimento">Data de Nascimento</label>
      <input id="nascimento" name="Nascimento" required type="date" />
    </div>

    <!-- Etapa 4 -->
    <div class="step">
      <label for="telefone">Telefone</label>
      <input id="telefone" name="Telefone" type="tel" placeholder="(00) 00000-0000" />
    </div>

    <!-- Etapa 5 -->
    <div class="step">
      <label for="email">E-mail</label>
      <input id="email" name="Email" required type="email" placeholder="seuemail@exemplo.com" />
    </div>

    <!-- Etapa 6 -->
    <div class="step">
      <label for="catolico">É Católico?</label>
      <select id="catolico" name="Catolico">
        <option>Sim</option>
        <option>Não</option>
      </select>
    </div>

    <!-- Etapa 7 -->
    <div class="step">
      <label for="objetivo">Objetivo no Apostolado</label>
      <textarea id="objetivo" name="Objetivo" placeholder="Conte-nos o que você busca aqui..."></textarea>
    </div>

    <!-- Etapa 8 -->
    <div class="step">
      <label for="vocacao">Vocação desejada</label>
      <select id="vocacao" name="Vocacao">
        <option>Leigo</option>
        <option>Coroinha</option>
        <option>Acólito</option>
        <option>Seminarista</option>
        <option>Padre</option>
      </select>
    </div>

    <!-- Etapa 9 -->
    <div class="step">
      <h3>Canais Oficiais</h3>
      <p>Antes de concluir seu acolhimento, entre em nossos canais oficiais. Após entrar em todos eles, clique em <b>Próximo</b>.</p>
      
      <div class="canal-box">
        <p><b>📢 Canais de Comunicações</b></p>
        <a href="#" target="_blank">Entrar no canal</a>
      </div>

      <div class="canal-box">
        <p><b>🙏 Comunidade dos Leigos</b></p>
        <a href="https://chat.whatsapp.com/KvO7l2PFIqPJ59X7Xc4pLr?s=cl&p=a&ilr=1" target="_blank">Entrar no canal</a>
      </div>

      <div class="canal-box">
        <p><b>🎓 Entre nesse canal se quiser ser Padre, Religioso ou Religiosa</b></p>
        <a href="https://chat.whatsapp.com/BxJYPSVgnY78TTIpYCde5z?s=cl&p=a&ilr=1" target="_blank">Entrar no canal</a>
      </div>
    </div>

    <!-- Etapa 10 -->
    <div class="step">
      <label class="checkbox-label">
        <input required type="checkbox" name="Aceitou_Regras" /> 
        <span>Li e aceito todas as regras da Santa Sé do Minecraft.</span>
      </label>
    </div>

    <!-- Etapa 11 -->
    <div class="step">
      <label class="checkbox-label">
        <input required type="checkbox" name="Aceitou_LGPD" /> 
        <span>Aceito os termos da LGPD. Leia antes de aceitar, basta pesquisar o que é.</span>
      </label>
    </div>

    <!-- Etapa 12 -->
    <div class="step">
      <label for="experiencia">Há quantos anos participa de servidores religiosos?</label>
      <input id="experiencia" name="Experiencia" type="number" min="0" placeholder="Ex: 2" />
    </div>

    <!-- Etapa 13 -->
    <div class="step">
      <label for="comentarios">Limitações suas</label>
      <textarea id="comentarios" name="Comentarios" placeholder="Escreva aqui se possui alguma limitação ou observação importante..."></textarea>
    </div>

    <!-- Área de Botões Modificada -->
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
  const barra = document.getElementById("barra");
  const prevBtn = document.getElementById("prevBtn");
  const nextBtn = document.getElementById("nextBtn");
  const submitBtn = document.getElementById("submitBtn");

  function atualizarInterface() {
    // Atualiza a barra de progresso de forma correta e proporcional
    barra.style.width = ((atual + 1) / steps.length * 100) + "%";

    // Controle do botão Anterior
    if (atual === 0) {
      prevBtn.style.visibility = "hidden";
    } else {
      prevBtn.style.visibility = "visible";
    }

    // Controle dos botões Próximo e Enviar
    if (atual === steps.length - 1) {
      nextBtn.style.display = "none";
      submitBtn.style.display = "inline-block";
    } else {
      nextBtn.style.display = "inline-block";
      submitBtn.style.display = "none";
    }
  }

  function mudarStep(n) {
    // Se o usuário está avançando, valida os campos obrigatórios da etapa atual
    if (n === 1) {
      const camposDaEtapa = steps[atual].querySelectorAll("input, select, textarea");
      let valido = true;

      camposDaEtapa.forEach(campo => {
        if (!campo.checkValidity()) {
          campo.reportValidity();
          valido = false;
        }
      });

      // Se houver algum campo inválido/vazio que seja obrigatório, interrompe a navegação
      if (!valido) return;
    }

    // Altera a etapa ativa
    steps[atual].classList.remove("active");
    atual += n;
    steps[atual].classList.add("active");

    // Atualiza o estado visual da barra e botões
    atualizarInterface();
  }

  // Inicializa o estado visual correto no primeiro carregamento
  atualizarInterface();
</script>

</body>
</html>
