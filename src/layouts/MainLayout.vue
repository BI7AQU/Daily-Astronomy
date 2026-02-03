<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          {{ Title }}
        </q-toolbar-title>

        <div>{{ Release }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
          style="background-color:var(--q-primary);color: #ffffff"
        >
          更多资讯
        </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view/>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import {ref, getCurrentInstance} from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: '浙江省高校天文联盟',
    caption: '793964660',
    icon: 'fa-brands fa-qq',
    link: 'https://qm.qq.com/q/NZxKP7unOG'
  },
  {
    title: '微信公众号',
    caption: '浙天盟',
    icon: 'fa-brands fa-weixin',
    link: 'https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzYzOTMwMDEwMw==&action=getalbum&album_id=4273573083287306248'
  },
  {
    title: '星空飨宴',
    caption: 'Star Parties',
    icon: 'fa-solid fa-star',
    link: 'https://aunu.steveling.cn/'
  },
  {
    title: 'Github仓库',
    caption: 'Daily-Astronomy',
    icon: 'fa-brands fa-github',
    link: 'https://github.com/BI7AQU/Daily-Astronomy'
  },
]



// 访问全局属性
const instance = getCurrentInstance();
const config = instance.appContext.config.globalProperties.$config;
const Title = config['bookTitle'];
const Release = config['bookRelease'];

const leftDrawerOpen = ref(false)

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>
