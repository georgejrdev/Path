<template>
    <section class="selection">
        <h2 class="selection">APENAS CLIQUE</h2>

        <div id="container">
            <div @click="callRenderContent('backend','estruturaDeDados')" class="box" id="BackEnd">
                <p class="selection">BackEnd</p>
            </div>


            <div @click="callRenderContent('frontend','html')" class="box" id="FrontEnd">
                <p class="selection">FrontEnd</p>
            </div>

            <div @click="callRenderContent('fullstack','b')" class="box" id="FullStack">
                <p class="selection">FullStack</p>
            </div>


            <div @click="callRenderContent('devops','c')" class="box" id="Devops">
                <p class="selection">Devops</p>  
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'PageSelection',
        props:{
            functionRenderContent: Function
        },
        methods:{
            callRenderContent(sector,content){
                this.functionRenderContent(sector,content)
            }
        }
    }
</script>

<style scoped>
    section.selection{
        margin: auto;
        width: 90vw;
        height: 100vh;
    }

    div#container{
        margin-top: 5vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .box{
        margin: 10px;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 60vw;
        height: 15vh;
        color: var(--color-button);
        cursor: pointer;
    }

    #BackEnd{
        background-color: var(--background-backend);
    }

    #FrontEnd{
        background-color: var(--background-frontend);
    }

    #FullStack{
        background-color: var(--background-fullstack);
    }

    #Devops{
        background-color: var(--background-devops);
    }

    p.selection{
        font-size: 28px;
        font-weight: bolder;
    }

    @media (min-width:1024px) {

        section.selection{
            height: 75vh;
        }

        h2.selection{
            margin-top: 15vh;
        }
        
        div#container{
            margin-top: 20vh;
            flex-direction: row;
        }
    }
</style>
