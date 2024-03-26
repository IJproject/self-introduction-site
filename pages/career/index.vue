<script setup>
const CAREER_TIMELINE_ITEMS = [
  {
    id: "test",
    icon: "mdi-school-outline",
    color: "primary",
    start_date: "2018/04",
    end_date: "2021/03",
    title: "愛知県立半田高等学校",
    description:
      "説明あああああああああ説明あああああああああ説明あああああああああ",
  },
];
</script>

<template>
  <v-container>
    <h1>タイトル</h1>
    <section>
      <h2>自己紹介</h2>
      <v-card class="elevation-2">
        <v-card-text> こんにちは。私は〇〇と申します。 </v-card-text>
      </v-card>
    </section>
    <section>
      <h2>保有資格</h2>
      <v-card class="elevation-2">
        <v-card-text> こんにちは。私は〇〇と申します。 </v-card-text>
      </v-card>
    </section>
    <section>
      <h2>経歴</h2>
      <v-timeline>
        <v-timeline-item
          v-for="item in CAREER_TIMELINE_ITEMS"
          :key="item.id"
          :icon="item.icon"
          :dot-color="item.color"
          fill-dot
          side="start"
        >
          <template #opposite>
            <span>
              {{ item.start_date }}<br />
              〜{{ item.end_date }}
            </span>
          </template>
          <v-card class="elevation-2">
            <v-card-title class="text-h5">
              {{ item.title }}
            </v-card-title>
            <v-card-text>{{ item.description }}</v-card-text>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </section>
  </v-container>
</template>
