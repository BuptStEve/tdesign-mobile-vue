<template>
  <div class="tdesign-mobile-demo">
    <h1 class="title">Input 输入框</h1>
    <p class="summary">空状态时的占位提示。</p>
    <tdesign-demo-block title="01 类型" summary="基础文本框">
      <t-input label="标签文字" placeholder="请输入文字"></t-input>
    </tdesign-demo-block>
    <tdesign-demo-block summary="必填、选填文本框">
      <t-cell-group>
        <t-input label="标签文字" placeholder="请输入文字" :required="true" />
        <t-input label="标签文字" placeholder="请输入文字 (选填)" />
      </t-cell-group>
    </tdesign-demo-block>
    <tdesign-demo-block summary="无标题文本框">
      <t-input placeholder="请输入文字" />
    </tdesign-demo-block>
    <tdesign-demo-block summary="带提示信息文本框">
      <t-input v-model="text" label="标准五个字" placeholder="请输入文字">
        <template #suffixIcon>
          <info-circle-filled-icon />
        </template>
      </t-input>
    </tdesign-demo-block>
    <tdesign-demo-block summary="长标题文本框">
      <t-input label="超长需换行的标签" placeholder="预设文本"> </t-input>
    </tdesign-demo-block>
    <tdesign-demo-block title="02 状态" summary="文本框状态">
      <t-cell-group>
        <t-input v-model="text1" label="标签文字"></t-input>
        <t-input v-model="text1" label="填写错误" error-message="提示信息" />
        <t-input v-model="text2" label="不可编辑" readonly />
      </t-cell-group>
    </tdesign-demo-block>
    <tdesign-demo-block title="03 特殊类型" summary="特殊文本框类型">
      <div class="input-demo">
        <t-input v-model="passwd" label="输入密码" type="password" clearable />
      </div>
      <div class="input-demo">
        <t-input label="验证码" placeholder="输入验证码">
          <template #suffix>
            <div style="font-size: 16px">XYDZ</div>
          </template>
        </t-input>
      </div>
      <div class="input-demo">
        <t-input placeholder="请输入手机号码">
          <template #suffix>
            <t-button theme="primary" variant="text" size="small" style="height: 24px; padding: 0">发送验证码</t-button>
          </template>
        </t-input>
      </div>
      <div class="input-demo">
        <t-input label="价格" align="right" placeholder="0.00" suffix="元" />
      </div>
      <div class="input-demo">
        <t-input label="数量" align="right" placeholder="填写个数" suffix="个" />
      </div>
    </tdesign-demo-block>
  </div>
  <tdesign-demo-block title="04 规格" summary="文本框尺寸规格">
    <div class="input-demo">
      <t-input label="小规格H48" placeholder="请输入文字" />
    </div>
    <div class="input-demo">
      <t-input label="中规格H56" placeholder="请输入文字" size="medium" />
    </div>
  </tdesign-demo-block>
  <tdesign-demo-block title="05 内容位置" summary="文本框内容位置">
    <div class="input-demo">
      <t-input label="左对齐" placeholder="请输入文字" />
    </div>
    <div class="input-demo">
      <t-input label="居中" placeholder="请输入文字" align="center" />
    </div>
    <div class="input-demo">
      <t-input label="右对齐" placeholder="请输入文字" align="right" />
    </div>
  </tdesign-demo-block>
  <tdesign-demo-block title="04 字数限制" summary="文本框字数限制">
    <div class="input-demo">
      <t-input placeholder="最大输入10个字符" :maxlength="10" />
    </div>
    <div class="input-demo">
      <t-input placeholder="最大输入10个字符，汉字算两个" :maxcharacter="10" />
    </div>
  </tdesign-demo-block>
</template>
<script lang="ts">
import { InfoCircleFilledIcon } from 'tdesign-icons-vue-next';
import { reactive, toRefs, defineComponent } from 'vue';

export default defineComponent({
  components: { InfoCircleFilledIcon },
  setup() {
    const state = reactive({
      text: '',
      text1: '请输入文字',
      text2: '不可编辑的内容',
      text3: '',
      passwd: '12345678',
    });
    const changeText = function (val: string) {
      console.log('change', val);
    };
    return {
      ...toRefs(state),
      changeText,
    };
  },
});
</script>

<style scoped lang="less">
.input-demo {
  margin-bottom: 16px;
}
</style>
