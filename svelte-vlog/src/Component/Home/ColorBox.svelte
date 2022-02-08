<script>
  export let color;
  export let number;
  export let test;
  let chagedColor = color;
  $: if (chagedColor) {
    console.log('color', color);
    console.log('chagedColor', chagedColor);
    console.log(number);
    console.log(test);
  }
</script>

<div style="margin: 10px; display: grid; grid-template-columns: 1fr 1fr; grid-gap: 50px">
  <div style="background-color:{color}">{color}</div>
  <div style="background-color:{chagedColor}">{chagedColor}</div>
</div>
