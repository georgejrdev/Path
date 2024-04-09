<template>
    <header>
        <nav>
            <p>path</p>
        </nav>

        <div id="header-content">
            <h1>O INICIO DA SUA CARREIRA</h1>
            <div id="header-div-decoration"></div>
        </div>
    </header>
</template>

<script>
    export default {
        name: 'PageHeader',
    }
</script>

<style scoped>
    header{
        width: 100vw;
        max-width: 100%;
        height: 100vh;
        display: flex;
        flex-direction: column;
    }


    nav{
        width: 100vw;
        max-width: 100%;
        background-color: var(--background-navbar);
        display: flex;
        align-items: center;
        max-height: 25vh;
    }


    nav > p{
        color: var(--color-navbar);
        font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        font-size: 19px;
        margin-left: 2vw;
        padding-top: 2.5vh;
        padding-bottom: 2.5vh;
    }


    div#header-content{
        flex: 1;
        align-items: center;
        justify-content: center;
    }


    h1{
        margin-top: 10vh;
        text-align: center;
        font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans';
        font-weight: lighter;
        letter-spacing: 3px;
        font-size: 68px;
    }


    div#header-div-decoration{
        margin: auto;
        margin-top: 9vh;
        background-color: var(--div-decoration);
        width: 65vw;
        height: 3vh;
    }



    @media (min-width:1024px) {
        header{
            display: flex;
            flex-direction: column;
        }
        
        
        nav{
            display: flex;
            align-items: center;
        }
        
        
        div#header-content{
            display: flex;
            flex-direction: column;
                align-items: center;
            justify-content: center;
        }

        h1{
            margin: 0;
            margin: auto;
            width: 60vw;
        }
    }
</style>
