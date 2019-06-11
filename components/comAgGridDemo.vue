<template>
    <no-ssr >
      <ag-grid-vue
      style="width: 100vw; height: 500px;"
      class="ag-theme-balham"
      :columnDefs="columnDefs"
      :rowData="rowData"
      :defaultColDef="defaultColDef"></ag-grid-vue>
    </no-ssr >
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import { AgGridVue } from "ag-grid-vue";
@Component({
  name: 'ag-grid-demo',
  components:{
    AgGridVue
  }
})
export default class agGridDemo extends Vue{

  columnDefs: any = [
    { headerName: "Make", field: "make" },
    { headerName: "Model", field: "model" },
    { headerName: "Price", field: "price" }
  ]

  rowData: any = [
    { make: "Toyota", model: "Celica", price: 35000 },
    { make: "Ford", model: "Mondeo", price: 32000 },
    { make: "Porsche", model: "Boxter", price: 72000 }
  ]

  defaultColDef: {} = {               
    editable: true          
  }
}
</script>

<style lang="scss">
  @import "~/node_modules/ag-grid-community/dist/styles/ag-grid.css";
  @import "~/node_modules/ag-grid-community/dist/styles/ag-theme-balham.css";
</style>