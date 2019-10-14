<script>
import BaseCity from './BaseCity.vue'
export default {
  extends: BaseCity,
  data() {
    return {
      content: {
        name: 'two_cities.right_city.name',
        shortname: 'two_cities.right_city.short_name',
        caption: 'two_cities.right_city.caption',
        description: this.isMobile
          ? 'two_cities.right_city.mobile-description'
          : 'two_cities.right_city.description',
        backgroundUrl: this.isMobile ? '/m_waw@2x.jpg' : '/wew_desktop@2x.jpg'
      }
    }
  }
}
</script>
<style lang="scss">
.city--right {
  right: 0;
  .city__info-element-title {
    &:after {
      background: url('~assets/line_waw.svg');
    }
  }
  .city__photo {
    object-position: right;
  }
}
</style>
