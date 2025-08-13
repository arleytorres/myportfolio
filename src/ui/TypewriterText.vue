<template>
  <span class="typewriter-text">
    {{ displayText }}
    <span
      v-if="showCursor"
      class="cursor"
      :class="cursorClass"
    >
      {{ cursor }}
    </span>
  </span>
</template>

<script>
export default {
  name: 'TypewriterText',
  props: {
    words: {
      type: Array,
      required: true,
      default: () => ['Texto exemplo']
    },
    typeSpeed: {
      type: Number,
      default: 80
    },
    deleteSpeed: {
      type: Number,
      default: 40
    },
    pauseTime: {
      type: Number,
      default: 1200
    },
    showCursor: {
      type: Boolean,
      default: true
    },
    cursor: {
      type: String,
      default: '▌'
    },
    cursorClass: {
      type: String,
      default: 'animate-pulse text-cyan-400'
    },
    autoStart: {
      type: Boolean,
      default: true
    }
  },
  data() {
    return {
      currentWordIndex: 0,
      currentCharIndex: 0,
      isDeleting: false,
      displayText: '',
      timeoutId: null,
      isRunning: false
    };
  },
  mounted() {
    if (this.autoStart) {
      this.start();
    }
  },
  beforeUnmount() {
    this.stop();
  },
  watch: {
    words: {
      handler() {
        this.restart();
      },
      deep: true
    }
  },
  methods: {
    start() {
      if (!this.isRunning) {
        this.isRunning = true;
        this.type();
      }
    },

    stop() {
      this.isRunning = false;
      if (this.timeoutId) {
        clearTimeout(this.timeoutId);
        this.timeoutId = null;
      }
    },

    restart() {
      this.stop();
      this.reset();
      this.start();
    },

    reset() {
      this.currentWordIndex = 0;
      this.currentCharIndex = 0;
      this.isDeleting = false;
      this.displayText = '';
    },

    type() {
      if (!this.isRunning) return;

      const currentWord = this.words[this.currentWordIndex];

      if (this.isDeleting) {
        this.displayText = currentWord.substring(0, this.currentCharIndex - 1);
        this.currentCharIndex--;

        if (this.currentCharIndex === 0) {
          this.isDeleting = false;
          this.currentWordIndex = (this.currentWordIndex + 1) % this.words.length;
          this.timeoutId = setTimeout(() => this.type(), 100);
          return;
        }

        this.timeoutId = setTimeout(() => this.type(), this.deleteSpeed);
      } else {
        this.displayText = currentWord.substring(0, this.currentCharIndex + 1);
        this.currentCharIndex++;

        if (this.currentCharIndex === currentWord.length) {
          this.timeoutId = setTimeout(() => {
            this.isDeleting = true;
            this.type();
          }, this.pauseTime);
          return;
        }

        this.timeoutId = setTimeout(() => this.type(), this.typeSpeed);
      }

      this.$emit('typing', {
        text: this.displayText,
        wordIndex: this.currentWordIndex,
        charIndex: this.currentCharIndex,
        isDeleting: this.isDeleting
      });
    }
  }
};
</script>

<style scoped>
.typewriter-text {
  display: inline-block;
}

.cursor {
  display: inline-block;
}

.animate-pulse {
  animation: pulse 1s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
}
</style>