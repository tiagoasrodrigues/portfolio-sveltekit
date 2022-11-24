<title>Contate-me</title>

<script lang="ts">

</script>

<div class="container">
  <h1>Preencha o formulário abaixo que retornarei em breve :)</h1>

  <form>
    <input name="name" type="text" placeholder="Nome" autocapitalize="words">
    <input name="email" type="email" placeholder="E-mail">
    <br>
    <textarea name="message" type="text" placeholder="Mensagem"  maxlength="420"> </textarea>
    <br>
    <button>Enviar</button>
  </form>
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100vh;
    align-items: center;
    justify-content: center;
  }

  h1 {
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  }

  form {
    padding-top: 96px;
  }

  form input {
    background-color: var(--dark-blue-900);
    color: var(--white);
    font-size: 16px;
    height: 36px;
    width: 350px;
    padding-left: 10px;
    margin-bottom: 16px;
    border: 1.5px solid var(--blue-600);
    border-radius: 8px;
  }

  form textarea {
    background-color: var(--dark-blue-900);
    color: var(--white);
    font-size: 16px;
    height: 200px;
    width: 100%;
    padding: 26px;
    padding-bottom: 150px;
    border: 1.5px solid var(--blue-600);
    border-radius: 8px;
    margin-bottom: 10px;
  }

  ::placeholder {
    color: var(--white);
  }

  input:focus-visible {
    outline: 1px solid var(--blue-400);
  }

  button {
    height: 28px;
    width: 100px;
    font-weight: bold;
    background-color: var(--blue-600);
    color: var(--white);
    border: 1px solid var(--white);
    border-radius: 3px;
    transition: 0.3s;
  }

  button:hover {
    background-color: var(--blue-400);
    color: var(--background);
  }
</style>