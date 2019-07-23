<template lang="pug">
  .layout
    header.header
      b
        g-link(to="/") {{ $static.metaData.siteName }}
      nav.nav
        g-link(class="nav__link" to="/docs") Docs
        a(class="nav__link" href="https://github.com/hypefide/ether" target="_blank") GitHub
    slot
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<style>
.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}
</style>
