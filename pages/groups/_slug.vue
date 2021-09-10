<template>
  <div>
    <Header></Header>
    <main>
      <h1 class="page-title">{{ group.name }}</h1>
      <div class="container">
        <img :src="`/img/${group.id}.png`" alt="">
        <p>{{ group.description }}</p>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    // params.slugには、URLの末尾が入る。/groups/group1 というURLだったら"group1"が返ってきます。
    // params.slugが"group1"なら、以下は/content/groups配下の group1 という名前のファイルを取得するという意味
    const group = await $content(`groups/${params.slug}`).fetch();
    return { group };
  },
};
</script>
