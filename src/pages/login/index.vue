<template>
    <div>
        <van-field :value="value" placeholder="请输入用户名"></van-field>
        <van-button type="info">按钮</van-button>
    </div>
</template>

<script>
export default {
    data () {
        return {
            value: ''
        }
  }
}
</script>

<style>

</style>
