<template>
  <div class="user-info">
		<div class="form-line">
		  <span class="label">用户名：</span>
		  <span class="text">{{userForm.username}}</span>
		</div>
    <div class="form-line">
      <span class="label">昵 称：</span>
      <span class="text">{{userForm.name}}</span>
    </div>
    <div class="form-line">
      <span class="label">电 话：</span>
      <span class="text">{{userForm.mobile}}</span>
    </div>
    <div class="form-line">
      <span class="label">邮 箱：</span>
      <span class="text">{{userForm.email}}</span>
    </div>
    <a class="btn btn-submit" @click="loadPage('user-center-update')">编辑</a>
  </div>
</template>
<script type="text/ecmascript-6">
  export default {
    data() {
      return {
        userForm: []
      };
    },
    created() {
      this.queryUserInfo();
    },
    methods: {
      queryUserInfo() {
        this.ajax({
          url: `/uac/user/getInformation`,
          success: (res) => {
            if (res.code === '200') {
              this.userForm = res.data;
            }
          }
        });
      }
    },
    components: {}
  };
</script>
<style rel="stylesheet/scss" lang="scss">
</style>
