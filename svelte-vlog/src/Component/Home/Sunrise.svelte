<script>
  import axios from 'axios';
  //시작 날짜를 1일로 한다.
  let numberForSunrise = 1;
  let sunriseDate = 1;
  // input 태그에서 바인딩 된 sunriseDate가 31보다 클 경우
  // sunriseDate 를 31로 변경한다.
  $: if (sunriseDate > 31) {
    sunriseDate = 31;
  } //sunriseDate가 없을경우 sunriseDate를 1로 변경한다.
  else if (!sunriseDate) {
    sunriseDate = 1;
  }
  let changedSunrise = getSunrise();
  async function clickToGetSunrise() {
    console.log(2);
    changedSunrise = getSunrise();
  }
  function getSunrise() {
    return new Promise(async function (resolve, reject) {
      let sunriseData;
      try {
        sunriseData = await axios({
          method: 'GET',
          //input태그에 적은 날짜를 url에 넣음.
          url: `http://api.sunrise-sunset.org/json?lat=36.7201600&lng=-4.4203400&date=2022-01-${sunriseDate}`,
        });
        //텍스트에 보일 날짜를 input태그에 적은 날짜로 변경.
        numberForSunrise = sunriseDate;
        //api호출 후 받아온 객체에서 일출시간을 리턴
        resolve(sunriseData.data.results.sunrise);
      } catch (e) {
        reject(e);
      }
    });
  }
</script>

<div>
  <input type="number" bind:value={sunriseDate} />
  {#await changedSunrise}
    <p>...기다리는중~</p>
  {:then sunriseTime}
    <p>2022년 1월 {numberForSunrise}일의 일출시간은 {sunriseTime}</p>
  {:catch e}
    <p style="color: red">{e}</p>
  {/await}
  <!-- 프로미스객체를 리턴하는 getSunrise를 실행하는 함수 -->
  <button on:click={clickToGetSunrise}>일출 정보!</button>
</div>
