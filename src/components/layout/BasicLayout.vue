<template>
  <div class="common-layout">
    <el-container class="layout-container">
      <!-- 左侧侧边栏 -->
      <el-aside class="left-aside">
        <div class="aside-content">
          <AssetDisplayModule />
        </div>
      </el-aside>

      <!-- 主体部分 -->
      <el-main class="main-content">
        <div class="strategy-section">
          <!-- 策略选择和详情 -->
          <StrategyExecution />
        </div>
        <div class="result-section">
          <!-- 策略执行结果 -->
          <StrategyExecutionResult />
        </div>
      </el-main>

      <!-- 右侧侧边栏 -->
      <el-aside class="right-aside">
        <div class="aside-content">
          <!-- 资产对比分析模块 -->
          <AssetComparisonAnalysis />
        </div>
      </el-aside>
    </el-container>
  </div>
</template>

<script>
import AssetDisplayModule from '../AssetDisplayModule.vue';
import StrategyExecution from '../basic/StrategyExecution.vue'; // 引入策略选择组件
import StrategyExecutionResult from '../basic/StrategyExecutionResult.vue'; // 引入策略执行结果组件
import AssetComparisonAnalysis from '../basic/AssetComparisonAnalysis.vue';

export default {
  name: 'BasicLayout',
  components: {
    AssetDisplayModule,
    StrategyExecution,
    StrategyExecutionResult,
    AssetComparisonAnalysis,
  },
};
</script>

<style scoped>
.common-layout {
  width: 100%;
  height: 100vh; /* 使布局高度铺满整个视窗 */
  display: flex;
  flex-direction: column;
}

.layout-container {
  height: 100%; /* 使容器高度铺满父容器 */
  display: flex;
  flex: 1;
}

/* 左侧侧边栏 */
.left-aside {
  background-color: #f5f5f5; /* 侧边栏背景色 */
  padding: 20px; /* 侧边栏内边距 */
  flex: 0.9; /* 左侧侧边栏占据 1 份 */
  overflow-y: auto; /* 添加垂直滚动条 */
}

.aside-content {
  height: 100%; /* 占据整个侧边栏高度 */
  display: flex;
  flex-direction: column;
  gap: 20px; /* 组件之间的间距 */
}

/* 主体部分 */
.main-content {
  background-color: #ffffff; /* 主体背景色 */
  padding: 20px; /* 主体内边距 */
  flex: 1.5; /* 主体部分占据 1 份 */
  display: flex;
  flex-direction: column;
  gap: 20px; /* 组件之间的间距 */
}

.strategy-section,
.result-section {
  flex: 1; /* 每个部分占据相等的高度 */
  background-color: #ffffff; /* 背景色 */
  padding: 20px; /* 内边距 */
  border-radius: 4px; /* 圆角 */
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1); /* 阴影 */
}

/* 右侧侧边栏 */
.right-aside {
  background-color: #f5f5f5; /* 侧边栏背景色 */
  padding: 20px; /* 侧边栏内边距 */
  flex: 1; /* 右侧侧边栏占据 1 份 */
  overflow-y: auto; /* 添加垂直滚动条 */
}
</style>