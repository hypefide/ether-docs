<template>
  <Layout>
    <div v-html="$page.doc.content"/>
  </Layout>
</template>

<page-query>
query Doc ($path: String!) {
  doc: doc (path: $path) {
    title,
    content
  }
}
</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.doc.title
    }
  }
}
</script>