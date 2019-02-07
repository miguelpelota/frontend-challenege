<template>
  <div id="app">
    <h1>Welcome to the Leaf Group Store!</h1>
    <h3>Please hover over our categories to see what is available.</h3>
    <ol>
      <li
        class="main-category-text" 
        v-for="category in categories" 
        :key="category.name"
        @mouseover="shownChildren = category.name" 
        @mouseout="shownChildren = ''"
      >
        {{ category.name }}
        <ol>
          <li 
            v-for="child in category.children" 
            :key="child.name" 
            v-show="shownChildren === category.name"
            @mouseover="shownSecondChildren = child.name" 
            @mouseout="shownSecondChildren = ''"
          >
            {{ child.name }}
            <ol>
              <li 
                class="hover-color-blue second-child-text"
                v-for="secondChild in child.children" 
                :key="secondChild.name"
                v-show="shownSecondChildren === child.name"
              >
                {{ secondChild.name }}
              </li>
            </ol>
          </li>
        </ol>
      </li>
    </ol>
  </div>
</template>

<!-- /////////////////////////////////////////////////////////////////////// -->

<script>
export default {
  name: 'App',
  data() {
    return {
      shownChildren: '',
      shownSecondChildren: '',
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
  #app {
    margin: 0 auto;
    text-align: center;
    width: 50%;
  }

  h1 {
    background-color: #06A5CF;
    color: white;
  }

  ol {
    padding-left: 0;
  }

  li {
    background-color: #06A5CF;
    border: 1px solid #06A5CF;
    color: white;
    font-weight: normal;
    margin: 20px 0;
    padding: 10px 20px;
    text-align: left;
    list-style-type: none;
  }

  li:hover {
    background-color: white;
    color: #06A5CF;
    font-weight: bold;
  }

  .main-category-text,
  .second-child-text {
    font-weight: bold;
  }

</style>
