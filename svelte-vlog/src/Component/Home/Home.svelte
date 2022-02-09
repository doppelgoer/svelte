<script>
  import ColorBox from './ColorBox.svelte';
  // import axios from 'https://unpkg.com/axios/dist/axios.min.js';
  import axios from 'axios';
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
  let exchangeDate = getExchange();
  function test() {
    getExchange();
  }
  async function getExchange() {
    // const res = await fetch(`http://api.manana.kr/exchange/rate/KRW/JPY,USD,KRW.json`);
    return new Promise(async function (resolve, reject) {
      let data;
      try {
        data = await axios({
          //token
          method: 'GET',
          url: `https://cors-anywhere.herokuapp.com/http://api.manana.kr/exchange/rate/KRW/JPY.json`,
          // params: _data,
        });
        // console.log(dataFromServer);
        console.log(111, data);
        resolve(data);
      } catch (e) {
        reject(e);
      }
    });
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
<div class="colors-container">
  <div>
    <!-- #each 객체 as 객체의 아이템, 인덱스 -->
    {#each colors as color, index (color.color)}
      <ColorBox color={color.color} />
      <!-- else 블록은 colors에 요소가 없을 때 실행되는 부분 -->
    {:else}
      color가 없습니다!
    {/each}
  </div>
</div>
<button on:click={eachBtn}>버튼</button>
<!-- <div>
  {#each colors as color (color.num)}
    <ColorBox color={color.color} number={color.num} test={true} />
    <div />
  {:else}
    color가 없어요!
  {/each}
</div> -->

<!-- {:else}
    color가 없어요! -->

<button on:click={test}>환율 정보!</button>

{#await exchangeDate}
  <p>...waiting</p>
{:then number1}
  <p>The number is {number1}</p>
{:catch e}
  <p style="color: red">{e}</p>
{/await}

<!-- http://api.manana.kr/exchange/rate/KRW/JPY,USD,KRW.json -->
<style>
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
