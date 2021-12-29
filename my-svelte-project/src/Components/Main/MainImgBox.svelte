<script>
	// let name = '1'
    import SmallImgBox from "./SmallImgBox.svelte";
    import MainContent from "./MainContent.svelte"
    let imgs = [
        {src:`/image/mainImg1.jpg`},
        {src:`/image/mainImg2.jpg`},
        {src:`/image/mainImg3.jpg`},
        {src:`/image/mainImg4.jpg`},
        {src:`/image/mainImg5.jpg`},
    ]
</script>


    <div class="main-img-container">
        {#each imgs as {src}}
        <SmallImgBox imgSrc={src}></SmallImgBox>
        {/each}
        <MainContent></MainContent>
        <!-- <button class="testBtn">ddddddddddddd</button> -->
    </div>
    <!-- <div class="main-img-container">
        {#each imgs as {src}}
        <SmallImgBox imgSrc={src}></SmallImgBox>
        {/each}
        <button class="testBtn">ddddddddddddd</button>
    </div> -->
	<!-- <h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p> -->

<style>
    .main-img-container{
        position: relative;
        /* background-color: black; */
        width: 100%;
        height: 100vh;
        display: grid;
        grid-template-columns: repeat(5, 1fr);
        grid-template-rows: 100%;
    }
    .testBtn{
     position: absolute;
    }

	
</style>