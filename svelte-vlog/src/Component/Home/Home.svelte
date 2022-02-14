<script>
  import ColorBox from './ColorBox.svelte';
  import Sunrise from './Sunrise.svelte';
  ////02-14
  import BindComponentInput from './BindComponentInput/BindComponentInput.svelte';
  ////02-14-1
  import Lifecycle from './Lifecycle/Lifecycle.svelte';
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
  let colors = [
    {num: 1, color: 'pink'},
    {num: 2, color: 'blue'},
    {num: 3, color: 'red'},
    {num: 4, color: 'green'},
    // {num: 9, color: 'purple'},
    {num: 5, color: 'yellow'},
    {num: 7, color: 'grey'},
    {num: 8, color: 'purple'},
  ];
  function eachBtn() {
    colors = colors.slice(1);
  }
</script>

<h1>Home</h1>
<div class="home-container">
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
  <div class="colors-container">
    <div>
      <!-- #each 객체 as 객체의 아이템, 인덱스 -->
      {#each colors as color, index (color.color)}
        <ColorBox color={color.color} />
        <!-- else 블록은 colors에 요소가 없을 때 실행되는 부분 -->
      {:else}
        color가 없습니다!
      {/each}
      <button on:click={eachBtn}>버튼1</button>
    </div>
  </div>
  <Sunrise />
  <!-- 02-14 -->
  <BindComponentInput />
  <!-- 02-14-1 -->
  <Lifecycle />
</div>

<style>
  .home-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }
  .colors-container {
    height: 200px;
    margin: 50px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 50px;
  }

  .numbers-container {
    display: flex;
  }

  .number-container {
    margin: 0 20px 0 20px;
  }
</style>
