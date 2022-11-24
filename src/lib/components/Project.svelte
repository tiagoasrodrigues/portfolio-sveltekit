<script>
  import { fade } from 'svelte/transition';
  import { elasticOut } from 'svelte/easing';

  export let numProject = "";
  export let visible = false;

  let active = false;

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
</script>

<button class:active={active} on:click="{() => active = !active}">
  <label>
    <div class="label-merge">
      <input type="checkbox" bind:checked={visible} class:active={active} on:click="{() => active = !active}">
      Project {numProject}

      {#if visible}
      <div class="centered" in:spin="{{duration: 8000}}" out:fade>
        <span>Project_{numProject}</span>
      </div>
      {/if}
    </div>
  </label>
</button>

<style>
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

  .active {
    background-color: var(--blue-600);
    color: var(--white);
    border: 2px solid var(--white);
    transition: 0.3s;
  }

  button {
    background-color: var(--blue-400);
    color: var(--background);
    font-size: 36px;
    transition: 0.5s;
    height: 200px;
    width: 400px;
    border: 2px solid var(--blue-600);
    border-radius: 16px;
    margin: 26px;
  }

  button:hover {
    background-color: var(--blue-600);
    color: var(--white);
    border: 2px solid var(--white);
  }

  label {
    background-color: red;
    height: 30px;
    width: 30px;
  }

  .label-merge {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 200px;
    border-radius: 16px;
  }

  input {
    display: none;
  }
</style>