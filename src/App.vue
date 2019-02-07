<template>
  <div id="app">
  </div>
</template>

<!-- /////////////////////////////////////////////////////////////////////// -->

<script>
export default {
  name: 'App',
  data() {
    return {
      categories: [
        {
          name: 'Tours',
          slug: 'tours',
          children: [
            {
              name: 'Restaurants',
              slug: 'restaurants',
            },
            {
              name: 'Houses',
              slug: 'houses',
            },
            {
              name: 'Hotels',
              slug: 'hotels',
            },
            {
              name: 'Apartments',
              slug: 'apartments',
            },
          ],
        },
        {
          name: 'Design',
          slug: 'design',
        },
        {
          name: 'Landscaping',
          slug: 'landscaping',
          children: [
            {
              name: 'Plants',
              slug: 'plants',
              children: [
                {
                  name: 'Trees',
                  slug: 'trees',
                },
                {
                  name: 'Succulents',
                  slug: 'succulents',
                },
                {
                  name: 'Grass',
                  slug: 'grass',
                },
              ],
            },
            {
              name: 'Flower Beds & Specialty Gardens',
              slug: 'flower-beds-specialty-gardens',
            },
          ],
        },
      ],
    }
  },
}
</script>

<!-- /////////////////////////////////////////////////////////////////////// -->

<style>
</style>
