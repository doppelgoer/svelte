<script>
  export let color;
  let chagedColor = color;
</script>

<div class="color-container">
  <div style="background-color:{color}">{color}</div>
  <div style="background-color:{chagedColor}">{chagedColor}</div>
</div>

<style>
  .color-container {
    margin: 10px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 50px;
  }
</style>
