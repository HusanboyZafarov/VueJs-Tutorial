<template>
  <div class="app font-monospace">
    <div class="content">
      <AppInfo :allMoviesCount="movies.length" :favouriteMoviesCount="movies.filter(e => e.favourite).length" />
      <div class="search-panel">
        <SearchPanel />
        <AppFilter />
      </div>

      <MovieList :movies="movies" />
      <MovieAddForm @createMovie="createMovie" />
    </div>
  </div>
</template>

<script>
import AppInfo from '@/components/app-info/AppInfo.vue';
import SearchPanel from '../search-panel/SearchPanel.vue';
import AppFilter from '../app-filter/AppFilter.vue';
import MovieList from '../movie-list/MovieList.vue';
import MovieAddForm from '../movie-add-form/MovieAddForm.vue';

export default {
  components: {
    AppInfo,
    SearchPanel,
    AppFilter,
    MovieList,
    MovieAddForm,
  },
  data() {
    return {
      movies: [
        {
          name: "Omar",
          viewers: 555,
          favourite: false,
          like: true,
        },
        {
          name: "Empire of Osman",
          viewers: 155,
          favourite: false,
          like: false,
        },
        {
          name: "Ertugrul",
          viewers: 355,
          favourite: true,
          like: false,
        },
      ]
    }
  },
  methods: {
    createMovie(item) {
      this.movies.push(item)
    }
  }
}
</script>

<style>
.app {
  height: 100vh;
  color: #000;
}

.content {
  width: 1000px;
  min-height: 700px;
  background: #fff;
  margin: 0 auto;
  padding: 5rem 0;
}

.search-panel {
  margin-top: 2rem;
  padding: 1.5rem;
  background: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px #00000015;
}
</style>