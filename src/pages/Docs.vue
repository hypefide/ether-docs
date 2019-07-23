<template lang="pug">
  Layout
    h1 Docs
    h2 Elements
    ul
      li(v-for="element in $page.elements.edges" :key="element.node.id")
        g-link(:to="element.node.path") {{ element.node.name }}
</template>

<page-query>
query Docs {
  elements: allDoc(filter: { layer: { eq: "element" } }) {
    edges {
    	node {
        id,
        name,
        path,
        layer
      }
  	}
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Docs'
  },

  mounted() {
    console.log(this.$page)
  }
}
</script>
