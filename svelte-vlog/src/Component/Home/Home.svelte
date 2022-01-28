<script>
  //number 변수 선언
  let number = 0;
  let number2 = 0;
  $: sum = number + number2;
  //number가 1씩 더해지는 함수 선언
  function plusNumber() {
    number++;
  }
  //number가 1씩 빼지는 함수 선언
  function minusNumber() {
    number--;
  }
  function plusNumber2() {
    number2++;
  }
  //number가 1씩 빼지는 함수 선언
  function minusNumber2() {
    number2--;
  }

  $: if (sum === 10) {
    alert('합은 10입니다.');
  }
</script>

<h1>Home</h1>
<div class="numbers-container">
  <div class="number-container">
    <h2>number : {number}</h2>

    <button on:click={plusNumber}>Plus</button>
    <button on:click={minusNumber}>Minus</button>
  </div>
  <div class="number-container">
    <h2>number2 : {number2}</h2>
    <button on:click={plusNumber2}>Plus</button>
    <button on:click={minusNumber2}>Minus</button>
  </div>
  <!-- 시작은 "3" -->
  {#if sum < 5}
    <div class="number-container">
      <h2>sum : {sum}은 5보다 작습니다</h2>
    </div>
    <!-- 중간은 ":" -->
  {:else if sum >= 5 && sum < 10}
    <div class="number-container">
      <h2>sum : {sum}은 4보다 크고 10보다 작습니다</h2>
    </div>
    <!-- 끝은 "/" -->
  {:else}
    <div class="number-container">
      <h2>sum : {sum}은 9보다 큽니다</h2>
    </div>
  {/if}
</div>

<style>
  .numbers-container {
    display: flex;
  }
  .number-container {
    margin: 0 20px 0 20px;
  }
</style>
