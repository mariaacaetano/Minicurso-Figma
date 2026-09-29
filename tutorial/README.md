# Tutorial: criando a página Pulse com Vue

## 1. Criar o projeto

```bash
npm create vite@latest pulse -- --template vue
cd pulse
npm install
npm run dev
```

O Vite cria a estrutura inicial e inicia um servidor local para acompanhar as alterações.

## 2. Planejar a página

Divida a landing page em seções semânticas: `header`, hero, serviços, contato e `footer`. Essa divisão facilita a leitura do HTML, a estilização e a acessibilidade.

## 3. Construir o template Vue

No `App.vue`, use `<template>` para a marcação. Para conteúdos repetidos, mantenha os dados no `<script setup>` e renderize-os com `v-for`:

```vue
<script setup>
const services = [
  { title: 'Estratégia', text: 'Clareza para sua marca.' },
  { title: 'Design', text: 'Visuais consistentes.' },
]
</script>

<template>
  <article v-for="service in services" :key="service.title">
    <h3>{{ service.title }}</h3>
    <p>{{ service.text }}</p>
  </article>
</template>
```

## 4. Estilizar com CSS

Comece por cores, tipografia e espaçamento. Depois use Flexbox ou Grid para o layout. Crie classes reutilizáveis para container, botões e cards, evitando estilos inline desnecessários.

## 5. Tornar responsivo

Adicione uma media query para telas menores, reduzindo títulos e transformando grids em uma coluna:

```css
@media (max-width: 700px) {
  .hero-grid,
  .service-grid {
    grid-template-columns: 1fr;
  }
}
```

## 6. Validar e publicar

```bash
npm run build
```

Confira links, contraste, foco de teclado e visual em diferentes larguras antes de publicar.
