<template>
  <div>
    <div class="bcn" />
    <div class="wew">
      <div class="wew__place-title">
        <h3 align="center">Warsaw Tech Hub</h3>
      </div>
      <div class="wew__title">
        <div>
          <span>
            Warsaw Tech Hub
          </span>
        </div>
        <p>
          Icing pie dragée tootsie <br />
          roll sweet caramels <br />donut chocolate cake.<br />
          C hocolate cake donut <br />topping lollipop tart <br />cheesecake
          lollipop ice <br />
          cream. Cake roll toffee <br />
          soufflé cotton candy.<br />
          Sugar plum icing sweet
          <br />
          candy canes.
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.wew {
  position: absolute;
  background-image: url('../assets/wew_desktop@2x.png');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 100% 50%;
  width: 50%;
  height: 110vh;
  right: 0px;
  &__title {
    display: none;
  }
  &--clicked {
    box-shadow: inset 0 0 0 2000px rgba(7, 7, 7, 0.45);
    width: 75%;
    .wew__place-title {
      display: none !important;
    }
    .wew__title {
      display: block;
      padding: 80px 0px 150px 0px;
      font-size: 20px;
    }
  }
  //удалить нахой потом
  &:hover {
    box-shadow: inset 0 0 0 2000px rgba(7, 7, 7, 0.45);
    width: 75%;
    .wew__title {
      font-size: 50px !important;
    }
    .wew__place-title {
      display: none !important;
    }
  }
}

.bcn {
  position: absolute;
  background-image: url('../assets/bcn_desktop@2x.png');
  background-repeat: no-repeat;
  background-size: cover;
  left: 0px;
  width: 50%;
  height: 100vh;
  //background-position: center;
}
</style>
