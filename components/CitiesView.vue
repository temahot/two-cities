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
import { isMobile } from 'mobile-device-detect'
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
      activeCity: activeCitiesState.NONE,
      isMobile
    }
  },
  computed: {
    isLeftCityActive() {
      return this.activeCity === activeCitiesState.LEFT
    },
    isRightCityActive() {
      return this.activeCity === activeCitiesState.RIGHT
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
