<script>
  //상위 컴포넌트(App.svelte)에서 할당받은 name 이라는 props를 사용하는 법
  //일반적인 변수선언 방법과 비슷하다, let 앞에 export만 적어주면 끝!
  export let name;
</script>

<!-- 보여주는 방법은 일반 변수와 똑같다 -->
<span>{name}</span>
<span>JoY</span>
