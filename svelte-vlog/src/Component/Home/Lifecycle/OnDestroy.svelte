<script>
  import {onMount, onDestroy} from 'svelte';

  onMount(function () {
    console.log('onDestroy에서 마운트 됐어요~!');
  });
  onDestroy(function () {
    console.log('onDestroy에서 마운트 해제됐어요ㅠㅠ');
  });
</script>
