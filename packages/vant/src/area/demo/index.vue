<script setup lang="ts">
import VanArea from '..';
import { ref } from 'vue';
import { areaList } from '@vant/area-data';
import { areaListEn } from './area-en';
import { useTranslate } from '../../../docs/site';

const t = useTranslate({
  'zh-CN': {
    title2: '控制选中项',
    title3: '配置显示列',
    title4: '配置列占位提示文字',
    columnsPlaceholder: ['省份', '城市', '区县'],
    areaList,
  },
  'en-US': {
    title2: 'Model Value',
    title3: 'Columns Number',
    title4: 'Columns Placeholder',
    columnsPlaceholder: ['Province', 'City', 'County'],
    areaList: areaListEn,
  },
});

const value = ref('330302');
</script>

<template>
  <demo-block card :title="t('basicUsage')">
    <van-area :title="t('title')" :area-list="t('areaList')" />
  </demo-block>

  <demo-block card :title="t('title2')">
    <van-area v-model="value" :title="t('title')" :area-list="t('areaList')" />
  </demo-block>

  <demo-block card :title="t('title3')">
    <van-area :title="t('title')" :area-list="t('areaList')" :columns-num="2" />
  </demo-block>

  <demo-block card :title="t('title4')">
    <van-area
      :title="t('title')"
      :area-list="t('areaList')"
      :columns-placeholder="t('columnsPlaceholder')"
    />
  </demo-block>
</template>
