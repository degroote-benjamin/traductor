<template>
  <div id="trad">
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
      texteatrad:'',
      langue:'en'
    }
  },
  methods:{
    formsub(e){
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
