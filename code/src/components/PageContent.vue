<template>
    <section class="content">

        <h2 class="content">{{ title }}</h2>

        <p id="summary">{{ description }}</p>


        <a target="_blank" :href="material" id="material">Clique para acessar o material recomendado</a>

        <input @click="callRenderContent(sector,back)" type="button" value="VOLTAR" id="back">
        <input @click="callRenderContent(sector,next)" type="button" value="PRÓXIMO" id="next">

    </section>
</template>

<script>
    export default {
        name: 'PageContent',
        props:{
            title:String,
            description:String,
            material:String,
            next:String,
            back:String,
            sector:String,
            functionRenderContent:Function
        },
        methods:{
            callRenderContent(sector,content){
                this.functionRenderContent(sector,content)
            }
        }
    }
</script>

<style scoped>
    section.content{
        text-align: center;
    }

    p#summary{
        margin: auto;
        margin-top: 5vh;
        margin-bottom: 13vh;
        width: 75vw;
        font-size: 24px;
        font-weight: 300;
        text-align: left;
    }


    a#material{
        text-align: center;
        font-weight: 300;
        text-decoration: underline;
        cursor: pointer;
        color: black;
    }

    input{
        margin-top: 3vh;
        padding: 5px;
        width: 85vw;
        border: 0px;
        color: var(--color-off-button);
        background-color: var(--div-decoration);
        cursor: pointer;
    }

    @media (min-width:1024px) {
        h2.content{
            margin-top: 4vh;
        }

        a#material{
            margin-top: 15vh;
            font-size: 22px;
            width: 100vw;
            max-width: 100%;
            text-align: center;
        }

        input{
            margin-top: 15vh;
            width: 75vw;
        }

        input#next{
            margin-top: 2vh;
        }
    }

</style>