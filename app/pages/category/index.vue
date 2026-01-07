<template>
  <div>
    <v-card
    title="Nutrition"
    flat
    elevation="2"
  >
    <template v-slot:text>
      <v-text-field
        v-model="search"
        label="Search"
        prepend-inner-icon="mdi-magnify"
        variant="outlined"
        hide-details
        single-line
      ></v-text-field>
    </template>

    <v-data-table
      :headers="headers"
      :items="category.data"
      :search="search"
    ></v-data-table>
  </v-card>
  </div>
</template>

<script  setup>
 const search = ref('')
     const { data: category} = await useFetch
     ('http://localhost:1337/api/inventories');

  const headers = [
  
    { key: 'category_name', title: 'category' },
    { key: 'description', title: 'Fat (g)' },
    { key: 'createdAt', title: 'Carbs (g)' },

  ]

</script>

<style>

</style>