<template>
  <button
      :class="buttonClasses"
      :disabled="disabled"
      @click="handleClick"
      class="cursor-pointer"
  >
    <slot>{{ text }}</slot>
  </button>
</template>

<script>
export default {
  name: 'CustomButton',
  props: {
    text: {
      type: String,
      default: 'Clique aqui'
    },
    disabled: {
      type: Boolean,
      default: false
    },
    type: {
      type: String,
      default: 'primary',
      validator: function (value) {
        return ['primary', 'secondary', 'danger'].indexOf(value) !== -1
      }
    },
    size: {
      type: String,
      default: 'medium',
      validator: function (value) {
        return ['small', 'medium', 'large'].indexOf(value) !== -1
      }
    }
  },
  computed: {
    buttonClasses() {
      let classes = 'font-medium rounded-lg transition-colors duration-200 focus:outline-none'

      // Tamanhos
      if (this.size === 'small') {
        classes += ' px-6 py-2 text-base'
      } else if (this.size === 'medium') {
        classes += ' px-7 py-2 text-base'
      } else if (this.size === 'large') {
        classes += ' px-6 py-3 text-lg'
      }

      // Tipos/cores
      if (this.disabled) {
        classes += ' bg-gray-300 text-gray-500 cursor-not-allowed'
      } else {
        if (this.type === 'primary') {
          classes += ' bg-sky-500 hover:bg-sky-600'
        } else if (this.type === 'secondary') {
          classes += ' bg-slate-600 text-white hover:bg-slate-700'
        } else if (this.type === 'danger') {
          classes += ' bg-red-600 text-white hover:bg-red-700'
        }
      }

      return classes
    }
  },
  methods: {
    handleClick(event) {
      if (!this.disabled) {
        this.$emit('click', event)
      }
    }
  }
}
</script>