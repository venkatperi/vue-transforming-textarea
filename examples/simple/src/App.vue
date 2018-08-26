<template>
  <div>
    <transforming-textarea
      v-model="text"
      :transform="upperCase"
      class="input2">
    </transforming-textarea>
  </div>
</template>


<script>
  import TransformingTextarea from 'code/VueTransformingTextarea'

  export default {

    components: { TransformingTextarea },

    data() {
      return {
        text: '',
      }
    },

    methods: {
      upperCase( x ) {
        return (x || '').toUpperCase()
      },
    },

  }
</script>

<style lang="scss" scoped>
  .input2 {
    width: 600px;
    resize: none;
  }
</style>

