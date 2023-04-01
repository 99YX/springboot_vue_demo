<template>
  <div class="home"  style="width: 100%;padding-left: 10px">
    <!--  上下10px 左右0    -->
    <div style="margin: 10px 0">
      <el-button type="primary" @click="add">新增用户</el-button>
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
          prop="id"
          label="ID"
          sortable
          >
      </el-table-column>
      <el-table-column
          prop="username"
          label="姓名"
         >
      </el-table-column>
      <el-table-column
          prop="nickName"
          label="昵称">
      </el-table-column>

      <el-table-column
          prop="age"
          label="年龄">
      </el-table-column>

      <el-table-column
          prop="nickName"
          label="昵称">
      </el-table-column>

      <el-table-column
          prop="sex"
          label="性别">
      </el-table-column>

      <el-table-column
          prop="address"
          label="地址">
      </el-table-column>

      <el-table-column
          fixed="right"
          label="操作"
          width="180">
        <template slot-scope="scope">
          <el-button @click="handleClick(scope.row)" type="success"   >编辑</el-button>
          <el-popconfirm
              title="数据确定删除吗？"
          >
            <el-button slot="reference" type="danger" style="margin-left:20px "   >删除</el-button>
          </el-popconfirm>

        </template>
      </el-table-column>
    </el-table>
    <!--    分页  -->
    <div style="margin: 10px 0">
    <el-pagination
        @size-change="handleSizeChange"
        @current-change="handleCurrentChange"
        :current-page="currentPage"
        :page-sizes="[5, 10,15, 20]"
        :page-size="5"
        layout="total, sizes, prev, pager, next, jumper"
        :total="400">
    </el-pagination>
      </div>
     <!--  新增用户对框    -->
    <el-dialog
        title="新增用户"
        :visible.sync="dialogVisible"
        width="30%"
       >

         <!--    添加表单 -->
      <el-form ref="form" :model="form" label-width="80px">
        <el-form-item label="用户">
          <el-input v-model="form.username"></el-input>
        </el-form-item>
        <el-form-item label="昵称">
          <el-input v-model="form.nickName"></el-input>
        </el-form-item>
        <el-form-item label="性别">
          <el-radio v-model="form.sex" label="男">男</el-radio>
          <el-radio v-model="form.sex" label="女">女</el-radio>
          <el-radio v-model="form.sex" label="未知">未知</el-radio>
        </el-form-item>
        <el-form-item label="地址">
          <el-input type="textarea" v-model="form.address"></el-input>
        </el-form-item>
      </el-form>
      <span slot="footer" class="dialog-footer">
    <el-button @click="dialogVisible = false">取 消</el-button>
    <el-button type="primary"  @click="save">确 定</el-button>
  </span>
    </el-dialog>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
  components: {},
  methods: {
    /*新增用户*/
    add(){
      /*打开弹窗*/
      this.dialogVisible=true;

      /*清空历史数据*/
      this.form={}

    },
    /*发送前端请求，保存数据*/
    save(){

      this.dialogVisible=false;
    },
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
      form:{},
      dialogVisible: false,
      total:'',
      search: '',

      currentPage: 4,
      tableData: []
    }
  }

}
</script>
