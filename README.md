# intelig-ncia-artificial-0.1
<nav class="tabs">
  <button onclick="openTab('problema')" class="tab-btn active">1. Problema</button>
  <button onclick="openTab('persona')" class="tab-btn">2. Personas</button>
  <button onclick="openTab('prototipo')" class="tab-btn">3. Protótipo</button>
  <button onclick="openTab('apresentacao')" class="tab-btn">4. Apresentação</button>
  <button onclick="openTab('pitch')" class="tab-btn">5. Pitch</button>
</nav>

<main class="container">
  <section id="problema" class="tab-content active">
    <h2>Mapeamento do Problema</h2>
    <p>Estudantes têm dificuldade de organizar tarefas e gerenciar tempo sem distrações.</p>
    <div class="card">
      <h3>Dores Identificadas</h3>
      <ul>
        <li>Procrastinação frequente no celular.</li>
        <li>Falta de planejamento semanal visível.</li>
      </ul>
    </div>
  </section>

  <section id="persona" class="tab-content">
    <h2>Persona</h2>
    <div class="card">
      <h3>Lucas, 17 anos</h3>
      <p><strong>Meta:</strong> Passar no vestibular sem exaustão mental.</p>
      <p><strong>Frustração:</strong> Não sabe por onde começar a estudar quando a matéria acumula.</p>
    </div>
  </section>

  <section id="prototipo" class="tab-content">
    <h2>Protótipo: Timer de Foco</h2>
    <div class="card interactive">
      <h3 id="timer">25:00</h3>
      <button onclick="startTimer()">Iniciar Ciclo</button>
    </div>
  </section>

  <section id="apresentacao" class="tab-content">
    <h2>Apresentação da Solução</h2>
    <p>Nossa plataforma unifica a organização visual de tarefas com um timer de foco Pomodoro.</p>
  </section>

  <section id="pitch" class="tab-content">
    <h2>Pitch de 1 Minuto</h2>
    <div class="card">
      <p><strong>O Problema:</strong> Alunos perdem tempo tentando se organizar.</p>
      <p><strong>A Solução:</strong> Uma ferramenta leve que combina foco e planejamento em um clique.</p>
    </div>
  </section>
</main>
body {
  font-family: Arial, sans-serif;
  background: #f4f4f9;
  margin: 0;
  padding: 20px;
}

.tabs {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

.tab-btn {
  padding: 10px 15px;
  border: none;
  background: #e0e0e0;
  cursor: pointer;
  border-radius: 5px;
}

.tab-btn.active {
  background: #007bff;
  color: white;
}

.tab-content {
  display: none;
}

.tab-content.active {
  display: block;
}

.card {
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  margin-top: 10px;
}

.interactive {
  text-align: center;
}
function openTab(tabId) {
  document.querySelectorAll('.tab-content').forEach(tab => tab.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
  
  document.getElementById(tabId).classList.add('active');
  event.currentTarget.classList.add('active');
}

let timerInterval;
function startTimer() {
  let time = 1500;
  clearInterval(timerInterval);
  timerInterval = setInterval(() => {
    let minutes = Math.floor(time / 60);
    let seconds = time % 60;
    document.getElementById('timer').innerText = 
      `${minutes}:${seconds < 10 ? '0' : ''}${seconds}`;
    if (time > 0) time--;
    else clearInterval(timerInterval);
  }, 1000);
}
