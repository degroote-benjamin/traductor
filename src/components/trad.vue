<template>
  <div id="trad">
    <!-- submit methode formsub-->
    <form v-on:submit="formsub">
        <input type="text" v-model="texteatrad" placeholder="entrer un mot">
        <select v-model="langue">
              <option value="ru">Russe</option>
              <option value="es">espagnole</option>
              <option value="en">Anglais</option>
              <option value="zh">Chinois</option>
              <option value="ja">Japonais</option>
        </select>
        <input type="submit" name="" value="traduire">
    </form>
  </div>
</template>

<script>

export default {
  name: 'trad',
  data(){
    return {
      // texte recuperer dans le input
      texteatrad:'',
      langue:'en'
    }
  },
  methods:{
    formsub(e){
      // envoie des donner sur app.vue du composant trad.vue
      this.$emit('formsub',this.texteatrad,this.langue)
      e.preventDefault()
    }
  }
}
</script>

<style>
#app {
}
</style>
