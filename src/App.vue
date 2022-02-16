<template>
  <div id="app">
    <header>
      <div class="logo">
        <img alt="Vue logo" src="./assets/logo.png">
      </div>
    </header>
      <main>
        <div class="container">
          <div class="section">
            <h2 class="title">buttons</h2>
            <h3 class="title-small">Main buttons</h3>

            <div class="box">
              <AppButton text="save" color="yellow" width="20rem" theme="but-primary"/>
              <AppButton text="primary" color="blue" width="20rem" theme="but-primary"/>
              <AppButton text="tertiary" color="cyan" width="20rem" theme="but-tertiary"/>
              <AppButton text="disabled" color="cyan" width="20rem" theme="but-disabled"/>
            </div>

          </div>
        </div>
      </main>
    <footer></footer>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import AppButton from '@/components/AppButton'

export default {
  data () {
    return {
    }
  },
  name: 'App',
  components: {
    AppButton
  },
  methods: {
  }
}
</script>

<style>
  *,
  ::before,
  ::after {
    margin: 0;
    padding: 0;
    box-sizing: inherit;
  }

  html {
    font-size: 62.5%
  }

 body {
    background-color: #26242A;
    font-family: Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    box-sizing: border-box;
    color: #ffff;
  }
  h1, h2, h3, p {
    margin: 0;
  }

  #app {
    display: grid;
    grid-template-rows: 10vh 70vh 10vh;
    grid-template-columns: 1fr;
    grid-template-areas: "header"
                          "main"
                          "footer"
    ;
  }

  .logo {
    margin: 0 auto;
    width: 260px;
  }

  header {
    background-color: #39363E;
    grid-area: header;
  }

  main {
    grid-area: main;
  }

  footer {
    background-color: #26242A;
    grid-area: footer
  }

  .container {
    width: 80%;
    margin: auto;
    height: 70vh;
  }
  .section {
    padding: 1rem;
  }
  .box {
    margin-top: 2rem;
  }


  .title {
    font-size: 2rem;
    text-transform: uppercase;
    font-weight:  bold;
    padding: 2rem 1rem;
  }
  .title-small {
    font-size: 1.2rem;
    text-transform: uppercase;
    font-weight: normal;
    border-bottom: 1px solid #666666;
    padding: 2rem .5rem 1rem;
  }

  .modal {
    height: 100vh;
    width: 100%;
    background-color: rgba(0, 0, 0, .4);
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;
  }


</style>
