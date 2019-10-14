<script>
import BaseCity from './BaseCity.vue'
export default {
  extends: BaseCity,
  data() {
    return {
      content: {
        name: 'two_cities.left_city.name',
        caption: 'two_cities.left_city.caption',
        shortname: 'two_cities.left_city.short_name',
        description: this.isMobile
          ? 'two_cities.left_city.mobile-description'
          : 'two_cities.left_city.description',
        backgroundUrl: this.isMobile ? '/m_bcn@2x.jpg' : '/bcn_desktop@2x.jpg'
      }
    }
  }
}
</script>
<style lang="scss">
.city--left {
  left: 0;
  .city__info-element-title {
    &:after {
      background: url('~assets/line_bcn.svg');
    }
  }
  .city__photo {
    object-position: left;
  }
}
</style>
