<template lang="pug">
form.form-horizontal(@submit='submitForm')
  .form-group
    .col-3
      label.form-label Заголовок
    .col-9
      input.form-input(
        type='text',
        v-model='title',
        placeholder='Введите заголовок...'
      )
  .form-group
    .col-3
      label.form-label Содержание
    .col-9
      textarea.form-input(
        v-model="body",
        rows=8,
        placeholder='Введите содержание...'
      )
  .form-group
    .col-3
    .col-9
      button.btn.btn-primary(type='submit') Добавить
</template>

<script>
export default {
  name: 'create-note',
  data () {
    return {
      title: '',
      body: ''
    }
  },
  methods: {
    submitForm (event) {
      this.createNote()
      // Т.к. мы уже отправили запрос на создание заметки строчкой выше,
      // нам нужно теперь очистить поля title и body
      this.title = ''
      this.body = ''
      // preventDefault нужно для того, чтобы страница
      // не перезагружалась после нажатия кнопки submit
      event.preventDefault()
    },
    createNote () {
      // Вызываем действие `createNote` из хранилища, которое
      // отправит запрос на создание новой заметки к нашему API.
      this.$store.dispatch('createNote', {
        title: this.title,
        body: this.body
      })
    }
  }
}
</script>
