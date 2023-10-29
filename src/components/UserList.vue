<template>
  <div>
    <ul>
      <li>
        
        <h2></h2>
        <p></p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    searchResults: {
      type: Array,
      default: () => [],
    },
  },
};
</script>