<template>
  <header class="header">
    <h3 class="header__icon">
      <i class="ion-social-octocat" />
    </h3>

    <p class="header__route">
      {{$route.name}}
    </p>

    <div class="windowControl">
      <button @click="minimize">
        <svg x="0" y="0" viewBox="0 0 10 2" style="width: 10px; height: 10px;">
          <rect fill="#fff" width="10.2" height="0.5"></rect>
        </svg>
      </button>
      <button @click="resize">
        <svg x="0" y="0" viewBox="0 0 10.2 10.2" style="width: 10px; height: 10px;">
          <path fill="rgba(255, 255, 255, 0.6)" d="M0,0v10.1h10.2V0H0z M9.2,9.2H1.1V1h8.1V9.2z"></path>
        </svg>
      </button>
      <button @click="close">
        <svg x="0" y="0" viewBox="0 0 10.2 10.2" style="width: 10px; height: 10px;">
          <polygon fill="rgba(255, 255, 255, 0.8)" points="10.2,0.7 9.5,0 5.1,4.4 0.7,0 0,0.7 4.4,5.1 0,9.5 0.7,10.2 5.1,5.8 9.5,10.2 10.2,9.5 5.8,5.1 "></polygon>
        </svg>
      </button>
    </div>

  </header>
</template>

<script>
export default {
  name: 'LayoutHeader',
  data: () => ({
    window: undefined,
  }),
  methods: {
    minimize() {
      this.window.minimize();
    },
    resize() {
      if (this.window.isMaximized()) {
        this.window.unmaximize();
      } else {
        this.window.maximize();
      }
    },
    close() {
      this.window.close();
    },
  },
  created() {
    this.window = this.$electron.remote.getCurrentWindow();
  },
};
</script>

