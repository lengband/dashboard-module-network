<template>
  <div>
    <page-header title="NAT网关" :tabs="cloudEnvOptions" :current-tab.sync="cloudEnv" />
    <page-body>
      <nat-list :id="listId" :cloud-env="cloudEnv" />
    </page-body>
  </div>
</template>

<script>
import NatList from './components/List'
export default {
  name: 'NatIndex',
  components: {
    NatList,
  },
  data () {
    return {
      listId: 'NatList',
      cloudEnvOptions: [
        { key: '', label: '全部' },
        { key: 'public_cloud', label: this.$t('cloud_env.public') },
      ],
      cloudEnv: '',
    }
  },
}
</script>
