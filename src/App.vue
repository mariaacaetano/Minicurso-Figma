<script setup>
const services = [
  {
    icon: '⚡',
    title: 'Estratégia',
    text: 'Posicionamento com clareza para sua marca saber onde quer chegar.',
  },
  {
    icon: '🎨',
    title: 'Design',
    text: 'Visuais fortes, consistentes e impossíveis de confundir com qualquer outro.',
  },
  {
    icon: '📈',
    title: 'Crescimento',
    text: 'Experiências digitais que aproximam pessoas e movimentam negócios.',
  },
];
</script>

<template>
  <header class="header">
    <div class="container navigation">
      <a class="brand" href="#" aria-label="Pulse — página inicial">
        <span class="brand-mark">✦</span>
        <span>PULSE<span class="brand-dot">.</span></span>
      </a>

      <nav aria-label="Menu principal">
        <a href="#servicos">Serviços</a>
        <a href="#contato">Contato</a>
      </nav>

      <a class="button button-small" href="#contato">Vamos conversar</a>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="container hero-grid">
        <div class="hero-copy">
          <span class="eyebrow">Design que não passa despercebido</span>
          <h1>Sua ideia merece <em>acontecer.</em></h1>
          <p>
            Criamos identidades e experiências digitais com atitude para marcas
            que nasceram para ocupar espaço.
          </p>

          <div class="hero-actions">
            <a class="button" href="#contato">Quero começar</a>
            <a class="text-link" href="#servicos">Conhecer serviços →</a>
          </div>
        </div>

        <div class="dashboard" aria-label="Resumo de resultados">
          <div class="dashboard-top">
            <div>
              <span class="dashboard-label">Impacto da marca</span>
              <strong>+84%</strong>
            </div>
            <span class="status">Em alta</span>
          </div>

          <div class="chart" aria-hidden="true">
            <span style="height: 30%"></span>
            <span style="height: 46%"></span>
            <span style="height: 40%"></span>
            <span style="height: 62%"></span>
            <span style="height: 76%"></span>
            <span style="height: 94%"></span>
          </div>

          <div class="dashboard-stats">
            <div>
              <small>Novas conexões</small>
              <strong>2.4k</strong>
            </div>
            <div>
              <small>Engajamento</small>
              <strong>12,6%</strong>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="servicos" class="services">
      <div class="container">
        <div class="section-heading">
          <span class="eyebrow">Nosso trabalho</span>
          <h2>Estratégia com uma boa dose de personalidade.</h2>
        </div>

        <div class="service-grid">
          <article v-for="service in services" :key="service.title" class="card">
            <span class="card-icon">{{ service.icon }}</span>
            <h3>{{ service.title }}</h3>
            <p>{{ service.text }}</p>
          </article>
        </div>
      </div>
    </section>

    <section id="contato" class="contact">
      <div class="container contact-box">
        <div>
          <span>Tem uma ideia inquieta?</span>
          <h2>A gente ajuda a colocar ela no mundo.</h2>
        </div>
        <a class="button button-light" href="mailto:oi@pulsestudio.com.br">
          Fale com a gente
        </a>
      </div>
    </section>
  </main>

  <footer class="footer">
    <div class="container footer-content">
      <a class="brand" href="#">
        <span class="brand-mark">✦</span>
        <span>PULSE<span class="brand-dot">.</span></span>
      </a>
      <span>© 2026 Pulse Studio</span>
    </div>
  </footer>
</template>
