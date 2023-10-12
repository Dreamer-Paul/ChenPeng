<template>
  <a-row :gutter="[16, 16]">
    <a-col :span="12">
      <a-card title="风扇设备控制" :bordered="false">
        <a-row class="item-row">
          <a-col :span="8">
            室内温度：{{1}}°C
          </a-col>
          <a-col :span="8">
            室内湿度：{{1}}%
          </a-col>
          <a-col :span="8">
            二氧化碳浓度：{{1}}ppm
          </a-col>
        </a-row>
        <a-row class="item-switch">
          <a-col :span="12">
            风扇开关
          </a-col>
          <a-col :span="12">
            关
            <a-switch v-model:checked="state.fanEnabled" />
            开
          </a-col>
        </a-row>
      </a-card>
    </a-col>
    <a-col :span="12">
      <a-card title="水泵设备控制" :bordered="false">
        <a-row class="item-row">
          <a-col :span="24">
            土壤湿度：{{1}}%
          </a-col>
        </a-row>
        <a-row class="item-switch">
          <a-col :span="12">
            水泵开关
          </a-col>
          <a-col :span="12">
            关
            <a-switch v-model:checked="state.pumpEnabled" />
            开
          </a-col>
        </a-row>
      </a-card>
    </a-col>
    <a-col :span="12">
      <a-card title="灯设备控制" :bordered="false">
        <a-row class="item-row">
          <a-col :span="24">
            光照强度：{{1}} Lux
          </a-col>
        </a-row>
        <a-row class="item-switch">
          <a-col :span="12">
            灯开关
          </a-col>
          <a-col :span="12">
            关
            <a-switch v-model:checked="state.lightEnabled" />
            开
          </a-col>
        </a-row>
      </a-card>
    </a-col>
    <a-col :span="12">
      <a-card title="蜂鸣器设备控制" :bordered="false">
        <a-row class="item-row">
          <a-col :span="24">
            传感器数据正常，暂无报警信息！
          </a-col>
        </a-row>
        <a-row class="item-switch">
          <a-col :span="12">
            蜂鸣器开关：
          </a-col>
          <a-col :span="12">
            关
            <a-switch v-model:checked="state.buzzerEnabled" />
            开
          </a-col>
        </a-row>
      </a-card>
    </a-col>
  </a-row>
</template>
<style scoped>
.item-row {
  border: 1px solid #ccc;
  border-radius: 1em;
  padding: 1em;
  font-weight: bold;
  margin-bottom: 2em;
  text-align: center;
}

.item-switch {
  text-align: center;
}
</style>
<script lang="ts" setup>
import { reactive } from 'vue';

const state = reactive({
  fanEnabled: true,
  pumpEnabled: false,
  lightEnabled: false,
  buzzerEnabled: false,
});
</script>
