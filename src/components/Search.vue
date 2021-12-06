<template>
  <v-form>
    <v-text-field v-model="searchTitle"
                  label="What do you need to Search?"
                value="query"
                onChange="txt_change"
                  autofocus
                   v-on:input="search()"
                   ref="input"
                  >
    </v-text-field>
  </v-form>
</template>

<script>

export default {
  name: 'SeachField',
  data () {
    return {
      title: ""

    }
  },

  methods: {
   
   search(){
       
        this.$store.state.search=this.searchTitle
       
    }
  }
}

</script>
