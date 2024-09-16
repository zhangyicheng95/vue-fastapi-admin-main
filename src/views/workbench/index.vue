<template>
  <AppPage :show-footer="false">
    <div flex-1>
      <n-card rounded-10>
        <div flex items-center justify-between>
          <div flex items-center>
            <img rounded-full width="60" :src="userStore.avatar" />
            <div ml-10>
              <p text-20 font-semibold>
                {{ $t('views.workbench.text_hello', { username: userStore.name }) }}
              </p>
              <p mt-5 text-14 op-60>{{ $t('views.workbench.text_welcome') }}</p>
            </div>
          </div>
          <n-space :size="12" :wrap="false">
            <n-statistic v-for="item in statisticData" :key="item.id" v-bind="item"></n-statistic>
          </n-space>
        </div>
      </n-card>

      <n-card title="设备" size="small" :segmented="true" mt-15 rounded-10>
        <template #header-extra>
          <!-- <n-button text type="primary" @click="loadMore">{{
            $t('views.workbench.label_more')
          }}</n-button> -->
        </template>
        <div flex flex-wrap gap="24px">
          <n-card
            v-for="item in cardListData"
            :key="item.id"
            class="w-300 cursor-pointer card-shadow"
            hover:card-shadow
            :title="item.name"
            size="small"
          >
            <p op-60>{{ item.identifier }}</p>
          </n-card>
        </div>
      </n-card>
    </div>
  </AppPage>
</template>

<script setup>
import { useUserStore } from '@/store'
import { useI18n } from 'vue-i18n'

const dummyText = 'C4-1A通道压力值存在波动'
const { t } = useI18n({ useScope: 'global' })
const cardListData = computed(() => [
  {
    name: '工区A-C1通道',
    id: 0,
    identifier: 'XUST-0001',
    status: '1',
    onLineTime: '1天08小时21分',
    syncTime: new Date().getTime(),
    errorNum: 10,
    faultRate: 58,
    onLine: 88,
  },
  {
    name: '工区A-C2通道',
    id: 1,
    identifier: 'XUST-0001',
    status: '1',
    onLineTime: '1天08小时21分',
    syncTime: new Date().getTime(),
    errorNum: 10,
    faultRate: 98,
    onLine: 98,
  },
  {
    name: '工区A-C3通道',
    id: 2,
    identifier: 'XUST-0001',
    status: '1',
    onLineTime: '1天08小时21分',
    syncTime: new Date().getTime(),
    errorNum: 10,
    faultRate: 98,
    onLine: 98,
  },
  {
    name: '工区A-C4通道',
    id: 3,
    identifier: 'XUST-0001',
    status: '1',
    onLineTime: '1天08小时21分',
    syncTime: new Date().getTime(),
    errorNum: 10,
    faultRate: 98,
    onLine: 98,
  },
  {
    name: '工区A-C5通道',
    id: 4,
    identifier: 'XUST-0001',
    status: '1',
    onLineTime: '1天08小时21分',
    syncTime: new Date().getTime(),
    errorNum: 10,
    faultRate: 98,
    onLine: 98,
  },
  {
    name: '工区A-C6通道',
    id: 5,
    identifier: 'XUST-0001',
    status: '1',
    onLineTime: '1天08小时21分',
    syncTime: new Date().getTime(),
    errorNum: 10,
    faultRate: 98,
    onLine: 98,
  },
  {
    name: '工区A-C7通道',
    id: 6,
    identifier: 'XUST-0001',
    status: '1',
    onLineTime: '1天08小时21分',
    syncTime: new Date().getTime(),
    errorNum: 10,
    faultRate: 98,
    onLine: 98,
  },
  {
    name: '工区A-C8通道',
    id: 7,
    identifier: 'XUST-0001',
    status: '1',
    onLineTime: '1天08小时21分',
    syncTime: new Date().getTime(),
    errorNum: 10,
    faultRate: 98,
    onLine: 98,
  },
  {
    name: '工区A-C9通道',
    id: 8,
    identifier: 'XUST-0001',
    status: '1',
    onLineTime: '1天08小时21分',
    syncTime: new Date().getTime(),
    errorNum: 10,
    faultRate: 98,
    onLine: 98,
  },
  {
    name: '工区A-C10通道',
    id: 9,
    identifier: 'XUST-0001',
    status: '1',
    onLineTime: '1天08小时21分',
    syncTime: new Date().getTime(),
    errorNum: 10,
    faultRate: 98,
    onLine: 98,
  },
])
const statisticData = computed(() => [
  {
    id: 0,
    label: t('views.workbench.label_number_of_items'),
    value: '25',
  },
  {
    id: 1,
    label: t('views.workbench.label_upcoming'),
    value: '4/16',
  },
  {
    id: 2,
    label: t('views.workbench.label_information'),
    value: '12',
  },
])

const userStore = useUserStore()
async function loadMore() {}
</script>
