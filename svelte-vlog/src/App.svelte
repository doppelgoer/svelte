<script>
  // Contact 와 Home 컴포넌트를 임포트해준다.
  import Contact from './Component/Contact/Contact.svelte';
  import Home from './Component/Home/Home.svelte';
  //페이지 라우팅을 위해서 svelte-routing을 임포트해준다.
  import {Router, Link, Route} from 'svelte-routing';
</script>

<!-- 네비게이터 -->
<main>
  <!-- 아직 url은 뭔지 잘 모르겠다 이후에 추가요망. -->
  <Router url="">
    <nav>
      <!-- 네비게이션을 만들고 -->
      <!-- Link to에 path를 적어넣는다. -->
      <Link to="/">Home</Link>
      <Link to="Contact1">Contact1</Link>
      <Link to="Contact2">Contact2</Link>
    </nav>

    <div>
      <!-- 위에서 적은 Link to에 부합하는 path를 적고
      해당 path에 보여줄 컴포넌트를 넣는다 -->
      <Route path="/"><Home /></Route>
      <!-- 컴포넌트를 라우팅 해주는 방법은 아래 두가지가 있다
      둘다 똑같습니다! -->
      <Route path="/Contact1" component={Contact} />
      <Route path="/Contact2"><Contact /></Route>
    </div>
  </Router>
</main>
