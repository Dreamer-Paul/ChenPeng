<template>
  <a-layout id="page-home">
    <a-layout-sider v-model:collapsed="collapsed" :trigger="null" collapsible>
      <div class="logo">
        智慧农业监测系统
      </div>
      <a-menu v-model:selectedKeys="selectedKeys" theme="dark" mode="inline">
        <a-menu-item key="/home">
          <user-outlined />
          <span>
            <router-link to="/home">首页</router-link>
          </span>
        </a-menu-item>
        <a-menu-item key="/sensor">
          <video-camera-outlined />
          <span>
            <router-link to="/sensor">传感器</router-link>
          </span>
        </a-menu-item>
        <a-menu-item key="3">
          <upload-outlined />
          <span>nav 3</span>
        </a-menu-item>
      </a-menu>
    </a-layout-sider>
    <a-layout>
      <a-layout-header style="background: #fff; padding: 0">
        <menu-unfold-outlined
          v-if="collapsed"
          class="trigger"
          @click="() => (collapsed = !collapsed)"
        />
        <menu-fold-outlined v-else class="trigger" @click="() => (collapsed = !collapsed)" />
      </a-layout-header>
      <a-layout-content
        :style="{ margin: '24px 16px', minHeight: '280px' }"
      >
        <slot />
      </a-layout-content>
    </a-layout>
  </a-layout>
</template>
<script lang="ts" setup>
import { ref } from 'vue';
import {
  UserOutlined,
  VideoCameraOutlined,
  UploadOutlined,
  MenuUnfoldOutlined,
  MenuFoldOutlined,
} from '@ant-design/icons-vue';
import { useRouter } from 'vue-router';

const router = useRouter();
const selectedKeys = ref<string[]>(['1']);
const collapsed = ref<boolean>(false);
</script>
<style>
#page-home {
  height: 100%;
}
#page-home .trigger {
  font-size: 18px;
  line-height: 64px;
  padding: 0 24px;
  cursor: pointer;
  transition: color 0.3s;
}

#page-home .trigger:hover {
  color: #1890ff;
}

#page-home .logo {
  color: #fff;
  font-weight: bold;
  font-size: 1.2em;
  text-align: center;
  height: 32px;
  margin: 16px;
}

.site-layout .site-layout-background {
  background: #fff;
}
</style>