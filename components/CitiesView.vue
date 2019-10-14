<template>
  <div>
    <left-city
      :isMobile="isMobile"
      :isActive="isLeftCityActive"
      class="city--left"
      @click.native="toggleLeft"
    />

    <right-city
      :isMobile="isMobile"
      :isActive="isRightCityActive"
      class="city--right"
      @click.native="toggleRight"
    />
  </div>
</template>

<script>
import LeftCity from './CitiesView/internals/LeftCity.vue'
import RightCity from './CitiesView/internals/RightCity.vue'

const activeCitiesState = {
  LEFT: 'LEFT',
  RIGHT: 'RIGHT',
  NONE: 'NONE'
}

export default {
  components: {
    LeftCity,
    RightCity
  },
  data() {
    return {
      activeCity: activeCitiesState.NONE
    }
  },
  computed: {
    isLeftCityActive() {
      return this.activeCity === activeCitiesState.LEFT
    },
    isRightCityActive() {
      return this.activeCity === activeCitiesState.RIGHT
    },
    isMobile() {
      if (screen.width <= 600) {
        return true
      } else {
        return false
      }
    }
  },
  methods: {
    toggleLeft() {
      this.activeCity =
        this.activeCity === activeCitiesState.LEFT
          ? activeCitiesState.NONE
          : activeCitiesState.LEFT
    },
    toggleRight() {
      this.activeCity =
        this.activeCity === activeCitiesState.RIGHT
          ? activeCitiesState.NONE
          : activeCitiesState.RIGHT
    }
  }
}
</script>

