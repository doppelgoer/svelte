<!-- <script>
  export let inputValue;
</script>

<input type="text" bind:value={inputValue} /> -->
<script>
  export let name;
  function changeName() {
    name = 'DoP';
    console.log(name);
  }
</script>

<button on:click={changeName}>이름 변경</button>
