<template>
  <div>
    <ul>
      <li v-for="livro in livros" :key="livro.nome">
        <p>{{livro.nome}}</p>
      </li>
    </ul>
    <ul>
      <h2>livros lidos</h2>
      <li v-for="livro in livrosLidos(true)" :key="livro.nome">
        <p>{{livro.nome}}</p>
      </li>
    </ul>
    <!-- {{$store.state.acao}} -->
    <Aluno/>
    <Curso/>
  </div>
</template>

<script>
import { mapGetters} from "vuex"
import { mapState} from "vuex"
export default {
  computed: {
    ...mapGetters(["livrosLidos"]),
     ...mapState(["livros"])
  },
  created(){
    this.$store.dispatch("puxarAcao")
  }
}
</script>

<style>

</style>
<style>

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
