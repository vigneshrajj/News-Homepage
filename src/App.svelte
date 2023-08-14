<script lang="ts">
    import Header from './lib/Header.svelte';
    import Hero from './lib/Hero.svelte';
    import New from './lib/New.svelte';
    import TopBlogs from './lib/TopBlogs.svelte';
</script>

<div class="container">
  <Header />
  <div class="main-container">
    <Hero />
    <New />
  </div>
  <TopBlogs />
</div>

<style>
  :global(:root) {
    --mobile: 375px;
    --desktop: 1440px;
    
    --primary-orange: hsl(35, 77%, 62%);
    --primary-red: hsl(5, 85%, 63%);
    
    --white: hsl(36, 100%, 99%);
    --gray: hsl(233, 8%, 79%);
    --dark-gray: hsl(236, 13%, 42%);
    --black: hsl(240, 100%, 5%);
  }

  .main-container {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 1.5rem;
  }

  @media screen and (max-width: 576px) {
    .main-container {
      display: block;
    }
  }
</style>
