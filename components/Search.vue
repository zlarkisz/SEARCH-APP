<template>
  <v-card>
    <v-toolbar color="blue-dark"
      dark>
    <v-text-field
      class="mx-4"
      placeholder="Search"
      label="Search"
      prepend-inner-icon="search"
      solo-inverted
      loading
      @change="console"
    >
      <template v-slot:progress>
        <v-progress-linear
          :value="value"
          color="red"
          absolute
          height="3"
        ></v-progress-linear>
      </template>
    </v-text-field>
  </v-toolbar>
  <v-list subheader>
      <v-list-item
        v-for="item in items"
        :key="item.title"
        @click=""
      >
        <v-list-item-avatar>
          <v-img
            height="200px"
            width=400px
            :src="item.avatar"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
            <v-list-item-title v-html="item.title"></v-list-item-title>
            <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
          </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-card>
</template>

  <script>
export default {
  data () {
    return {
      items: [
        { header: 'Today' },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
          title: 'Brunch this weekend?',
          subtitle: "<span class='text--primary'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?"
        },
        { divider: true, inset: true },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
          title: 'Summer BBQ <span class="grey--text text--lighten-1">4</span>',
          subtitle: "<span class='text--primary'>to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend."
        },
        { divider: true, inset: true },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
          title: 'Oui oui',
          subtitle: "<span class='text--primary'>Sandra Adams</span> &mdash; Do you have Paris recommendations? Have you ever been?"
        },
        { divider: true, inset: true },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
          title: 'Birthday gift',
          subtitle: "<span class='text--primary'>Trevor Hansen</span> &mdash; Have any ideas about what we should get Heidi for her birthday?"
        },
        { divider: true, inset: true },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
          title: 'Recipe to try',
          subtitle: "<span class='text--primary'>Britta Holt</span> &mdash; We should eat this: Grate, Squash, Corn, and tomatillo Tacos."
        }
      ]
    }
  },
  methods: {
    console () {
      console.log('changed!')
    }
  },
  computed: {
    value () {
      return 100
    }
  }
}
</script>