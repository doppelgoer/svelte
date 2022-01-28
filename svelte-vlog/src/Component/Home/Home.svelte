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
<!-- number를 화면에 보여준다. -->
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
  <div class="number-container">
    <h2>sum : {sum}</h2>
  </div>
</div>

<style>
  .numbers-container {
    display: flex;
  }
  .number-container {
    margin: 0 20px 0 20px;
  }
</style>
