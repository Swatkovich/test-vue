<template>
  <div :class="`task ${task.done ? 'is-complete' : ''}`">
    <div class="content">
      {{ task.content }}
    </div>
    <div class="button">
      <button @click="toggleDone">
        {{ task.done ? 'Undo' : 'Done' }}
      </button>
      <button class="delete" @click="removeTask">
        Delete
      </button>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/require-prop-types
  props: ['task'],
  methods: {
    toggleDone () {
      this.$store.commit('TOGGLE_TASK', this.task)
    },
    removeTask () {
      this.$store.commit('REMOVE_TASK', this.task)
    }
  }
}
</script>

<style>

</style>
