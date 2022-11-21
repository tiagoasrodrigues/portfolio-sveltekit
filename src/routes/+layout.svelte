<script lang="ts">
  import Home from "/src/routes/+page.svelte"
  import Projects from "/src/routes/projects/+page.svelte"
  import Contact from "/src/routes/contact/+page.svelte"
</script>

<nav>
  <ul>
    <li><a href="/">Sobre mim</a></li>
    <li><a href="/projects">Meus projetos</a></li>
    <li><a href="/contact">Contate-me</a></li>
  </ul>
</nav>

<slot>
  <Projects />
  <Home />
  <Contact />
</slot>

<style>
   ul {
    display: flex;
    align-items: center;
    justify-content: space-between;
    list-style-type: none;
    padding: 16px;
  }

  ul a {
    color: var(--white);
    text-decoration: none;
  }

  ul a:hover {
    color: var(--blue);
  }
</style>