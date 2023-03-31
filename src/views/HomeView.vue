<template>
  <div class="home"  style="width: 100%;padding-left: 10px">
    <!--  上下10px 左右0    -->
    <div style="margin: 10px 0">
      <el-button type="primary">主要按钮</el-button>
      <el-button type="success">成功按钮</el-button>
      <el-button type="info">信息按钮</el-button>

   </div>
              <!--  搜索按钮 -->
    <div style="margin: 10px 0">
      <el-input v-model="search" placeholder="请输入内容" style="width: 20%" ></el-input>
      <el-button type="primary" style="margin-left: 5px">主要按钮</el-button>
    </div>
    <el-table
        :data="tableData"
        stripe
       >
     <!--   sortable排序   -->
      <el-table-column
          prop="date"
          label="日期"
          sortable
          >
      </el-table-column>
      <el-table-column
          prop="name"
          label="姓名"
         >
      </el-table-column>
      <el-table-column
          prop="address"
          label="地址">
      </el-table-column>
      <el-table-column
          fixed="right"
          label="操作"
          width="100">
        <template slot-scope="scope">
          <el-button @click="handleClick(scope.row)" type="text" >编辑</el-button>
          <el-popconfirm
              title="数据确定删除吗？"
          >
            <el-button slot="reference" type="text" style="padding: 5px">删除</el-button>
          </el-popconfirm>

        </template>
      </el-table-column>
    </el-table>
    <!--    分页  -->
    <div style="margin: 10px 0">
    <el-pagination
        @size-change="handleSizeChange"
        @current-change="handleCurrentChange"
        :current-page="currentPage4"
        :page-sizes="[100, 200, 300, 400]"
        :page-size="100"
        layout="total, sizes, prev, pager, next, jumper"
        :total="400">
    </el-pagination>
      </div>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
  components: {},
  methods: {
    handleClick(row) {
      console.log(row);
    },
    handleSizeChange(val) {
      console.log(`每页 ${val} 条`);
    },
    handleCurrentChange(val) {
      console.log(`当前页: ${val}`);
    }
  },
  data() {
    return {
      search: '',
      currentPage1: 5,
      currentPage2: 5,
      currentPage3: 5,
      currentPage4: 4,
      tableData: [{
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1517 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1519 弄'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1516 弄'
      }]
    }
  }

}
</script>
