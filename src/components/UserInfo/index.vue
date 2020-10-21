<template>
  <div class="wrapper">
    <section class="user_info">
      <div class="info">
        <img src="@/assets/avatar.png" alt="">
        <p>
          Victor Javier<br />
          <span>Restam ainda <strong>50</strong> vaders</span>
        </p>
      </div>
      <div class="buttons">
        <button class="create_event">Criar evento</button>
        <button class="view_wallet">Ver minha carteira</button>
      </div>
    </section>
  </div>
</template>

<script>

export default {
  name: 'UserInfo',
  components: {
  },
};
</script>

<style scoped lang="scss">
.wrapper {
  max-width: 1200px;
  width: 100%;
  margin: 85px auto;
}
.user_info {
  display: flex;
  justify-content: space-between;
  align-items: center;

  .info {
    display: flex;
    align-items: center;

    p {
      margin-left: 30px;
      text-align: left;
      font-weight: normal;
      font-size: 31px;
      line-height: 38px;

      span {
        display: flex;
        align-items: center;
        font-weight: 600;
        font-size: 35px;
        line-height: 43px;
        color: #515151;

        strong {
          color: #6A35FF;
          margin-left: 10px;
          margin-right: 10px;
        }
      }
    }
  }

  .buttons {
    display: flex;
    flex-direction: column;

    button {
      width: 300px;
      height: 68px;
      align-self: flex-end;
      cursor: pointer;
      transition: 0.6s ease-out;
      filter: drop-shadow(0px 4px 15px rgba(0, 0, 0, 0.25));
      border-radius: 10px;
      font-size: 20px;
      border: 2px solid #6A35FF;
    }

    .create_event {
      margin-bottom: 30px;
      background: transparent;
      color: #6A35FF;

      &:hover {
        background: #6A35FF;
        color: #fff;
      }
    }

    .view_wallet {
      background: #6A35FF;
      color: #fff;

      &:hover {
        background: #fff;
        color: #6A35FF;
      }
    }
  }
}
</style>
