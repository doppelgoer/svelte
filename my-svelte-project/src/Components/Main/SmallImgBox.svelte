<script>
export let imgSrc;
</script>


<div class="small-img-box" >
    <!-- svelte-ignore a11y-missing-attribute -->
    <img  src = {imgSrc} >
</div>


<style>
    .small-img-box{
        /* position: absolute; */
        width: 100%;
        height: 100%;
        overflow: hidden;
    }
    @keyframes imgMove{

        0%{
            transform: translateX(20vw);
        }
        /* 50%{
            transform: translateX(10vw);

        } */
        100%{
            transform: translateX(0vw);
        }
    }
    img{
        animation-name: imgMove;
  animation-duration: 1s;
        width: 100%;
        height: 100%;
        overflow: hidden;
    }
</style>