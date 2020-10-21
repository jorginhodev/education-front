<template>
    <div class="wrapper">
      <h1>Lista de Milões disponíveis</h1>

      <section class="events">
        <article class="event" v-for="event in events" :key="event.id">
          <header>
            <img src="@/assets/event-image.png" alt="Imagem ilustrativa de um lanche" />
            <div>
              Seg
              <strong>{{ event.event_date }}</strong>
            </div>
            <div>
              R$ {{ event.price }}
            </div>
          </header>
          <div>
            <h2>{{ event.name }}</h2>
            <p>{{ event.location }}</p>
            <p>Por: {{ event.creator.name }}</p>
            <p>
              <img src="@/assets/icon-users.svg" alt="Ícone de alerta" width="24" height="24" />
              <span>{{ event.how_many_participants }}/{{ event.minimum_participants }}</span>
            </p>
          </div>
          <footer>
            <button @click="goEvent">Quero ir</button>
          </footer>
        </article>
      </section>

      <modal @close="closeModal" v-show="openModal" />
    </div>
</template>

<script>
import Modal from '@/components/Modal/index.vue';

export default {
  name: 'Events',
  components: {
    Modal,
  },
  data() {
    return {
      openModal: false,
      events: [
        {
          id: 1,
          title: 'Shanguay Sushi',
          creator: {
            name: 'Freddy',
          },
          location: 'R. Mal Deodoro, 1231',
          description: 'descrição do evento',
          price: 50,
          how_many_participants: 1,
          minimum_participants: 12,
          event_date: '02/09',
        },
        {
          id: 2,
          title: 'Noruega',
          creator: {
            name: 'Dioninho',
          },
          location: 'Av. Dom Joaquim, 823',
          description: 'descrição do evento',
          price: 50,
          how_many_participants: 3,
          minimum_participants: 6,
          event_date: '05/09',
        },
        {
          id: 3,
          title: 'Soni Lanches',
          creator: {
            name: 'Jorge',
          },
          location: 'Av. Marechal Floriano, 1237',
          description: 'descrição do evento',
          price: 50,
          how_many_participants: 2,
          minimum_participants: 12,
          event_date: '09/09',
        },
        {
          id: 4,
          title: 'Nicolas Lanches',
          creator: {
            name: 'Victor Xavier',
          },
          location: 'Av. Sei lá, s/n',
          description: 'descrição do evento',
          price: 50,
          how_many_participants: 4,
          minimum_participants: 12,
          event_date: '12/09',
        },
      ],
    };
  },
  methods: {
    goEvent() {
      console.log('ir no evento');
      this.openModal = true;
    },
    closeModal() {
      this.openModal = false;
    },
  },
};
</script>

<style scoped lang="scss">
.wrapper {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;

  h1 {
    margin: 0 auto 40px auto;
    font-weight: bold;
    font-size: 25px;
    line-height: 30px;
    border-left: 4px solid #6a35ff;
    padding-left: 10px;
  }
}

.events {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  margin: 0 auto 40px auto;
}

.event {
  max-width: 376px;
  width: 100%;
  height: 579px;
  background: #FBFBFB;
  box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  overflow-x: hidden;
  margin-bottom: 40px;

  header {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    position: relative;

    img {
      position: absolute;
      width: 100%;
      height: 100%;
    }

    div {
      background-color: #fff;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      z-index: 1;
    }

    div:nth-of-type(1) {
      width: 54px;
      height: 74px;
      border-radius: 10px;
      margin: 8px;
      font-weight: 500;
      font-size: 18px;
      line-height: 24px;

      strong {
        margin-top: 5px;
        font-weight: bold;
        font-size: 22px;
        line-height: 30px;
        color: #6A35FF;
      }
    }

    div:nth-of-type(2) {
      width: 91px;
      height: 54px;
      border-radius: 10px 0 0 0;
      align-self: flex-end;
      font-weight: bold;
      font-size: 28px;
      line-height: 39px;
      color: #6A35FF;
    }
  }

  div {
    padding: 0 20px;

    h2 {
      font-weight: 600;
      font-size: 25px;
      line-height: 30px;
    }

    p {
      font-size: 18px;
      line-height: 22px;
    }

    p:nth-of-type(1) {
      font-weight: 300;
    }

    p:nth-of-type(2) {
      font-weight: 500;
    }

    p:nth-of-type(3) {
      font-weight: bold;
      font-size: 23px;
      line-height: 28px;
      float: right;
      display: flex;
      align-items: baseline;

      img {
        margin-right: 10px;
      }

      span {
        align-self: self-end;
      }
    }
  }

  footer {
    button {
      font-weight: normal;
      font-size: 24px;
      line-height: 34px;
      background: #fff;
      color: #6A35FF;
      border: 1px solid #6A35FF;
      box-sizing: border-box;
      border-radius: 10px;
      width: 100%;
      height: 70px;
      transition: 0.6s;

      &:hover {
        background: #6A35FF;
        color: #fff;
        cursor: pointer;
      }
    }
  }
}
</style>
