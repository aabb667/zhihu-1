<template>
  <div id="app">
    <div class="global-header">
      <a target="_blank" href="https://github.com/ccforward/zhihu" id="forkme_banner"><span>View on GitHub</span></a>
        <div class="wrap">
            <router-link :to="{path: '/'}">
              <img src="data:image/png;base64,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" alt="logo">
            </router-link>
            <p class="power">Powered By Node.js & Vue.js</p>
        </div>
      </div>
    <transition name="fade" mode="out-in">
      <router-view class="view"></router-view>
    </transition>
  </div>
</template>

<style lang="stylus">
  @import './assets/common.styl'
</style>
