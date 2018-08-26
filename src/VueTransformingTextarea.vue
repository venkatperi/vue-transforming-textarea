<template>
  <!--suppress HtmlFormInputWithoutLabel -->
  <textarea v-model="internalValue"> </textarea>
</template>

<script>
  // noinspection JSUnusedGlobalSymbols
  export default {
    name: 'transforming-textarea',

    props: {
      value: { required: false },
      transform: {
        type: Function,
        default: x => x,
      },
    },

    data: vm => ({
      lazyValue: vm.value,
    }),

    computed: {
      internalValue: {
        get() {
          return this.lazyValue
        },
        set( val ) {
          this.lazyValue = this.transform( val )
          this.$emit( 'input', this.lazyValue )
        },
      },
    },

    watch: {
      value( x ) {
        this.lazyValue = this.transform( x )
      },
    },
  }
</script>


