<script>
  //페이지 라우팅을 위해서 svelte-routing을 임포트해준다.
  import {Link} from 'svelte-routing';
</script>

<nav>
  <!-- 네비게이션을 만들고 -->
  <!-- Link to에 path를 적어넣는다. -->
  <Link to="/">Home</Link>
  <Link to="Contact1">Contact1</Link>
  <Link to="Contact2">Contact2</Link>
</nav>
