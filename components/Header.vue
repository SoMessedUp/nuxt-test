<template>
  <header class="header">
    <img src="img/logo.png" alt="Logo" class="logo">
    <div class="wrapper">
      <div class="navigation">
        <div class="navigation__element navigation__element-search">
          <img src="img/Search.svg" alt="" class="navigation__element-img">
        </div>
        <div class="navigation__element navigation__element-favorite">
          <img src="img/Favorite.svg" alt="" class="navigation__element-img">
        </div>
        <div class="navigation__element navigation__element-user">
          <img src="img/User.svg" alt="" class="navigation__element-img">
        </div>
        <div class="navigation__element navigation__element-basket">
          <img src="img/Basket.svg" alt="" class="navigation__element-img">
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  position: relative;
  width: 100%;
  height: auto;
}
.header .wrapper {
  display: flex;
  justify-content: end;
}
.logo {
  position: absolute;
  height: 24px;
  width: 54px;
  top: 30px;
  left: 50%;
  transform: translateX(-50%);
}
.navigation {
  display: flex;
  align-self: end;
  padding: 32px 9px 32px 0;
}
.navigation__element+.navigation__element {
  margin-left: 16px;
}

@media (max-width: 760px) {
  .navigation__element-user {
    position: absolute;
    left: 0;
  }
  .navigation__element-search {
    position: absolute;
    left: 36px;
  }
  .navigation__element-favorite {
    display: none;
  }
  .navigation {
    padding: 15px 0;
  }
  .logo {
    width: 38px;
    height: 17px;
    top: 17px;
  }
}

</style>
