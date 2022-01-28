<script>
  // Contact 와 Home 컴포넌트를 임포트해준다.
  import Home from './Component/Home/Home.svelte';
  import Contact from './Component/Contact/Contact.svelte';
  import Header from './Component/Header/Header.svelte';
  //페이지 라우팅을 위해서 svelte-spa-router를 임포트해준다.
  import Router from 'svelte-spa-router';
  //path와 라우팅 할 컴포넌트
  const routes = {
    '/': Home,
    '/Contact1': Contact,
    '/Contact2/:test': Contact,
  };
</script>

<main>
  <!-- routes 객체를 라우팅 -->
  <Header />
  <Router {routes} />
</main>
