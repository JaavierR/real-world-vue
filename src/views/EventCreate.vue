<template>
  <div>
    <h1>Create an Event, {{ user.name }}</h1>
    <p>This event was created by {{ user.id }}</p>
    <p>This is a test {{ localComputed }}</p>
    <p>There are {{ catLength }} categories</p>
    <ul>
      <li v-for="cat in categories" :key="cat">{{ cat }}</li>
    </ul>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'

export default {
  // ### 2 METHOD with extra computed properties ###
  computed: {
    localComputed() {
      return this.user.name + ' with an extra computed property'
    },
    ...mapGetters(['catLength']),
    // We use the spread operator
    ...mapState(['user', 'categories'])
  }

  // ### 1 METHOD ###
  // computed: mapState({
  //   // userName: state => state.user.name,
  //   // userID: state => state.user.id,
  //   user: 'user',
  //   // For top level states (i.e. not using dot notation), I could use a string instead.
  //   categories: 'categories'
  // })
}
</script>

<style scoped></style>
