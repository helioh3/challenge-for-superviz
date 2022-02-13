<template>
  <div id="app">
    <header>
      <div class="logo">
        <img alt="Vue logo" src="./assets/logo.png">
      </div>
    </header>
      <div class="modal" v-show="open">
        <section class="header-modal">
          <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's
            standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it
            to make a type specimen book. It has survived not only five centuries, but also the leap into electronic
          </p>
          <div class="box">
            <button class="but but-primary" @click.prevent="closeModal">Ok</button>
            <button class="but but-secondary" @click.prevent="closeModal">Cancel</button>
          </div>
        </section>
      </div>

      <main>
        <div class="container">
          <div class="section">
            <h2 class="title">buttons</h2>
            <h3 class="title-small">Main buttons</h3>

            <div class="box">
              <button class="but but-primary"
                @click.prevent="showModal"
              >
                primary
              </button>

              <button class="but but-secondary" @click.prevent="showModal">secondary</button>
              <button class="but but-tertiary but-disabled">Disabled</button>
            </div>

            <div class="box">
              <button class="but but-primary">primary</button>
              <button class="but but-secondary">secondary</button>
              <button class="but but-tertiary but-disabled">Disabled</button>
            </div>
          </div>
        </div>
      </main>
    <footer></footer>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  data () {
    return {
      open: false
    }
  },
  name: 'App',
  components: {
    // HelloWorld
  },
  methods: {
    showModal () {
      this.open = !this.open
    },
    closeModal () {
      this.open = false
    }
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
  .but {
    font-size: 1.2rem;
    border: none;
    color: white;
    padding: 12px 40px;
    text-align: center;
    transition-duration: 0.2s;
    text-decoration: none;
    margin: 4px 2px;
    cursor: pointer;
    display: inline-block;
    text-transform: uppercase;
    border-radius: 10px;
    font-weight: bold;
  }
  .but-disabled {
    opacity: 0.5;
    cursor: not-allowed;
    border: 1px solid #d4d4d4;
    color: #868686;
    z-index: -2;
  }

  .but-primary {
    background-color: #F4CE00; /* Green */
  }
  .but-primary:hover {
    background-color: #ffd400; /* Green */
  }

  .but-secondary {
    background-color: #56525E; /* Green */
  }

  .but-tertiary {
    background-color:#39363E; /* Green */
  }

  .but-secondary:hover {
    background-color: #46434c; /* Green */
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

  .header-modal {
    width: 70rem;
    height: 20rem;
    background-color: white;
    border-radius: 1.5rem;
    padding: 2rem;
  }
  .header-modal .box {
    box-shadow: #26242A;
  }
  .header-modal p {
    color: black;
    font-size: 2rem;
  }


</style>
