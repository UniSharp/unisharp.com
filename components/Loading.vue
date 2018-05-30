<template lang="pug">
  .u-loading
    .u-loading-logo
      .u-loading-ring
</template>

<script>
  export default {
    //
  }
</script>

<style lang="scss" scoped>
  @import "~assets/scss/helpers";
  @import "~assets/scss/variables";

  @keyframes spin {
    from {
      transform: rotate(0);
    }

    to {
      transform: rotate(360deg);
    }
  }

  .u-loading {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 100;
    background: #fff;

    &, &-logo {
      display: flex;
      align-items: center;
      justify-content: center;
    }

    &-ring {
      flex: 0 0 auto;
      border-radius: 50%;
      border: 2px solid #262c32;
      width: 5.625rem;
      height: 5.625rem;
      border-top-color: rgba(255, 255, 255, .7);
      animation: spin .8s infinite linear;
    }

    &-logo {
      @include background("/loading.svg", 100%);

      width: 1.875rem;
      height: 1.875rem;
    }
  }
</style>
