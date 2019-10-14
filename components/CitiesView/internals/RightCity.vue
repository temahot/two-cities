<script>
import BaseCity from './BaseCity.vue'
export default {
  extends: BaseCity,
  data() {
    return {
      content: {
        name: 'Warsaw',
        caption: 'Tech Hub',
        description: this.isMobile
          ? ' \n Icing pie dragée \n tootsie roll sweet \n caramels donut \n chocolate cake. \n Chocolate cake \n donut topping \n lollipop tart \n cheesecake \n lollipop ice cream. \n Cake roll toffee \n soufflé cotton \n candy'
          : ' \n Icing pie dragée tootsie \n roll sweet caramels \n donut chocolate cake. \n Chocolate cake donut \n topping lollipop tart \n cheesecake lollipop ice \n cream. Cake roll toffee \n soufflé cotton candy. \n Sugar plum icing sweet \n candy canes.',
        shortname: 'WAW',
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
