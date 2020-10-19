<template>
  <div class="home">
    <el-row>
      <el-col>
        <el-table ref="table" :show-header="false" :data="tableData"  style="width: 800px;margin:20px auto;">
          <el-table-column  prop="id.value"></el-table-column>
          <el-table-column label prop="name.value"></el-table-column>
          <el-table-column label prop="desc.value"></el-table-column>
          <el-table-column label width="100" align="center">
            <template slot-scope="scope">
              <el-button type="text" @click="toogleExpand(scope.row)">{{scope.row.expansion ? '收起' : '展开'}}</el-button>
              <i :class="[scope.row.expansion ?'el-icon-arrow-up':'el-icon-arrow-down']"></i>
            </template>
          </el-table-column>
          <!-- <el-table-column type="expand" width="1">
            <template slot-scope="props">
              <el-form label-position="left" inline class="demo-table-expand">
                展开内容
              </el-form>
            </template>
          </el-table-column> -->

          <el-table-column type="expand" width="1">
            <template  inline class="demo-table-expand" slot-scope="scope">
               展开内容
            </template>
          </el-table-column>


        </el-table>
      </el-col>
    </el-row>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  data() {
    return {
      popoverInput: '',
      tableData: [{
        id: {
          key: '商品 ID',
          value: '12987122',
          visible: false,
        },
        name: {
          key: '商品名称',
          value: '好滋好味鸡蛋仔',
          visible: false,
        },
        shop: {
          key: '所属店铺',
          value: '王小虎夫妻店',
          visible: false,
        },
        shopId: {
          key: '店铺 ID',
          value: '10333',
          visible: false,
        },
        category: {
          key: '商品分类',
          value: '江浙小吃、小吃零食',
          visible: false,
        },
        address: {
          key: '店铺地址',
          value: '上海市普陀区真北路',
          visible: false,
        },
        desc: {
          key: '商品描述',
          value: '荷兰优质淡奶，奶香浓而不腻',
          visible: false,
        },
      }, {
        id: {
          key: '商品 ID',
          value: '12987123',
          visible: false,
        },
        name: {
          key: '商品名称',
          value: '好滋好味鸡蛋仔',
          visible: false,
        },
        shop: {
          key: '所属店铺',
          value: '王小虎夫妻店',
          visible: false,
        },
        shopId: {
          key: '店铺 ID',
          value: '10333',
          visible: false,
        },
        category: {
          key: '商品分类',
          value: '江浙小吃、小吃零食',
          visible: false,
        },
        address: {
          key: '店铺地址',
          value: '上海市普陀区真北路',
          visible: false,
        },
        desc: {
          key: '商品描述',
          value: '荷兰优质淡奶，奶香浓而不腻',
          visible: false,
        },
      }, {
        id: {
          key: '商品 ID',
          value: '12987124',
          visible: false,
        },
        name: {
          key: '商品名称',
          value: '好滋好味鸡蛋仔',
          visible: false,
        },
        shop: {
          key: '所属店铺',
          value: '王小虎夫妻店',
          visible: false,
        },
        shopId: {
          key: '店铺 ID',
          value: '10333',
          visible: false,
        },
        category: {
          key: '商品分类',
          value: '江浙小吃、小吃零食',
          visible: false,
        },
        address: {
          key: '店铺地址',
          value: '上海市普陀区真北路',
          visible: false,
        },
        desc: {
          key: '商品描述',
          value: '荷兰优质淡奶，奶香浓而不腻',
          visible: false,
        },
      }, {
        id: {
          key: '商品 ID',
          value: '12987125',
          visible: false,
        },
        name: {
          key: '商品名称',
          value: '好滋好味鸡蛋仔',
          visible: false,
        },
        shop: {
          key: '所属店铺',
          value: '王小虎夫妻店',
          visible: false,
        },
        shopId: {
          key: '店铺 ID',
          value: '10333',
          visible: false,
        },
        category: {
          key: '商品分类',
          value: '江浙小吃、小吃零食',
          visible: false,
        },
        address: {
          key: '店铺地址',
          value: '上海市普陀区真北路',
          visible: false,
        },
        desc: {
          key: '商品描述',
          value: '荷兰优质淡奶，奶香浓而不腻',
          visible: false,
        },
      },
      ]
    }
  },
  created() {
    let tableData = this.tableData
    tableData.map(item => {
      item.expansion = false
    })
  },
  methods: {
    toogleExpand(row) {
      let $table = this.$refs.table;
      this.tableData.map(item => {
        if (row.id != item.id) {
          $table.toggleRowExpansion(item, false)
          item.expansion = false
        } else {
          item.expansion = !item.expansion
        }
      })
      $table.toggleRowExpansion(row)
    },
    
    
    confirmChange(item) {
      console.log(item)
      item.value = this.popoverInput
      
    }
  }
}
</script>

<style>
.demo-table-expand {
  font-size: 0;
}
.demo-table-expand label {
  width: 90px;
  color: #99a9bf;
}
.demo-table-expand .el-form-item {
  margin-right: 0;
  margin-bottom: 0;
  width: 50%;
}
</style>