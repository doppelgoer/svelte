<script>
  import MyName from './Component/MyName.svelte';
  let name = 'JoY';
  function changeName() {
    if (name === 'JoY') {
      name = 'DoP';
    } else {
      name = 'JoY';
    }
  }
</script>

<main>
  <h1>Hello <MyName {name} />!</h1>
  <!-- 버튼을 만들어 봅시다 -->
  <button on:click={changeName}>바꿔보자!</button>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
