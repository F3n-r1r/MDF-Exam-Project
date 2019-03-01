<template>
    <div class="tab-container">

        <div class="tab-container__tabs">

            <a class="tabs__tab" v-on:click="activetab=1" v-bind:class="[ activetab === 1 ? 'active' : '' ]">DESCRIPTION</a>
            <a class="tabs__tab" v-on:click="activetab=2" v-bind:class="[ activetab === 2 ? 'active' : '' ]">VIDEO</a>
            <a class="tabs__tab" v-on:click="activetab=3" v-bind:class="[ activetab === 3 ? 'active' : '' ]">SIZE &amp; SPECS</a>
            <a class="tabs__tab" v-on:click="activetab=4" v-bind:class="[ activetab === 4 ? 'active' : '' ]">DELIVERY &amp; RETURNS</a>
            <a class="tabs__tab" v-on:click="activetab=5" v-bind:class="[ activetab === 5 ? 'active' : '' ]">REVIEWS</a>
        
        </div>

        <div class="tab-container__tabs-content">

            <div v-if="activetab === 1" class="tabs-content__tabcontent">
                <h4 class="tabcontent__headline">NUNC EGESTAS POSUERE ENIM, EU MAXIMUS ERAT POSUERE EGET</h4>
                <p class="tabcontent__text">Sed ut mi mollis, consequat nulla lacinia, hendrerit turpis. Nulla sapien magna, interdum quis pretium nec, pharetra at felis. Curabitur dictum sapien est, eget ultricies turpis porta vel. 
                Nam suscipit nec lacus sed imperdiet. Vestibulum a purus risus. Nulla et dictum augue, nec efficitur mi. Nam sit amet pretium elit. Aliquam congue, 
                ligula id vehicula vestibulum, orci ex vulputate lacus, ac malesuada elit dolor eget ex. Sed quis aliquet risus, ut cursus lectus. In eget lorem tellus.<br><br>
                Quisque eleifend varius nisi nec sagittis. Nulla ullamcorper imperdiet justo, ut venenatis purus lobortis ut. Nunc sagittis urna et hendrerit sodales. 
                Nunc molestie risus nec fringilla lacinia. Nulla facilisi. Etiam neque velit, tristique eget sollicitudin eget, placerat at metus. Proin dictum lobortis velit, id suscipit orci faucibus ut. Aliquam erat volutpat. 
                Vivamus feugiat justo in diam placerat, id dignissim elit auctor. Vestibulum scelerisque sem et lobortis ultricies. Morbi suscipit nulla urna. 
                Suspendisse potenti. Nullam varius quam sed nisl dignissim, vel faucibus ipsum blandit. Vivamus at suscipit augue. Nam finibus gravida lorem eu viverra. 
                Praesent rhoncus imperdiet ultricies. Nullam pretium cursus augue auctor vulputate. Quisque a convallis diam commodo eget diam id, eleifend dictum libero. 
                Etiam varius, nisi vel dignissim sodales, enim dui posuere mauris, in aliquet lorem eros eget neque.</p>
            </div>

            <div v-if="activetab === 2" class="tabs-content__tabcontent">
                VIDEO
            </div>

            <div v-if="activetab === 3" class="tabs-content__tabcontent">
                SIZE &amp; SPECS
            </div>

            <div v-if="activetab === 4" class="tabs-content__tabcontent">
                DELIVERY &amp; RETURNS
            </div>

            <div v-if="activetab === 5" class="tabs-content__tabcontent">
                REVIEWS
            </div>

        </div>

    </div>
</template>


<script>

export default {
    name: 'ProductTab',

    data: function() {
        return {
            activetab: 1
        }
    }
}
</script>


<style scoped lang="scss">

  @import "../../styles/utilities/mixins.scss";
  @import "../../styles/utilities/vars.scss";

  .tab-container {
    @include grid-item-position(1, -1, 2, 3);

    @include media-query(small) {
      width: $width-small;
    }

      .tab-container__tabs {
        display: flex;
        background-color: $color-lightgrey;
        height: 50px;
        font-family: $font-sec;

        @include media-query(small) {
          @include flexcolumn;
          height: 200px;
        }

          .tabs__tab {
            height: 100%;
            cursor: pointer;
            @include flexrow-cv;
            padding: 0px 20px 0px 20px;
            white-space: nowrap;
            user-select: none;

            &:hover {
              color: $color-cyan;
            }

            &.active {
              color: $color-white;
              background-color: $color-darkgrey;
              cursor: default;
            }    
          }
      }

      .tab-container__tabs-content {
        padding: 20px 10px 0px 10px;

        .tabs-content__tabcontent {

          .tabcontent__headline {
            margin-bottom: 15px;
            color: $color-darkgrey;
          }
        }
      }
  }

</style>
