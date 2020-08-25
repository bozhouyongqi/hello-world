<template>
  <div class="table-container">
    <el-table
        :data="tableData">
      <el-table-column
        prop="name"
        label="姓名"
        width="180">
        <template slot-scope="scope">
            <el-input v-model="scope.row.name" v-on:change="nameChange(scope.$index, scope.row.name)">
                
            </el-input>
        </template>
      </el-table-column>
      <el-table-column
        prop="age"
        label="年龄"
        width="180">
        <template slot-scope="scope">
            <el-input v-model="scope.row.age">
                
            </el-input>
        </template>
      </el-table-column>
      <el-table-column
        prop="address"
        label="地址">
        <template slot-scope="scope">
            <el-input v-model="scope.row.address">
                
            </el-input>
        </template>
      </el-table-column>
    </el-table>
    <button v-on:click="addNew">新增</button>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    /**
     * {
     *      name: '',
     *      age: 12,
     *      address:''
     * }
     */
    return {
        tableData: [
            {}
        ]
    };
  },
  watch: {
  },
  methods: {
      addNew: function() {
        this.tableData.push({});
    },
    nameChange: function(index, name) {
        // 遍历tableData
        for (let i = 0; i < this.tableData.length; i++) {
            if (i === index) {
                continue;
            }
            if (name === this.tableData[i].name) {
                alert('名称相等,请修改....  ')
            }
        }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.table-container {
    width: 80%;
    margin: 0 auto;
}

</style>
