<script>
  export let numProject = ""
</script>

<div class="container">
  <div class="project-container">
    <h1>Project {numProject}</h1>
  </div>
</div>

<style>
  .container {
    background-color: var(--background);
    background-image: linear-gradient(180deg, var(--white) 20%, var(--blue-400) 75%);
    height: 200px;
    width: 400px;
    border: 2px solid var(--blue-600);
    border-radius: 16px;
    margin: 26px;
  }

  .project-container {
    display: flex;
    height: 100%;
    width: 100%;
    align-items: center;
    justify-content: center;
    border-radius: 16px;
    transition: 0.5s;
  }

  .project-container h1 {
    text-align: center;
    color: var(--background);
  }

  .project-container:hover {
    background-color: var(--blue-600);
    color: var(--background);
  }
</style>