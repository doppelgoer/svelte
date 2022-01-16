<script>
  //MyName 컴포넌트를 import 해 오자.
  import MyName from './Component/MyName.svelte';
</script>

<main>
  <!-- MyName 컴포넌트에 name이라는 props를 전달  -->
  <h1>Hello <MyName name="JoY" />!</h1>
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
