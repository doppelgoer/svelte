<script>
let visible = false;
let visible1 = false;
function typewriter(node, { speed = 1 }) {
		const valid = (
			node.childNodes.length === 1 &&
			node.childNodes[0].nodeType === Node.TEXT_NODE
		);

		if (!valid) {
			throw new Error(`This transition only works on elements with a single text node child`);
		}

		const text = node.textContent;
		const duration = text.length / (speed * 0.01);

		return {
			duration,
			tick: t => {
				const i = ~~(text.length * t);
				node.textContent = text.slice(0, i);
			}
		};
	}
    setInterval(()=>{
        visible1 = !visible1;
    }, 5000)
    setTimeout(() => {
        visible = true;
    }, 2000);
</script>


<div class="main-content-container">
    <div class="header-container">
        <div class="header-logo">PORTFOLIO</div>
        <!-- <div class="header-logo">PORTFOLIO</div> -->
        <div class="header-menus">
            <div class='header-menu'>뭐하징?</div>
            <div class='header-menu'>SKILL</div>
            <div class='header-menu'>CONTACT</div>
            <div class='header-menu'>ABOUT</div>
        </div>
    </div>
    <div class="white-line"></div>
    <div class="main-content-container">
        <div class="main-content-wrapper"></div>
        <div class="txt-wrapper">
            <div class="typing-warpper">
                <!-- <h1 class="typing-txt" >
                    WLCOME TO MY PORTFOLIO
                </h1> -->
                {#if visible}
                    {#if visible1}
                    <span class="typing-txt1" transition:typewriter>
                        WELCOME TO MY PORTFOLIO
                    </span>
                    {/if}
                {/if}
                <span class="typing-cursor">|</span>
            </div>
        </div>
    </div>
</div>


<style>
    .main-content-container{
        align-items: center;
        justify-content: center;
        width: 100%;
        height: calc(100% - 65px);
    }
    .main-content-wrapper{
        width: 100%;
        height: 80vh;
    }
    .txt-wrapper{
        width: 100%;
        /* height: calc(100% - 65px); */
        display: flex;
        align-items: flex-end;
        justify-content: flex-start;

    }
    .typing-txt1 {
        font-size: 50px;
        text-decoration:underline
    }
    .typing-cursor {
        font-size: 50px;
        animation: typing-cursor 1s infinite;
        
    }


    .main-content-container{
        /* background-color: blueviolet; */
        width: 100%;
        height: 100%;
        position: absolute;
        /* display: grid;
        grid-template-rows: auto; */
        /* display: grid; */
        /* grid-template-columns: repeat(10, 1fr);
        grid-template-rows: repeat(10, 1fr); */
        /* background-color: blueviolet; */
    }
    .header-container{
        width: 100%;
        height: 65px;
        display: grid;
        grid-template-columns: repeat(12, 1fr);
        grid-template-rows: 65px;
        align-items: center;
        color: white;
    }
    .header-logo:nth-child(1){
        /* grid-column: span 1; */
        /* grid-row: span 6; */
        /* background-color: white; */
        /* place-items: center;
        text-align: start; */
        /* align-items: center;
        justify-content: center;
        align-content: center;
        justify-items: center; */
        padding: 25px;
        color: white;
    }
    .header-menus{
        margin-left: 50%;
        width: 50%;
        height: 100%;
        grid-column: span 11;
        display: grid;
        align-items: center;
        /* justify-content: end; */
        grid-template-columns: repeat(6, 1fr);
    }
    /* .header-menus:nth-child(1){
        grid-column: span 11;
    } */
    /* .header-container:nth-child(11){
        background-color: white;
    } */
    .white-line{
        width: 98%;
        /* align-items: center;
        justify-content: center; */
        position: absolute;
        left:50%;
        right:50%;
        transform: translate(-50%,-50%);
        height: 2px;
        background-color: rgb(209, 209, 209);
    }
    .typing-warpper{
        color: white;
    }
    .typing-txt{

        font-family: consolas;
        /* font-size: 15px; */
        min-width:11px;
        white-space: nowrap;
        margin: 0;
        position: fixed;
        color: transparent;
        /* top:50%;
        left:50%;
        transform: translate(-50%, -50%); */
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .typing-txt::before{
        font-family: consolas;
        content: 'WELCOME TO MY PORTFOLIO';
        position: absolute;
        
        top: 0;
        left: 0;
        width: 110%;
        height: 100%;
        color: white;
        overflow: hidden;
        border-right: 1px solid black;
        animation: typing 8s steps(28) infinite;
    }
    @keyframes typing{
        0%{
            width: 0%;
        }
        15%{
            width: 0%;
        }
        40%{
            width: 105%;
        }
        60%{
            width: 105%;
        }
        85%{
            width: 0%;
        }
        100%{
            width: 0%;
        }
    }
    @keyframes typing-cursor{
        50%{
            opacity: 0;
        }
    }

</style>