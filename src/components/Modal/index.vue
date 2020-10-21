<template>
  <div class="wrapper-modal" @click="outClick">
    <section class="modal">
      <img
        class="close"
        src="@/assets/icon-close.svg"
        alt="Ícone de alerta"
        @click="closeModal"
      />

      <div class="content">
        <section v-if="step1" class="step1">
          <img src="@/assets/icon-warning.svg" alt="Ícone de alerta" />
          <p class="alert">
            Você tem certeza que deseja participar deste evento?
          </p>
          <p class="confirm">
            Confirmando sua participação será descontado 50 vaders de sua carteira.
          </p>
          <button @click="confirmParticipation">Sim, desejo</button>
        </section>

        <section v-if="step2" class="step2">
          <img src="@/assets/user.png" alt="Imagem do usuário(a) que irá participar do evento" />
          <p class="line-1">
            Legal <b>Victor</b>, você confirmou presença no <b>Noruega</b>.
          </p>
          <p class="line-2">
            Compartilhe no grupo do milão o seu ingresso, para que seus
            colegas saibam que você fará parte. :)
          </p>
          <img src="@/assets/telegram-share.svg" alt="Ícone do Telegram" />
        </section>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  data() {
    return {
      step1: true,
      step2: false,
    };
  },
  methods: {
    closeModal() {
      console.log('emitiu evento de fechar');
      this.step1 = true;
      this.step2 = false;
      this.$emit('close');
    },
    outClick({ currentTarget, target }) {
      if (currentTarget === target) this.$emit('close');
    },
    confirmParticipation() {
      this.step1 = false;
      this.step2 = true;
    },
  },
};
</script>

<style scoped lang="scss">
.wrapper-modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
  background: rgba(0, 0, 0, 0.7);
  overflow-y: scroll;
}

.modal {
  width: 350px;
  height: 480px;
  background: #FBFBFB;
  box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
  padding: 0 20px;
  box-sizing: border-box;
  text-align: center;
  position: relative;
  display: flex;
  opacity: 1;
  animation: showModal .3s linear;

  .close {
    position: absolute;
    top: 20px;
    right: 20px;
    cursor: pointer;
    width: 30px;
    height: 30px;
  }

  .step1 {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100%;

    img {
      width: 80px;
      height: 80px;
    }

    .alert {
      font-weight: normal;
      font-size: 15px;
      line-height: 18px;
      color: #000000;
      margin-top: 40px;
    }

    .confirm {
      font-weight: normal;
      font-size: 12px;
      line-height: 15px;
      color: #0091C8;
      margin: 20px auto 55px;
    }

    button {
      width: 255px;
      height: 40px;
      border: 2px solid #6A35FF;
      filter: drop-shadow(0px 4px 15px rgba(0, 0, 0, 0.25));
      border-radius: 10px;
      transition: 0.6s ease-out;
      font-weight: normal;
      font-size: 16px;
      line-height: 20px;
      text-align: center;
      color: #6A35FF;
      cursor: pointer;

      &:hover {
        background: #6A35FF;
        color: #fff;
      }
    }
  }

  .step2 {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100%;
    animation: hideContent 2s;

    img:nth-of-type(2) {
      width: 80px;
      height: 80px;
    }
  }
}

@keyframes showModal {
  from {
    transform: scale(0);
    opacity: 0;
    z-index: -1;
  }
  to {
    opacity: 1;
    z-index: 2;
  }
}

@keyframes hideContent {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
