<script setup lang="ts">
const NAVIGATION_ITEMS = [
  {
    id: 1,
    label: "テスト",
    href: "/",
  },
  {
    id: 2,
    label: "About",
    href: "/about",
  },
];
</script>

<template>
  <v-app>
    <v-layout-item class="text-end" model-value position="bottom" size="100">
      <div class="ma-4">
        <v-menu>
          <template v-slot:activator="{ props }">
            <v-btn icon="" size="x-large" color="primary" v-bind="props">
              <v-icon>mdi-open-in-new</v-icon>
              <v-overlay
                activator="parent"
                location-strategy="connected"
                scroll-strategy="close"
              >
                <v-list>
                  <v-list-item v-for="item in NAVIGATION_ITEMS" :key="item.id" :href="item.href">
                    <v-list-item-title>{{ item.label }}</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-overlay>
            </v-btn>
          </template>
        </v-menu>
      </div>
    </v-layout-item>
    <v-container>
      <slot />
    </v-container>
  </v-app>
</template>
