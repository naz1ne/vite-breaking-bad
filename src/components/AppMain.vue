<script>
import { store } from '../store.js'
import SingleCard from './SingleCard.vue'
import CharactersLength from './CharactersLength.vue'
import CategorySelector from './CategorySelector.vue'

export default {
      name: 'AppMain',
      components: {
            SingleCard,
            CharactersLength,
            CategorySelector
      },
      data() {
            return {
                  store
            }
      },
      methods: {
            selectCategory() {
                  let categoryUrl = store.API_URL;
                  /* console.log(categoryUrl); */
                  if (this.store.selectCategory !== 'All') {
                        const selectSeries = this.store.selectCategory
                        /* console.log(this.store.selectCategory); */
                        categoryUrl = `${this.store.API_URL}?category=${selectSeries}`
                  }

                  store.callApi(categoryUrl)
            }
      }
}
</script>
<template>
      <main>
            <div class="container">
                  <CategorySelector @selectCategory="selectCategory()" />
                  <div class="row row-cols-5">
                        <CharactersLength />
                        <SingleCard />
                  </div>
            </div>
      </main>
</template>
<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;

.select_category {
      max-width: 300px;
      width: fit-content;
}

.row {
      background-color: $light;
      padding: 2rem;


}
</style>