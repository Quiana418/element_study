<template>
  <div>
    <el-button
      type="primary"
      round
      @click="onClick"
      size="mini"
      icon="el-icon-cold-drink
"
      >主要按钮</el-button
    >
    <hr />
    <i class="el-icon-cherry"></i>
    <i class="el-icon-grape"></i>
    <i class="el-icon-watermelon"></i>
    <i class="el-icon-apple"></i>
    <i class="el-icon-orange"></i>
    <i class="el-icon-cold-drink"></i>

    <hr />
    <!-- 完成状态 如果只想显示true或者false 组件默认不能显示上去 必须要转换 -->
    <el-table :data="tableData" border width="180" height="250">
      <el-table-column prop="date" label="日期" width="180"> </el-table-column>
      <el-table-column prop="name" label="姓名" width="180"> </el-table-column>
      <!-- 如果通过prop显示的数据不理想 可以通过作用域插槽实现 -->
      <el-table-column label="性别" width="180">
        <template v-slot="scope">
          {{ scope.row.sex === 1 ? "男" : "女" }}
        </template>
      </el-table-column>
      <el-table-column prop="address" label="地址"> </el-table-column>

      <el-table-column label="完成状态">
        <template v-slot="scope">
          <el-switch
            v-model="scope.row.done"
            active-color="#13ce66"
            inactive-color="#ff4949"
          >
          </el-switch>
        </template>
      </el-table-column>

      <el-table-column label="完成状态1">
        <template v-slot="scope">
          <el-button type="success" v-if="scope.row.done">完成</el-button>
          <el-button type="danger" v-else>未完成</el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  created () { },
  data () {
    return {
      tableData: [{
        date: '2016-05-02',
        name: '王小虎',
        sex: 0,
        address: '上海市普陀区金沙江路 1518 弄',
        done: false
      }, {
        date: '2016-05-04',
        name: '王小虎',
        sex: 0,
        address: '上海市普陀区金沙江路 1517 弄',
        done: true
      }, {
        date: '2016-05-01',
        name: '王小虎',
        sex: 1,
        address: '上海市普陀区金沙江路 1519 弄',
        done: false
      }, {
        date: '2016-05-03',
        name: '王小虎',
        sex: 1,
        address: '上海市普陀区金沙江路 1516 弄',
        done: true
      }]
    }
  },
  methods: {
    onClick () {
      alert("1111111")
    }
  },
  computed: {},
  watch: {},
  filters: {},
  components: {}
}
</script>

<style scoped lang='less'>
</style>
