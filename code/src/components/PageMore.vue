<template>
    <section>
        <h2 class="more">SOBRE O PROJETO</h2>

        <div id="container">
            <div id="photo"></div>
            
            <div id="credit">
                <p class="credits"><span class="emphasis">Feito por: </span>George Júnior</p>
                <p class="credits"><span class="emphasis">Portfólio: </span><a class="more" target="_blank" href="https://noxusjr.github.io/Portfolio">noxusjr.github.io/Portfolio</a></p>
                <p class="credits"><span class="emphasis">Github: </span><a class="more" target="_blank" href="https://github.com/NoxusJr">github.com/NoxusJr</a></p>
            </div>
        </div>

        <div id="div-decoration"></div>

    </section>
</template>


<script>
    export default {
        name: 'PageMore',
    }
</script>


<style scoped>
    h2.more{
        margin-top:10vh;
    }

    div#photo{
        margin: auto;
        margin-top: 8vh;
        margin-bottom: 5vh;
        width:250px;
        height: 250px;
        background-color: var(--div-decoration);
        border-radius: 100%;
    }

    p.credits{
        margin: auto;
        margin-top: 2px;
        width: 80vw;
        font-size:19px;
    }

    a.more{
        color: black;
    }

    .emphasis{
        font-weight: bolder;
    }

    div#div-decoration{
        margin: auto;
        margin-top: 4vh;
        width: 80vw;
        height: 3vh;
        background-color: var(--div-decoration);
    }


    @media (min-width:1024px) {
        h2.more{
            margin-top: 15vh;
        }

        div#container{
            margin: 0;
            display: flex;
            margin: auto;
            margin-top: 10vh;
            width: 80vw;
            justify-content: space-evenly;
            align-items: center;
        }

        div#credit{
            margin: 0;
            width: auto;

        }

        div#photo{
            margin: 0;
            width: 300px;
            height: 300px;
            
        }

        p.credits{
            margin: 0;
            width: auto;
        }

        div#div-decoration{
            margin-top: 15vh;
            margin-bottom: 5vh;
        }
    }
</style>