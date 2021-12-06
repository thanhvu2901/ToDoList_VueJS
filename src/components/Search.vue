<template>
  <v-form>
    <v-text-field v-model=" searchTitle"
                  label="What do you need to Search?"
                value="query"
                onChange="txt_change"
            
                  autofocus

                  >
    </v-text-field>
  </v-form>
</template>

<script>


export default {
  name: 'SeachField',
  data () {
    return {
      title: ''

    }
  },

  methods: {
    search () {
        this.
    }
  }
}

</script>
