<template>
  <div id="app">
      <rich-grid :options="grid">
          <template slot="id" slot-scope="row">{{row.data.name.first}} {{row.data.name.last}}<br/><strong>{{row.data.email}}</strong></template>
          <template slot="about" slot-scope="row"><small>{{row.data.registered}}</small><br/>{{row.data.about}}</template>
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
        grid: {
            noData: 'No data found',
            baseParams: {
            },
            columns: [{
                id : "id",
                width: 240,
                text: 'Id',
                align:"left",
            }, {
                id : "age",
                text: 'Age',
                width: 40,
                sortable: true,
                align:"right",
            }, {
                id : "about",
                text: 'Comment',
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
