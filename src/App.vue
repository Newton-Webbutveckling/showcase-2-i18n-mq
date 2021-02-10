<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <button @click="$i18n.locale = 'en'">English</button>
    <button @click="$i18n.locale = 'sv'">Svenska</button>
    <select v-model="$i18n.locale">
      <option v-for="lang in languages" :value="lang.localeKey" :key="lang.localeKey">{{lang.fullText}}</option>
    </select>
    <p> {{ $t('message') }} </p>

    <a href="#">{{$t('home')}}</a>
    <a href="#">{{$t('about')}}</a>
    <a href="#">{{$t('contact')}}</a>


    <section :class="$mq">
      <article>Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque corporis officia architecto eveniet velit totam at impedit. Qui, reprehenderit incidunt! Recusandae facilis reprehenderit suscipit voluptas officia saepe molestias nihil consectetur?</article>
      <article>Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque corporis officia architecto eveniet velit totam at impedit. Qui, reprehenderit incidunt! Recusandae facilis reprehenderit suscipit voluptas officia saepe molestias nihil consectetur?</article>
      <article>Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque corporis officia architecto eveniet velit totam at impedit. Qui, reprehenderit incidunt! Recusandae facilis reprehenderit suscipit voluptas officia saepe molestias nihil consectetur?</article>
      <article>Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque corporis officia architecto eveniet velit totam at impedit. Qui, reprehenderit incidunt! Recusandae facilis reprehenderit suscipit voluptas officia saepe molestias nihil consectetur?</article>
      <article>Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque corporis officia architecto eveniet velit totam at impedit. Qui, reprehenderit incidunt! Recusandae facilis reprehenderit suscipit voluptas officia saepe molestias nihil consectetur?</article>
    </section>
    <p>{{$mq}}</p>
    
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){return {
    languages: [{
      localeKey: 'sv',
      fullText: 'Svenska'
    },{
      localeKey:'en',
      fullText: 'English'
    }]
  }},
  components: {
  }
}
</script>

<style lang="scss" scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

section{

  article{
    margin: 1rem;
    background-color: hotpink;
    padding: 1rem;
    color: black;
  }



  &.mobile{
    display: flex;
    flex-direction: column;
  }

  &.laptop{
    display: grid;
    grid-template-columns: repeat(2, 1fr);
  }


  &.desktop{
    display: grid;
    grid-template-columns: repeat(4, 1fr);

    article:nth-of-type(2n){
      grid-column: span 2;
    }
  }
}
</style>
