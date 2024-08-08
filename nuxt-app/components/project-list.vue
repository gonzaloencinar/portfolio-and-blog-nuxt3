<template>
  <p class="mb-10">Take a look at my github projects</p>
  <section v-if="pending">Loading...</section>
  <section v-else-if="error">Something went wrong...</section>
  <section v-else>We display the repos!</section>
  <ul class="grid grid-cols-1 gap-4">
    <li
      v-for="repository in repos"
      :key="repository.id"
      class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 font-mono"
    >
      <a :href="repository.html_url" target="_blank"
        ><div class="flex items-center justify-between text-sm">
          <div class="font-semibold">{{ repository.name }}</div>
          <div class="flex items-center">
            {{ repository.stargazers_count }} ⭐️
          </div>
        </div>
        <p class="text-sm">{{ repository.description }}</p>
      </a>
    </li>
  </ul>
</template>

<script setup>
//usamos useFetch de Nuxt que devuelve un composable reactivo
//https://nuxt.com/docs/api/composables/use-fetch

const { error, pending, data } = await useFetch(
  "https://api.github.com/users/gonzaloencinar/repos"
);

//solo queremos los repos que tengan descripción, asi que filtramos la variable reactiva "data":
//utilizamos.sort para ordenar de mas a menos estrellas los repos
const repos = computed(() =>
  data.value
    .filter((repo) => repo.description)
    .sort((a, b) => b.stargazers_count - a.stargazers_count)
);
</script>
