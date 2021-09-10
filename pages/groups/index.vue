<template>
  <div>
    <Header></Header>
    <main>
      <h1 class="page-title">企画一覧</h1>
      <div class="container">
        <div
          class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5 g-3"
        >
          <div v-for="group in groups" v-bind:key="group.name">
            <div class="col">
              <NuxtLink :to="`/groups/${group.id}`" class="card-link">
                <div class="card shadow-sm">
                  <img :src="`/img/${group.id}.png`" :alt="`${group.name}のサムネイル`" class="group-thumbnail" />
                  <div class="card-body">
                    <h4 class="card-title">
                      {{ group.name }}
                    </h4>
                    {{ group.description }}
                  </div>
                </div>
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>
<script>
export default {
  async asyncData({ $content, params }) {
    const groups = await $content("groups").fetch();
    return { groups };
  },
};
</script>
