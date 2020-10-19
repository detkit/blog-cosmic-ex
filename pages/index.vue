<template>
  <div class="container flex flex-col">
    <h1>Nuxt-full-Site</h1>
    <div v-for="obj in getObjects.objects" :key="obj.title">
      <div class="border-solid my-10 p-10 bg-green-200">
        <nuxt-link :to="'/blog/' + obj.slug">
          <div class="text-6xl">{{ obj.title }}</div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import getObjects from "~/queries/getObjects";
export default {
  apollo: {
    getObjects: {
      prefetch: true,
      query: getObjects
    }
  }
};
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
