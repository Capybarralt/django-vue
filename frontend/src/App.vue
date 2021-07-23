<template lang="pug">
#app
  section.container.grid-960
    .columns
      .column.col-2
      .column.col-8.col-md-12
        header.text-center
          h2 Создать заметку
        create-note
        header.text-center
          h2 Список заметок
        note-list
      .column.col-2
</template>

<script>
import CreateNote from './components/CreateNote'
import NoteList from './components/NoteList'

export default {
  name: 'App',
  components: {
    'create-note': CreateNote,
    'note-list': NoteList
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

@import url(https://fonts.googleapis.com/css?family=Eczar);
@import url(https://fonts.googleapis.com/css?family=Work+Sans);

body {
  font-family: "Work Sans", "Segoe UI", "Helvetica Neue", sans-serif;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Eczar", sans-serif;
  font-size: 10;
}
</style>
