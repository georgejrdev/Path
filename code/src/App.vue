<template>
 <PageHeader />

  <main>
    <PageSelection :functionRenderContent="renderContent" />
    
    <PageContent v-if="showContent" :functionRenderContent="renderContent" :sector="sector" :title="title" :description="description" :material="material" :next="next" :back="back"/>
  </main>

 <PageMore />

</template>


<script>

  import { contents } from './content.js'
  import PageHeader from './components/PageHeader.vue'
  import PageSelection from './components/PageSelection.vue'
  import PageContent from './components/PageContent.vue'
  import PageMore from './components/PageMore.vue'

  export default {
    name: 'App',
    components: {
      PageHeader,
      PageSelection,
      PageContent,
      PageMore
    },
    data(){
      return{
        showContent:false,
        title:'',
        description:'',
        material:'',
        next:'',
        back:'',
        sector:'',
        contents:contents,
      }
    },
    methods:{
      renderContent(sector,content){
        this.changeStateIndicator(sector)
        this.showContent = true
        if (content == 'exit'){
          document.documentElement.style.setProperty('--background-backend','#4D8EB2')
          document.documentElement.style.setProperty('--background-frontend','#D66B1E')
          document.documentElement.style.setProperty('--background-fullstack','#A54646')
          document.documentElement.style.setProperty('--background-devops','#249282')
          this.showContent = false
          this.title = ''
          this.description =''
          this.material = ''
          this.next =''
          this.back = ''
          this.sector = ''

        } else{
          const item = this.contents[sector][content]
          this.sector = sector
          
          if (item) {
            this.title = item.titulo
            this.description = item.descricao
            this.material = item.material
            this.next = item.proximo
            this.back = item.voltar
            
          }else {
            this.showContent = false
          }
        }
      },

      changeStateIndicator(sector){
        document.documentElement.style.setProperty('--background-backend','#454545')
        document.documentElement.style.setProperty('--background-frontend','#454545')
        document.documentElement.style.setProperty('--background-fullstack','#454545')
        document.documentElement.style.setProperty('--background-devops','#454545')

        switch (sector){
          
          case 'backend':
            document.documentElement.style.setProperty('--background-backend','#4D8EB2')
            break

          case 'frontend':
            document.documentElement.style.setProperty('--background-frontend','#D66B1E')
            break

          case 'fullstack':
            document.documentElement.style.setProperty('--background-fullstack','#A54646')
            break
          case 'devops':
            document.documentElement.style.setProperty('--background-devops','#249282')
            break
        }
      }
    }
  }
</script>

<style>
  :root{
      --background-body: #FBFBFB;
      --background-navbar: #000000;
      --color-navbar: #FFFFFF;
      --color-title: #000000;
      --color-p: #000000;
      --div-decoration: #D9D9D9;
      --background-backend: #4D8EB2;
      --background-frontend: #D66B1E;
      --background-fullstack: #A54646;
      --background-devops: #249782;
      --color-button: #FFFFFF;
      --background-off-button: #8E8E8E;
      --color-off-button: #323232;
      --background-pix: #999999;
      --background-paypal: #1E4159;
  }

  *{
      margin: 0;
      padding: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  h2{
      text-align: center;
      font-size: 45px;
      font-weight: lighter;
      letter-spacing: 3px;
      margin-top: 3vh;
  }

  body{
      background-color: var(--background-body);
  } 

  a{
      color: black;
  }
</style>
