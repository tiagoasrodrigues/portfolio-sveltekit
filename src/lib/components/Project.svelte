<script>
  import { fade } from 'svelte/transition';
  import { elasticOut } from 'svelte/easing';

  export let visible = false;

  function spin(node, { duration }) {
    return {
      duration,
      css: t => {
        const eased = elasticOut(t);

        return `
					transform: scale(${eased}) rotate(${eased * 1080}deg);
					color: hsl(
						${~~(t * 360)},
						${Math.min(100, 1000 - 1000 * t)}%,
						${Math.min(50, 500 - 500 * t)}%
					);`
      }
    };
  }
  export let numProject = "";
</script>

<div class="container">
  <label>
    <div class="project-container">
      <input type="checkbox" bind:checked={visible} placeholder="Ola">
      Project {numProject}

      {#if visible}
      <div class="centered" in:spin="{{duration: 8000}}" out:fade>
        <span>transitions!</span>
      </div>
      {/if}
    </div>
  </label>
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

  .project-container:hover {
    background-color: var(--blue-600);
    color: var(--background);
  }

  .centered {
    position: absolute;
    left: 50%;
    top: 52%;
    transform: translate(-50%, -50%);
  }

  span {
    position: absolute;
    transform: translate(-50%, -50%);
    font-size: 2em;
  }

  label {
    color: var(--background);
    font-size: 36px;
  }

  input {
    display: none;
  }
</style>