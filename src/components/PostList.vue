<template>
  <div>
    <div class="loading" v-if="isLoading">
      <img src="../assets/loading.gif">
    </div>
    <div>
      <ul>
        <li>

        </li>
      </ul>
    </div>
  </div>

</template>

<script>``
export default {
  name: "PostList.vue",
  data() {
    return {
      isLoading: false
    }
  },
  methods: {
    getData() {
      this.$http.get('https://cnodejs.org/api/v1/topics', {
        page: 1,
        limit: 20
      }).then(res=> {
        this.isLoading = false
      }).catch(function (err) {
        console.log(err)
      })
    }
  },
  beforeMount() {
    this.isLoading = true
    this.getData()
  }
}
</script>

<style scoped>

</style>