<template>
  <div class="city" :class="{'city--active':isActive}">
    <div class="city__info-element-title">
      <img
        src="~/assets/close_mobile.svg"
        v-show="isMobile"
        class="city__info-element-close"
        alt="close"
      />
      <h3 align="center" class="city__info-element-content-mobile">
        {{content.name}}
        <span class="city__info-element-caption">{{content.caption}}</span>
      </h3>
      <h3 align="center" class="city__info-element-content">
        {{ isMobile ? content.shortname : content.name}}
        <span
          class="city__info-element-caption"
        >{{content.caption}}</span>
      </h3>
    </div>
    <p class="city__info-element-description">{{content.description}}</p>
    <img class="city__photo" :src="content.backgroundUrl" :alt="content.placeTitle" />
  </div>
</template>

<script>
export default {
  props: {
    isActive: {
      type: Boolean,
      required: true
    },
    isMobile: {
      type: Boolean,
      required: true
    }
  },
  data() {
    return {
      content: {
        name: this.isMobile ? 'msc' : 'Moscow',
        caption: 'city of vodka',
        description:
          'Hey, Lorem ipsum dolor sit amet, consectetur adipisicing elit,\n sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
        shortname: 'MOW',
        backgroundUrl: null
      }
    }
  },
  mounted() {
    window.addEventListener('resize', () => {
      console.log('le')
      console.log(window.innerHeight)
    })
  }
}
</script>

<style lang="scss" scoped>
$transition-duration: 0.3s;
.city {
  overflow: hidden;
  position: absolute;
  background-repeat: no-repeat;
  background-size: cover;
  width: 50%;
  height: 100vh;
  transition: $transition-duration all;
  cursor: url('~assets/cursor_hover_enter.svg'), auto;
  z-index: 0;
  p {
    white-space: pre-wrap;
    display: none;
  }
  &__info-element-close {
    visibility: hidden;
  }
  &__info-element-content-mobile {
    display: none;
  }
  &__info-element-content {
    transition: margin $transition-duration ease-in-out;
    font-size: 50px;
    color: white !important;
  }

  &__info-element-caption {
    font-weight: 300;
  }
  .city__info-element-title {
    &:after {
      width: 0%;
      background-repeat: no-repeat;
      margin-top: -10px;
      margin-left: 90px;
      display: block;
      content: '';
      height: 5px;
      transition: width 0.3s ease-in-out;
      opacity: 0;
    }
  }
  &__photo {
    transition: $transition-duration;
    position: absolute;
    top: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: -1;
    transform: scale(1.035);
  }
  &:hover,
  &--active {
    .city__photo {
      filter: brightness(0.75);
      transform: scale(1);
    }
  }

  &--active {
    .city__info-element-title {
      &:after {
        opacity: 1;
        width: 100%;
      }
    }
    z-index: 1;
    cursor: url('~assets/cursor_hover.svg'), auto;
    width: 75%;
    .city__info-element-content {
      margin-top: 100px;
      margin-left: 90px;
      text-align: left;
      color: white;
      font-size: 21px;
    }
    p {
      margin-top: 70px;
      margin-left: 70px;
      display: block;
      font-size: 42px;
      line-height: 1em;
      font-weight: bold;
      color: white;
    }
  }

  &:not(.city--active):hover {
    z-index: 0;
  }
}

@media (max-width: 600px) {
  .city {
    &__info-element-content {
      font-size: 30px;
      color: white !important;
    }
    &__info-element-caption {
      display: block;
      font-size: 20px;
    }
    &__info-element-content-mobile {
      display: none;
      transition: display 0.3s ease-in-out;
    }
    &--active {
      .city__info-element-close {
        visibility: visible;
        position: absolute;
        margin-left: 80%;
        margin-top: 5px;
      }
      .city__info-element-content-mobile {
        display: block;
        margin-top: 30px;
        margin-left: 30px;
        text-align: left;
        color: white;
        font-size: 18px;
      }
      .city__info-element-caption {
        display: unset !important;
        font-size: 20px;
      }
      .city__info-element-content {
        display: none;
      }
      .city__info-element-title {
        &:after {
          opacity: 1;
          width: 100%;
          margin-top: -10px;
          margin-left: 30px;
        }
      }
      z-index: 1;
      cursor: url('~assets/cursor_hover.svg'), auto;
      width: 100%;

      p {
        //letter-spacing: -2.7px;
        line-height: 1.3em;
        margin-top: 30px;
        margin-left: 30px;
        display: block;
        font-size: 30px;
        font-weight: bold;
        color: white;
      }
    }
  }
}
</style>