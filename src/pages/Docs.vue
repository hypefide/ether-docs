<template lang="pug">
  Layout
    h1 Docs
    h2 Guides
    ul
      li(v-for="guide in $page.guides.edges" :key="guide.node.id")
        g-link(:to="guide.node.path") {{ guide.node.name }}
    h2 Elements
    ul
      li(v-for="element in $page.elements.edges" :key="element.node.id")
        g-link(:to="element.node.path") {{ element.node.name }}
</template>

<page-query>
query Docs {
  guides: allDoc(filter: { type: { eq: "guide" } }) {
    edges {
    	node {
        id,
        name,
        path,
        type
      }
  	}
  },
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
