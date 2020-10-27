<template>
  <div class="bg-add">
    <div class="add">
      <div class="frf">
        <div class="cancle">
          <span></span>
          <span></span>
        </div>
        <form>
          <div class="form-group">
            <input
              type="text"
              class="form-control"
              id="nameInput"
              v-model="employee.name"
              placeholder="Name:"
            />
          </div>
          <div class="form-group">
            <!-- <label for="gmailInput">Email</label> -->
            <input
              type="text"
              class="form-control"
              id="gmailInput"
              v-model="employee.gmail"
              placeholder="Email:"
            />
          </div>
          <div class="form-group">
            <input
              type="text"
              class="form-control"
              pattern=""
              id="phoneInput"
              v-model="employee.phone"
              placeholder="Phone:"
            />
          </div>
          <div class="btn btn-primary" @click="clickSave()">save</div>
          <div class="btn btn-primary" id="close" @click="clickThoat()">Close</div>
        </form>
      </div>
    </div>
  </div>
</template>
<style>
.frf {
        margin: auto;
    border: 1px solid #fff;
    padding: 25px;
    border-radius: 5px;
    position: absolute;
    width: 500px;
    background: #000;
    left: 38%;
    margin-top: -30%;
}
.add {
position: absolute;
    display: flex;
    text-align: center;
    font-size: 20px;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 150%;
    top: 0;
    left: 0;
    opacity: 1;
    background: rgba(0,0,0,0.7);
}
#close{
  margin-left: 25px;
}
</style>
<script>
export default {
  name: "EditEmployee",
  props: {
    employee: Object,
  },
  methods: {
    clickSave() {
      this.$emit("save", this.employee);
    },
    clickThoat() {
      this.$emit("nosave", this.employee);
    },
  },
};
</script>
