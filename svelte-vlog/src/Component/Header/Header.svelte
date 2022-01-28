<script>
  import IsLoggedIn from './IsLoggedIn.svelte';
</script>

<div class="header-container">
  <nav>
    <a href="#/">Home</a>
    <a href="#/Contact1">Contact1</a>
    <a href="#/Contact2/1234">Contact2</a>
  </nav>
  <IsLoggedIn />
</div>

<style>
  a {
    text-decoration: none !important;
  }
  .header-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>
