# Tutorial: criando a página da Pulse com Vue

Esta branch é somente um guia. Ela não contém o projeto iniciado, arquivos de configuração, dependências ou código da página. O objetivo é explicar como construir a landing page da Pulse do zero.

## Pré-requisitos

- Node.js em versão LTS
- Editor de código, como VS Code
- Conhecimentos básicos de HTML e CSS

## 1. Criar o projeto

```bash
npm create vite@latest pulse -- --template vue
cd pulse
npm install
npm run dev
```

O Vite cria a estrutura inicial e inicia um servidor local. A URL exibida no terminal abre a aplicação no navegador.

## 2. Entender a estrutura

- `index.html`: documento HTML inicial.
- `src/main.js`: ponto de entrada que monta o Vue.
- `src/App.vue`: componente principal.
- `package.json`: scripts e dependências.

Para este exercício, a maior parte do trabalho ficará em `App.vue` e no arquivo de estilos.

## 3. Planejar a página

Divida a interface em blocos:

1. `header`: marca Pulse, navegação e botão de contato.
2. Hero: título, texto, ações e painel visual.
3. Serviços: cards de estratégia, design e crescimento.
4. Contato: chamada final para conversar.
5. `footer`: marca e informações finais.

Prefira elementos semânticos. Eles melhoram acessibilidade, SEO e a organização do código.

## 4. Criar os dados no Vue

No bloco `<script setup>` de `App.vue`, defina os serviços:

```vue
<script setup>
const services = [
  { title: 'Estratégia', text: 'Clareza para sua marca.' },
  { title: 'Design', text: 'Visuais fortes e consistentes.' },
  { title: 'Crescimento', text: 'Experiências que aproximam pessoas.' },
]
</script>
```

O `<script setup>` disponibiliza os dados diretamente no template.

## 5. Montar o template

Use `v-for` para não repetir manualmente o HTML dos cards:

```vue
<section id="servicos" class="services">
  <div class="container">
    <span class="eyebrow">Nosso trabalho</span>
    <h2>Estratégia com personalidade.</h2>
    <div class="service-grid">
      <article v-for="service in services"
               :key="service.title"
               class="card">
        <h3>{{ service.title }}</h3>
        <p>{{ service.text }}</p>
      </article>
    </div>
  </div>
</section>
```

Use interpolação (`{{ valor }}`) para exibir dados do JavaScript. Organize o hero com um título, uma descrição, um botão principal e um link secundário.

## 6. Organizar o CSS

Comece por tokens visuais e um container reutilizável:

```css
:root {
  --ink: #17151f;
  --muted: #6f6a7a;
  --accent: #ff5c35;
  --cream: #fff8f1;
  --radius: 1.25rem;
}

* { box-sizing: border-box; }
body { margin: 0; color: var(--ink); background: var(--cream); }
.container {
  width: min(1120px, calc(100% - 3rem));
  margin-inline: auto;
}
```

Use Grid para o hero e para os cards:

```css
.hero-grid, .service-grid {
  display: grid;
  gap: 2rem;
}
.hero-grid {
  grid-template-columns: 1.1fr 0.9fr;
  align-items: center;
}
.service-grid { grid-template-columns: repeat(3, 1fr); }
```

Crie classes reutilizáveis para botões e cards. Inclua estados `:hover` e `:focus-visible`; o foco deve permanecer visível para navegação por teclado.

## 7. Tornar responsivo

Em telas menores, empilhe as colunas e reduza os espaçamentos:

```css
@media (max-width: 700px) {
  .container { width: min(100% - 2rem, 1120px); }
  .hero-grid, .service-grid { grid-template-columns: 1fr; }
  .navigation nav { display: none; }
  h1 { font-size: clamp(2.5rem, 12vw, 4.5rem); }
}
```

Teste em diferentes larguras e confira se não há rolagem horizontal.

## 8. Acessibilidade

- Use um único `h1` e uma hierarquia correta de títulos.
- Dê nomes claros aos links e botões.
- Use `alt` em imagens e `aria-label` quando necessário.
- Garanta contraste adequado entre texto e fundo.
- Teste a navegação usando a tecla Tab.

## 9. Validar

```bash
npm run dev
npm run build
```

Revise o resultado visual, teste os links e confirme que o build termina sem erros.

## Sobre esta branch

Esta branch contém apenas este README. Execute os comandos da seção 1 em uma nova pasta para criar o projeto. A branch `main` contém a implementação pronta da página Pulse para comparação após o exercício.
