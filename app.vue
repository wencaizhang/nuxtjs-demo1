<template>
  <div>
    <NuxtRouteAnnouncer />
    <NuxtWelcome />
  </div>
</template>

<script setup lang="ts">
type Post = {
  title: string;
  id: number;
  like: number;
  download: boolean;
}

const { find } = useStrapi<Post>()

// typed to Course
const response = await find('posts').then(res => {
  console.log("%c 🥪 res", "font-size:18px;color:#ffffff;background:#ffdd4d", res);

}).catch(err => {
  console.log("%c 🍯 err", "font-size:18px;color:#ffffff;background:#3f7cff", err);

})
// console.log("%c 🥑 response", "font-size:18px;color:#ffffff;background:#3f7cff", response);
</script>

<style scoped>

</style>