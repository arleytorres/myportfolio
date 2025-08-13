<template>
  <div class="flex bg-[#0A101F] h-125 w-full p-6 rounded-2xl border border-slate-700 shadow-2xl shadow-cyan-900/30">
    <main class="text-white w-full">

      <!-- Mensagem de Sucesso -->
      <transition name="fade">
        <div v-if="showSuccess" class="mb-4 bg-green-900/30 border border-green-700 text-green-400 px-4 py-3 rounded-lg text-center">
          ✅ {{ successMessage }}
        </div>
      </transition>

      <!-- Campo Nome -->
      <div class="mb-6">
        <p class="ml-1 mb-2">Nome <span class="text-red-400">*</span></p>
        <input
            type="text"
            v-model="form.userName"
            :class="{ 'border-red-500': errors.userName }"
            class="w-full h-10 rounded-lg border border-slate-700 p-3 bg-[#080C17] text-white placeholder-gray-400 focus:border-cyan-500 focus:outline-none transition-colors"
            placeholder="Seu nome completo"
            @input="clearError('userName')"
        >
        <span v-if="errors.userName" class="text-red-400 text-sm mt-1 block">{{ errors.userName }}</span>
      </div>

      <!-- Campo Email -->
      <div class="mb-6">
        <p class="ml-1 mb-2">Email <span class="text-red-400">*</span></p>
        <input
            type="email"
            v-model="form.userEmail"
            :class="{ 'border-red-500': errors.userEmail }"
            class="w-full h-10 rounded-lg border border-slate-700 p-3 bg-[#080C17] text-white placeholder-gray-400 focus:border-cyan-500 focus:outline-none transition-colors"
            placeholder="seu.email@exemplo.com"
            @input="clearError('userEmail')"
        >
        <span v-if="errors.userEmail" class="text-red-400 text-sm mt-1 block">{{ errors.userEmail }}</span>
      </div>

      <!-- Campo Mensagem -->
      <div class="mb-6">
        <p class="ml-1 mb-2">Mensagem <span class="text-red-400">*</span></p>
        <textarea
            v-model="form.userMessage"
            :class="{ 'border-red-500': errors.userMessage }"
            class="bg-[#080C17] w-full h-40 rounded-lg border border-slate-700 p-3 text-white placeholder-gray-400 focus:border-cyan-500 focus:outline-none transition-colors resize-none"
            placeholder="Digite sua mensagem aqui..."
            @input="clearError('userMessage')"
        />
        <span v-if="errors.userMessage" class="text-red-400 text-sm mt-1 block">{{ errors.userMessage }}</span>
      </div>

      <!-- Botão Preview -->
      <button
          v-if="isFormValid"
          @click="togglePreview"
          class="mb-4 mr-3 px-4 py-2 text-cyan-400 border border-cyan-400 rounded-lg hover:bg-cyan-400 hover:text-black transition-all duration-300 text-sm"
          type="button"
      >
        📋 {{ showPreview ? 'Ocultar' : 'Visualizar' }} Email
      </button>

      <!-- Preview do Email -->
      <transition name="slide-down">
        <div v-if="showPreview && isFormValid" class="mb-6 bg-slate-800/50 border border-slate-600 rounded-lg p-4">
          <h3 class="text-cyan-400 font-semibold mb-3">📧 Prévia do Email:</h3>
          <div class="space-y-2 text-sm">
            <p><strong class="text-gray-300">Para:</strong> <span class="text-cyan-300">{{ myEmail }}</span></p>
            <p><strong class="text-gray-300">Assunto:</strong> {{ emailSubject }}</p>
            <p><strong class="text-gray-300">De:</strong> {{ form.userName }} ({{ form.userEmail }})</p>
            <div class="mt-3">
              <p class="text-gray-300 font-semibold">Mensagem:</p>
              <div class="bg-slate-900 rounded p-3 mt-2 text-gray-200 whitespace-pre-line">{{ form.userMessage }}</div>
            </div>
          </div>
        </div>
      </transition>

      <!-- Botão Enviar -->
      <custom-button
          :type="isFormValid ? 'primary' : 'disabled'"
          :text="isLoading ? 'Enviando...' : 'Enviar'"
          size="small"
          :class="{
          'text-black cursor-pointer': isFormValid && !isLoading,
          'opacity-50 cursor-not-allowed': !isFormValid || isLoading
        }"
          :disabled="!isFormValid || isLoading"
          @click="sendEmail"
      />

    </main>
  </div>
</template>

<script>
import CustomButton from "@/ui/CustomButton.vue";

export default {
  name: 'ContactCardEmail',
  components: { CustomButton },

  data() {
    return {
      myEmail: 'arley_emanuel@hotmail.com',

      form: {
        userName: '',
        userEmail: '',
        userMessage: ''
      },

      errors: {},
      showPreview: false,
      showSuccess: false,
      successMessage: '',
      isLoading: false
    }
  },

  computed: {
    isFormValid() {
      return this.form.userName.trim() !== '' &&
          this.form.userEmail.trim() !== '' &&
          this.form.userMessage.trim() !== '' &&
          this.isValidEmail(this.form.userEmail);
    },

    // Gera o assunto do email
    emailSubject() {
      return `Contato do site - ${this.form.userName || 'Visitante'}`;
    },

    emailBody() {
      return `Olá!

Você recebeu uma nova mensagem através do formulário de contato do seu site.

👤 DADOS DO REMETENTE:
Nome: ${this.form.userName}
Email: ${this.form.userEmail}

💬 MENSAGEM:
${this.form.userMessage}

---
Esta mensagem foi enviada através do formulário de contato do seu website.
Para responder, utilize o email: ${this.form.userEmail}`;
    }
  },

  methods: {
    isValidEmail(email) {
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      return emailRegex.test(email);
    },

    clearError(field) {
      if (this.errors[field]) {
        this.$delete(this.errors, field);
      }
    },

    validateForm() {
      this.errors = {};

      if (!this.form.userName.trim()) {
        this.$set(this.errors, 'userName', 'Nome é obrigatório');
      }

      if (!this.form.userEmail.trim()) {
        this.$set(this.errors, 'userEmail', 'Email é obrigatório');
      } else if (!this.isValidEmail(this.form.userEmail)) {
        this.$set(this.errors, 'userEmail', 'Email inválido');
      }

      if (!this.form.userMessage.trim()) {
        this.$set(this.errors, 'userMessage', 'Mensagem é obrigatória');
      }

      return Object.keys(this.errors).length === 0;
    },

    togglePreview() {
      if (this.isFormValid) {
        this.showPreview = !this.showPreview;
      }
    },

    sendEmail() {
      if (!this.validateForm()) {
        return;
      }

      this.isLoading = true;

      setTimeout(() => {
        const mailtoUrl = `mailto:${this.myEmail}?subject=${encodeURIComponent(this.emailSubject)}&body=${encodeURIComponent(this.emailBody)}`;

        window.location.href = mailtoUrl;

        this.showSuccessMessage('Seu cliente de email foi aberto com a mensagem pronta!');

        this.isLoading = false;
      }, 800);
    },

    // Mostrar mensagem de sucesso
    showSuccessMessage(message) {
      this.successMessage = message;
      this.showSuccess = true;

      setTimeout(() => {
        this.showSuccess = false;
      }, 5000);
    },

    // Resetar formulário (método opcional)
    resetForm() {
      this.form = {
        userName: '',
        userEmail: '',
        userMessage: ''
      };
      this.errors = {};
      this.showPreview = false;
    }
  },

  mounted() {
    console.log('🚀 ContactCard carregado!');
    console.log('📧 Email configurado:', this.myEmail);
  }
}
</script>

<style scoped>
/* Transições personalizadas */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter, .fade-leave-to {
  opacity: 0;
}

.slide-down-enter-active {
  transition: all 0.3s ease;
}

.slide-down-leave-active {
  transition: all 0.2s ease;
}

.slide-down-enter, .slide-down-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

/* Estilos adicionais para melhor UX */
input:focus, textarea:focus {
  box-shadow: 0 0 0 3px rgba(6, 182, 212, 0.1);
}

/* Animação no placeholder */
input::placeholder, textarea::placeholder {
  transition: color 0.3s ease;
}

input:focus::placeholder, textarea:focus::placeholder {
  color: rgba(156, 163, 175, 0.6);
}
</style>