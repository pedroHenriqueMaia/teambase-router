<template>
  <div class="row">
    <Item 
      v-for="(item, index) in items"
      v-bind:key="index"
      :item="item"
    />
  </div>
</template>

<script>
  import Item from './Item.vue';

  export default {
    data() {
        return {
            type: this.$route.params.type,
            items: []
        };
    },
    watch: {
        "$route": "fetchItems"
    },
    methods: {
        fetchItems() {
            this.items = [];
            this.type = this.$route.params.type;
            let initial_ids = [1, 2, 3, 4]

            for (let i in initial_ids) {
                let id = initial_ids[i];
                fetch(`https://rickandmortyapi.com/api/${this.type}/${id}`, {
                    method: "GET"
                })
                    .then(response => response.json())
                    .then(item => this.items.push(item));
            }
        }
    },
    components: { Item }
}
</script>