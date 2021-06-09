<template>
  <div id="root">
    @{{ user.username }} - {{ fullName }}
    <strong>Followers - {{ followers }}</strong>
    <button @click="followUser">Follow</button>
  </div>
</template>

<script>
  export default {
    name: "App",
    data: () => ({
      followers: 0,
      user: {
        id: 1,
        username: "webdevavi",
        firstName: "Avinash",
        lastName: "Sinha",
        email: "savinash2608@gmail.com",
        isAdmin: true
      }
    }),
    watch: {
      followers(newFollowersCount, oldFollowersCount) {
        console.log(`Followers changed from ${oldFollowersCount} to ${newFollowersCount}`)
      }
    },
    computed: {
      fullName() {
        return `${this.user.firstName} ${this.user.lastName}`
      }
    },
    methods: {
      followUser() {
        this.followers++
      }
    },
    mounted() {
      this.followUser()
    }
  }
</script>

<style>
  #root {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }
</style>
