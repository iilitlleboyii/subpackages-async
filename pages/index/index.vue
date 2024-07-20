<template>
  <view>
    <view>主包</view>
    <button @click="go">Go</button>
  </view>
</template>

<script setup>
loadMpPackage(
  'packages',
  () => {
    const hello = loadMpPackageModule('packages/static/utils/index.js')
    console.log(hello.default)

    const api = loadMpPackageModule('packages/static/api/index.js')

    global[Symbol.for('api')] = api
  },
  ({ mod, errMsg }) => {}
)

function go() {
  uni.navigateTo({ url: '/pages/home/index' })
}
</script>

<style lang="scss" scoped></style>
