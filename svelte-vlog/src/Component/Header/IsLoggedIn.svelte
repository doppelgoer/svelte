<script>
  let isLoggedIn = false;
  function loginLogout() {
    isLoggedIn = !isLoggedIn;
  }
</script>

{#if !isLoggedIn}
  <h2>로그인을 해주세요.</h2>
  <button on:click={loginLogout}>로그인</button>
{:else}
  <h2>로그인됐습니다.</h2>
  <button on:click={loginLogout}>로그아웃</button>
{/if}
