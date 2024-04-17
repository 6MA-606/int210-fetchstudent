<script>
const API_URL = `http://lvm00000.sit.kmutt.ac.th:9000/api/students`

export default {
  data: () => ({
    student: null
  }),

  created() {
    // fetch on init
    this.fetchData()
  },

  methods: {
    async fetchData() {
      const url = `${API_URL}`
      this.student = await (await fetch(url)).json()
    }
  }
}
</script>

<template>
  <h1>Fetch Students from API</h1>

  <p>{{ student }}</p>
</template>
