<template>
<div>
    <b-img @click="$bvModal.show('bv-modal-example')"  thumbnail fluid src="https://fastly.hautelookcdn.com/cjn0whlzl03cx0mqi1ngu4or6/personal-double-point-days.gif" v-bind="mainProps" width=150 height=150 rounded="circle" alt="Circle image"></b-img>
    <h3>click me</h3>
    <b-modal id="bv-modal-example" hide-footer centered scrollable size="xl">
      <template slot="modal-title">
        <h2>uNo</h2> 
      </template>
      <div class="row" style="margin-bottom: 10px">
        <div class="col"></div>
        <div class="col">
          <b-card
          title="Lace V-Neck Chiffon Evening Dress"
          img-src="https://n.nordstrommedia.com/id/sr3/61e59a75-0b6a-4a0f-bc56-8ea4d6169388.jpeg"
          img-alt="Image"
          style="max-width: 20rem;"
          img-top
          align="center"
          img-height="350px"
          img-width="70px"
        >
          <b-card-text>
            A lace V-neck overlays a plunging sweetheart neckline on this chiffon gown, featuring an unexpected back cutout and an enchanting floor-sweeping skirt.
          </b-card-text>
          <div class="row">
            <div class="col">
              <b-button href="#" variant="primary">Buy</b-button>
            </div>
            <div class="col">
              <b-button href="#" variant="secondary">Add to cart</b-button>
            </div>
          </div>
        </b-card>
        </div>
        <div class="col">
          <Stt></Stt>
        </div>
        
      </div>


      <b-alert show variant="dark">
        <h3>History</h3>
      </b-alert>

        <div>
          <b-card-group deck>
            <b-card title="Lace Bodice Chiffon Evening Dress" 
              img-src="https://n.nordstrommedia.com/id/sr3/b00d4894-09f2-4aaa-957b-e33eb7aee1ae.jpeg" 
              img-alt="Image" 
              img-top
              img-height="350px"
              img-width="70px"
              >
              <b-card-text>
                Shapely and sophisticated, this day-to-night sheath is cut with a sleek asymmetrical neckline and a flattering fan of pleats at the waist.
              </b-card-text>
              <div slot="footer" class="row">
                <div class="col">
                  <b-button pill>Black color</b-button>
                </div>
                <div class="col">
                  <b-button pill>Evening dress</b-button>
                </div>
                <div class="col">
                  <b-button pill>V-neck</b-button>
                </div>
              </div>
            </b-card>

            <b-card title="Scuba Crepe Sheath Dress" 
              img-src="https://n.nordstrommedia.com/id/sr3/b4b2c855-beb7-4861-8589-a56d1d3909d9.jpeg" 
              img-alt="Image" 
              img-top
              img-height="350px"
              img-width="70px"
              >
              <b-card-text>
                A tonal front tie accentuates the waist of a versatile sheath dress fashioned with flattering seams and a classic V-neck.
              </b-card-text>
              <div slot="footer" class="row">
                <div class="col">
                  <b-button pill>Evening dress</b-button>
                </div>
                <div class="col">
                  <b-button pill>V-neck</b-button>
                </div>
              </div>
            </b-card>

            <b-card title="Lace Midi Dress" 
              img-src="https://n.nordstrommedia.com/id/sr3/8fcbf1f6-a5ab-49ac-abdd-bb0c847a4145.jpeg" 
              img-alt="Image" 
              img-top
              img-height="350px"
              img-width="70px"
              >
              <b-card-text>
                Sweet, playful and party-ready, this lace midi-length dress has slender straps and an airy silhouette that's perfect for twirling in the sun.
              </b-card-text>
              <div slot="footer" class="row">
                <div class="col">
                  <b-button pill>V-neck</b-button>
                </div>
              </div>
            </b-card>
          </b-card-group>
        </div>


      <b-button class="mt-3" block @click="$bvModal.hide('bv-modal-example')">Close Me</b-button>

    </b-modal>
</div>
</template>

<script>

import Stt from './Stt.vue'

export default {
  name: 'Recs',
  props: {
    msg: String
  },
  components: {
    Stt
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
