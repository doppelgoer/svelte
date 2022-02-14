<script>
  import {onMount, onDestroy, beforeUpdate, afterUpdate, tick} from 'svelte';
  // let data;
  // beforeUpdate(async () => {
  //   console.log('parent beforeUpdate1111..');
  //   await tick(); // tick : 언제든지 호출가능 + 컴포넌트에 변경사항이 완료가 되었을때 Promise() 반환
  //   console.log('tick()..');
  // });
  // beforeUpdate(function () {
  //   console.log('parent beforeUpdate..');
  // });
  onMount(function () {
    console.log('마운트 됐어요~!');
  });
  // afterUpdate(function () {
  //   console.log('parent afterUpdate..');
  // });
  // onDestroy(function () {
  //   console.log('parent onDestroy..');
  // });
  // console.log('마운트가 더 빠른가?');
</script>
