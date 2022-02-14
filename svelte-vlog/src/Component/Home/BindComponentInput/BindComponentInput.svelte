<!-- <script>
  import BindInput from './BindInput.svelte';
  let inputTxt = '';
</script>

<div class="input-binding-container">
  {#if inputTxt}
    <div>
      <span>{inputTxt}</span>
    </div>
  {:else}
    <div>
      <span>내용이 없어요..</span>
    </div>
  {/if}
  <div>
    <BindInput bind:inputValue={inputTxt} />
  </div>
</div>
<div style="background-color : black; color : white">100</div>

<style>
  .input-binding-container {
    display: grid;
  }
</style> -->
<script>
  import BindInput from './BindInput.svelte';

  let name = 'JoY';
</script>

<div>
  {name}
  <!-- name 앞에 "bind:" 만 적어넣으면 끝 -->
  <BindInput bind:name />
</div>
