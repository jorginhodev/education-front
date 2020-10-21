<template>
  <div class="wrapper">
    <header>
      <img src="@/assets/logo.png" alt="Imagem com a logo do Milão da Atlas">
      <span>
        Olá, Javier
        <img
          src="@/assets/icon-arrow_down.svg" @click="openMenu"
          alt="Ícone de uma seta para baixo indicando que ao clicar irá abrir o menu" />
      </span>

      <nav v-if="isOpen">
        <ul class="menu">
          <li>
            <router-link to="/profile">
              <span>Meu Perfil</span>
              <img src="@/assets/icon-profile.svg" alt="Ícone simbolizando o perfil" />
            </router-link>
          </li>
          <li>
            <router-link to="/wallet">
              <span>Minha Carteira</span>
              <img src="@/assets/icon-wallet.svg" alt="Ícone simbolizando a carteira" />
            </router-link>
          </li>
          <li>
            <router-link to="/">
              <span>Sair</span>
              <img src="@/assets/icon-logout.svg" alt="Ícone simbolizando o botão de sair" />
            </router-link>
          </li>
        </ul>
      </nav>
    </header>
  </div>
</template>

<script>
export default {
  name: 'Header',
  components: {
  },
  data: () => ({
    isOpen: false,
  }),
  methods: {
    // openMenu: () => { this.isOpen = !(this.isOpen); },
    openMenu() { this.isOpen = !(this.isOpen); },
  },
};
</script>

<style scoped lang="scss">
.wrapper {
  width: 100vw;
  height: 80px;
  background: #FFFFFF;
  box-shadow: 0px 4px 25px rgba(0, 0, 0, 0.13);
  display: flex;
  justify-content: space-around;
  align-items: center;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  width: 100%;

  img {
    width: 60px;
    height: 60px;
  }

  span {
    display: flex;
    align-items: center;
    position: relative;

    img {
      width: 20px;
      height: 20px;
      margin-left: 8px;
      cursor: pointer;
    }
  }

  nav {
    position: absolute;
    right: 5%;
    top: 8%;
    background-color: #fff;
    border: 1px solid #4d4d4d;
    width: 200px;
    border-radius: 10px;
    z-index: 9;
  }
}

.menu {
  display: flex;
  flex-direction: column;
  list-style: none;
  padding: 0;
  margin: 0;

  li {
    padding: 3px;

    &:nth-of-type(even) {
      border-top: 1px solid blue;
      border-bottom: 1px solid blue;
    }

    a {
      text-decoration: none;
      font-weight: 500;
      font-size: 14px;
      line-height: 17px;
      color: #4d4d4d;
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: space-between;
      height: 30px;

      span {
        align-self: center;
        margin-left: 15px;
      }

      img {
        width: 20px;
        margin-right: 15px;
      }
    }
  }
}
</style>
