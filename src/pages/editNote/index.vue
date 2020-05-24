<template>
  <div class="editNoteBox">
    <van-cell>
      <view slot="title" class="editTitle">
        <span @click="cacelEdit" class="editCacel">取消</span>
        <van-button plain color="#a64b00" round size="small" @click="handleEdit">发表</van-button>
      </view>
    </van-cell>
    <!-- 输入内容 -->
    <div class="editContent">
      <!-- <van-loading type="spinner"> -->
      <van-field
        :value="editValue"
        type="textarea"
        placeholder="分享好心情"
        :border="false"
        class="editTextarea"
        :autosize="autosizeObj"
        :auto-focus="autoFocus"
        @change="changeValue"
      />
      <!-- </van-loading> -->
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      editValue: '',
      autosizeObj: {
        minHeight: 400
      },
      autoFocus: true
    }
  },
  methods: {
    cacelEdit() {
      const url = '../index/main'
      mpvue.navigateTo({url})
    },
    changeValue(event) {
      this.editValue = event.mp.detail
    },
    handleEdit() {
      const url = '../index/main?content=' + this.editValue
      mpvue.navigateTo({url})
    }
  }

}
</script>

<style scoped>
.editNoteBox {
  height: 100%;
}
.editTitle {
  display: flex;
  flex: 2;
  justify-content: space-between;
}
.editContent {
  /* border: 1px solid #000; */
  height: calc(100% - 52px);
  /* background-color: pink; */
}
.editTextarea {
  /* height: calc(100% - 52px); */
}
</style>
