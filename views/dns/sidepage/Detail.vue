<template>
  <detail
    :list="list"
    :data="data"
    :base-info="baseInfo"
    :extra-info="extraInfo" />
</template>

<script>
export default {
  name: 'DNSDetail',
  props: {
    data: {
      type: Object,
      required: true,
    },
    list: {
      type: Object,
      required: true,
    },
  },
  data () {
    return {
      baseInfo: [
        {
          field: 'records',
          title: '记录值',
        },
        {
          field: 'ttl',
          title: 'TTL',
        },
        {
          field: 'enabled',
          title: '状态',
          formatter: ({ cellValue }) => {
            return <span style={{ color: cellValue ? '#67C23A' : '#F56C6C' }}>{cellValue ? '启用' : '禁用' }</span>
          },
        },
      ],
      extraInfo: [
        {
          title: '其他信息',
          items: [],
        },
      ],
    }
  },
}
</script>
