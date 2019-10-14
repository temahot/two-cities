<script>
import BaseCity from './BaseCity.vue'
export default {
  extends: BaseCity,
  data() {
    return {
      content: {
        name: 'Barcelona',
        caption: 'HQ',
        description: this.isMobile
          ? ' \n Our Tech Hub in \n Sunny Barcelona is \n located only 12 min \n walk from the \n beach and we now \n count with a +70 \n engineering team \n to  build and \n improve  products \n for our customers.'
          : ' \n Our Tech Hub in Sunny \n Barcelona is located \n only 12 min walk from \n the beach and we now \n count with a +70 \n engineering team to \n build and improve \n products for our \n customers.',
        shortname: 'BCN',
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
@media (max-width: 600px) {
}
</style>
