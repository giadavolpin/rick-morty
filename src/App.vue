<template>
  <AppHeader />
  <main>
    <AppSearch />
    <CharacterList />
  </main>
</template>

<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppSearch from './components/AppSearch.vue';
import CharacterList from './components/CharacterList.vue';

export default {
  components: {
    AppHeader,
    AppSearch,
    CharacterList
  },
  data() {
    return {
      apiURL: 'https://rickandmortyapi.com/api/character',
      CharacterList: []

    }
  },
  methods: {
    getCharacters() {
      axios.get(this.apiURL).then(
        () => {
          console.log(res.data)
        },
      )
    }
  },
  created() {
    this.getCharacters()
  }
}
</script>

<style lang="scss" scoped>

</style>