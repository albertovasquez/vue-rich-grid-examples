<template>
  <div id="app">
      <rich-grid :options="grid" :data="rows">
          <template slot="body" slot-scope="row"><strong>{{row.data.title}}</strong><br/>{{row.data.body}}</template>
      </rich-grid>
  </div>
</template>

<script>
import richGrid from 'vue-rich-grid'
export default {
  name: 'app',
  components: {
      'rich-grid': richGrid
  },
  data () {
    return {
        rows: [{
                userId: 1,
                id: 1,
                title: "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
                body: "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto",
            },
            {
                userId: 1,
                id: 2,
                title: "qui est esse",
                body: "est rerum tempore vitae sequi sint nihil reprehenderit dolor beatae ea dolores neque fugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis qui aperiam non debitis possimus qui neque nisi nulla",
            },
        ],
        grid: {
            noData: 'No data found',
            baseParams: {
            },
            columns: [{
                id : "id",
                width: 40,
                sortable: true,
                text: 'Id',
                align:"left",
            }, {
                id : "body",
                text: 'Body',
                align:"left",
            }],
        },
    }
  }
}
</script>

<style>
    body {
        margin: 200px;
    }
</style>
