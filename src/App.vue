<template>
  <div id="app">
      <rich-grid :options="options" :columns="columns" :data="rows">
          <template slot="body" slot-scope="row"><strong>{{row.data.title}}</strong><br/>{{row.data.body}}</template>
      </rich-grid>
  </div>
</template>

<script>
import richGrid from 'vue-rich-grid'
import axiosMixin from 'vue-rich-grid-axios';

// we can add mixins to our richgrid
// before Vue attatches your component
richGrid.mixins = [axiosMixin];

export default {
  name: 'app',
  components: {
      'rich-grid': richGrid
  },
  data () {
    return {
        rows: [
            {
                userId: 1,
                id: 1,
                title: "1 - sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
                body: "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto",
            },
            {
                userId: 1,
                id: 2,
                title: "2 - qui est esse",
                body: "est rerum tempore vitae sequi sint nihil reprehenderit dolor beatae ea dolores neque fugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis qui aperiam non debitis possimus qui neque nisi nulla",
            },{
                userId: 1,
                id: 3,
                title: "3 - sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
                body: "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto",
            },
            {
                userId: 1,
                id: 4,
                title: "4 - qui est esse",
                body: "est rerum tempore vitae sequi sint nihil reprehenderit dolor beatae ea dolores neque fugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis qui aperiam non debitis possimus qui neque nisi nulla",
            },{
                userId: 1,
                id: 11,
                title: "11 - sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
                body: "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto",
            },
            {
                userId: 1,
                id: 6,
                title: "6 - qui est esse",
                body: "est rerum tempore vitae sequi sint nihil reprehenderit dolor beatae ea dolores neque fugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis qui aperiam non debitis possimus qui neque nisi nulla",
            },
        ],
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
        options: {
            noDataText: 'No data found',
            baseParams: {
            },
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
