<template>
  <base-side-page
    @cancel="cancelSidePage"
    title="NAT网关"
    icon="res-nat"
    :res-name="data.name"
    :actions="params.actions"
    :current-tab="params.windowData.currentTab"
    :tabs="detailTabs"
    @tab-change="handleTabChange">
    <component :is="params.windowData.currentTab" :res-id="params.resId" :data="data" :list="params.list" :getParams="getParams" />
  </base-side-page>
</template>

<script>
import NatDetail from './Detail'
import Snat from './Snat'
import Dnat from './Dnat'
import SidePageMixin from '@/mixins/sidePage'
import WindowsMixin from '@/mixins/windows'
import Actions from '@/components/PageList/Actions'

export default {
  name: 'NatSidePage',
  components: {
    NatDetail,
    Snat,
    Dnat,
    Actions,
  },
  mixins: [SidePageMixin, WindowsMixin],
  data () {
    return {
      detailTabs: [
        { label: '详情', key: 'nat-detail' },
        { label: 'SNAT', key: 'snat' },
        { label: 'DNAT', key: 'dnat' },
        { label: '操作日志', key: 'event-drawer' },
      ],
    }
  },
  computed: {
    getParams () {
      return null
    },
    data () {
      return this.params.list.data[this.params.resId].data
    },
  },
}
</script>
