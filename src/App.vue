<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim.lazy="addObj.uname" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.lazy="addObj.age" min="0" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="addObj.sex">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="addPerson">添加/修改</button>
    </div>
    <div>
      <table border="1" cellpadding="10" cellspacing="0">
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="(item, index) in arr" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ item.uname }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.sex }}</td>
          <td>
            <button @click="delPerson(index)">删除</button>
            <button
              @click="editMsg(index), (isEdit = true), (isEditId = index)"
              v-model="isEdit"
            >
              编辑
            </button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      // v-model 绑定收集数据
      isEdit: false,
      isEditId: "",
      addObj: { uname: "", age: "", sex: "" },
      arr: [
        { uname: "小张", age: "20", sex: "男" },
        { uname: "小王", age: "22", sex: "女" },
        { uname: "小李", age: "30", sex: "女" },
      ],
    };
  },
  methods: {
    addPerson() {
      // 添加事件
      if (
        this.addObj.uname.length === 0 ||
        this.addObj.age.length === 0 ||
        this.addObj.sex.length === 0
      )
        return alert("信息不能为空");
      if (this.isEdit) {
        this.arr[this.isEditId] = this.addObj;
      } else {
        this.arr.push(this.addObj);
        this.isEdit = false;
      }
    },
    delPerson(ind) {
      // 删除事件
      this.arr.splice(ind, 1);
    },
    editMsg(ind) {
      // 编辑事件
      console.log(this.arr[ind]);
      this.addObj.uname = this.arr[ind].uname;
      this.addObj.age = this.arr[ind].age;
      this.addObj.sex = this.arr[ind].sex;
    },
  },
};
</script>
