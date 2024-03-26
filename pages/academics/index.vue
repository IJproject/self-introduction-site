<script setup>
const ACADEMICS_DATA = [
  {
    id: "physics",
    title: "Physics - 物理学",
    contents: [
      {
        id: "mechanics",
        title: "Mechanics - 力学",
        description: "ここに簡潔な説明文がきます。",
        href: "/academics/physics/mechanics",
      },
      {
        id: "electromagnetism",
        title: "Electromagnetism - 電磁気学",
        description: "ここに簡潔な説明文がきます。",
      },
    ],
  },
  {
    id: "mathematics",
    title: "Mathematics - 数学",
    contents: [],
  },
  {
    id: "informatics",
    title: "Informatics - 情報",
    contents: [],
  },
  {
    id: "others",
    title: "Others - その他",
    contents: [],
  },
];
</script>

<template>
  <div>
    <v-tabs
      bg-color="indigo-darken-2"
      show-arrows
      center-active
      align-tabs="center"
    >
      <v-tab> Physics </v-tab>
      <v-tab> Mathematics </v-tab>
      <v-tab> Informatics </v-tab>
      <v-tab> Others </v-tab>
    </v-tabs>
    <v-container>
      <div>メモ：breadcrumb使う？？</div>
      <h1>タイトル</h1>
      <section v-for="academics in ACADEMICS_DATA" :key="academics.id">
        <h2>{{ academics.title }}</h2>
        <div v-for="item in academics.contents" :key="item.id">
          <h3>{{ item.title }}</h3>
          <p>{{ item.description }}</p>
          <a :href="item.href"> 詳細はこちら </a>
        </div>
      </section>
    </v-container>
  </div>
</template>
