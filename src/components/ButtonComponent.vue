<template>
  <div class="text-center cursor-pointer">
    <v-menu data-app offset-y>
        <template v-slot:activator="{ on, attrs }">
            <v-btn data-app
            color="#0652DD"
            dark
            v-bind="attrs"
            v-on="on"
            >
                Language
            </v-btn>
        </template>
        <v-list data-app>
            <v-list-item data-app
            @click="changelg"
            v-for="(item, index) in items" :key="index"
            >
            <v-list-item-title data-app>{{ item.title }}</v-list-item-title>
            </v-list-item>
        </v-list>
    </v-menu>
  </div>
</template>

<script>
export default {
    name: "ButtonComponent",
    methods: {
        changelg() {
            location.reload()
        }
    },

    data: () => ({
        items: [
            { title: 'EN' },
            { title: 'CN' },
        ],
    }),
}
</script>

<style>

</style>