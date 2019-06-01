<template>
  <div>
    <v-layout class="px-2 pb-2">
      <v-flex xs2>
        <v-btn outline color="indigo" large>新增商品</v-btn>
      </v-flex>
      <v-spacer></v-spacer>
      <v-flex xs2>
        <v-text-field label="搜索" v-model="key" outline append-icon="search"></v-text-field>
      </v-flex>
    </v-layout>
    <v-data-table
      :headers="headers"
      :items="brands"
      :pagination.sync="pagination"
      :total-items="totalBrands"
      :loading="loading"
      class="elevation-1"
    >
      <template slot="items" slot-scope="props">
        <td class="text-xs-center">{{ props.item.id }}</td>
        <td class="text-xs-center">{{ props.item.name }}</td>
        <td class="text-xs-center"><img :src="props.item.image" alt=""></td>
        <td class="text-xs-center">{{ props.item.letter }}</td>
        <td class="text-xs-center">
          <v-btn outline color="error" small>
            <v-icon>remove</v-icon>
          </v-btn>
          <v-btn outline color="info" small>
            <v-icon>edit</v-icon>
          </v-btn>
        </td>
      </template>
    </v-data-table>
  </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: "MyBrand",
        data () {
          return {
            headers: [
              {text: '商品ID', align: 'center', sortable: true, value: 'id'},
              {text: '商品名称', align: 'center', sortable: false, value: 'name'},
              {text: '商品LOGO', align: 'center', sortable: false, value: 'image'},
              {text: '商品首字母', align: 'center', sortable: true, value: 'letter'},
              {text: '操作', align: 'center', sortable: false}
            ],
            brands: [],
            loading: false,
            pagination: {},
            totalBrands: 0,
            key: "",
          }
      },
      created() {
          this.brands = [
            {
              "id": 2032,
              "name": "OPPO",
              "image": "http://img10.360buyimg.com/popshop/jfs/t2119/133/2264148064/4303/b8ab3755/56b2f385N8e4eb051.jpg",
              "letter": "O"
            },
            {
              "id": 2033,
              "name": "飞利浦（PHILIPS）",
              "image": "http://img12.360buyimg.com/popshop/jfs/t18361/122/1318410299/1870/36fe70c9/5ac43a4dNa44a0ce0.jpg",
              "letter": "F"
            },
            {
              "id": 2034,
              "name": "华为（HUAWEI）",
              "image": "http://img10.360buyimg.com/popshop/jfs/t5662/36/8888655583/7806/1c629c01/598033b4Nd6055897.jpg",
              "letter": "H"
            },
            {
              "id": 2036,
              "name": "酷派（Coolpad）",
              "image": "http://img10.360buyimg.com/popshop/jfs/t2521/347/883897149/3732/91c917ec/5670cf96Ncffa2ae6.jpg",
              "letter": "K"
            },
            {
              "id": 2037,
              "name": "魅族（MEIZU）",
              "image": "http://img13.360buyimg.com/popshop/jfs/t3511/131/31887105/4943/48f83fa9/57fdf4b8N6e95624d.jpg",
              "letter": "M"
            }
          ];
          this.totalBrands = 15;

          //去后台查询
        this.loadBrands()
      },
      watch: {
        key(){
          this.pagination.page = 1;
          this.loadBrands()
        },
        pagination: {
          deep:true,
          handler() {
            this.loadBrands();
          }
        }

      },
      methods: {
          loadBrands(){
            this.loading = true,
            this.$http.get("/item/brand/page",{
              params:{
                //搜索条件
                page: this.pagination.page,//当前页
                rows:this.pagination.rowsPerPage,//每页大小
                sortBy: this.pagination.sortBy,//排序字段
                desc:this.pagination.descending,//是否降序
                key:this.key//搜索条件
              }
            }).then(resp => {
              // 将得到的数据赋值给本地属性
              this.brands = resp.data.items;
              this.totalBrands = resp.data.total;
              // 完成赋值后，把加载状态赋值为false
              this.loading = false;
            })
          }
      }
    }
</script>

<style scoped>

</style>
