<template>
  <q-page class="flex flex-center">
    <div class="q-pa-md row items-start q-gutter-md">
      <div
      class="my-card"
      v-for="(card, index) in cards"
      :key="index"
      v-if="cards && 5 > 0 && index <= limitationList"
      >
        <img :src="card.card_images[0].image_url">

        <div>
          <div class="text-h6"># {{ card.id }}</div>
          <div class="text-subtitle2">Name: {{ card.name }}</div>
          <div class="text-subtitle2">Race: {{ card.race }}</div>
          <div class="text-subtitle2">Type: {{ card.type }}</div>
          <div class="text-subtitle2">Type: {{ card.desc }}</div>
        </div>

      </div>
    </div>
  </q-page>
</template>

<script>
import { Quasar, QList, QItem, QItemSection, QItemLabel, QIntersection, Loading } from 'quasar'
export default {
  name: 'PageIndex',
  data() {
    return {
      cards: [],
      limitationList: 5
    }
  },
  computed: {
    },
  mounted() {
    this.getCards()
    this.updateLimitation()
  },
  methods: {
    updateLimitation(limitationList){
      if (this.limitationList == 5) {
        this.limitationList = 5
      }else{
        this.limitationList = 5
      }
    },
    getCards() {
      Loading.show()
      this.$axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
      .then((response) => {
        for (let index = 0; index < 5; index++) {
          this.cards = response.data.data
          console.log(this.cards)
        }
      }).catch((error) => {
        console.log(error)
      }).finally(() => {
        Loading.hide()
      })
    },
  }
}
</script>
