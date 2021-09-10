<template>
  <div>
    <Header />
    <main>
      <div class="container">
        <h1 class="page-title">
          トップページ
        </h1>
        <NuxtLink to="/groups" class="btn btn-primary">
          企画を見る
        </NuxtLink>
      </div>
    </main>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>
