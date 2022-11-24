<title>My projects</title>

<script lang="ts">
  import Project from "/src/lib/components/Project.svelte";
</script>

<div class="container">
  <div class="grid-wrapper">
    <Project numProject="Transition" />
    <Project numProject="2" />
    <Project numProject="3" />
    <Project numProject="4" />
    <Project numProject="5" />
    <Project numProject="6" />
  </div>
</div>

<style>
  .container {
    display: flex;
    width: 100%;
    height: 100vh;
    align-items: center;
    justify-content: center;
  }

  .grid-wrapper {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 300px;
  }
</style>