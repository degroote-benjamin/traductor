<template>
<div id="app">
  <h1 class="jumbotron blue">traducteur</h1>
  <!-- utilise la fonction texttraduit via formsub de trad.vue , les paramettre de la fonction sont les parametre recuperer dans le emit-->
  <trad class="text-center "v-on:formsub="texttraduit"></trad>
  <!-- recupere le texte traduit via tradsortie avec un props -->
  <tradsortie class="text-center" v-text="textetrad"></tradsortie>
</div>
</template>
<script>
import trad from './components/trad'
import tradsortie from './components/tradsortie'


export default {
  name: 'app',
  components: {
    trad,
    tradsortie
  },
  data(){
    return {
      textetrad:''
    }
  },
  methods: {
    texttraduit: function(texte,langue) {
      // GET /someUrl
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170329T180255Z.3c18d2dc7b65d525.f23ed9a9efa992bded4ef96334e3c154f61d2dea&lang=fr-'+langue+'&text='+texte)
      .then((response) => {
        this.textetrad = response.body.text[0]
      })
    }
  }
}
</script>

<style>
.blue{
  background: blue;
  text-align: center;
}
</style>
