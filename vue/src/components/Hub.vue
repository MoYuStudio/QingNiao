<template>
    <div class="layout-container-demo" style="height: 100vh;">
      <el-container>
        <el-aside width="200px">
          <el-scrollbar>
            <el-menu :default-openeds="['2']">
              <el-sub-menu index="1">
                  <template #title>
                      <el-icon><icon-menu /></el-icon>审批
                  </template>
              </el-sub-menu>
  
              <el-sub-menu index="2">
                <template #title>
                  <el-icon><icon-menu /></el-icon>数据
                </template>
                <el-menu-item-group>
                  <!-- <template #title>客户</template> -->
                  <el-menu-item index="2-1">客户</el-menu-item>
                  <el-menu-item index="2-2">代理商</el-menu-item>
                  <el-menu-item index="2-3">ID</el-menu-item>
                </el-menu-item-group>
              </el-sub-menu>
  
              <el-sub-menu index="3">
                <template #title>
                  <el-icon><icon-menu /></el-icon>账单
                </template>
  
              </el-sub-menu>
            </el-menu>
          </el-scrollbar>
        </el-aside>
  
        <el-container>
          <el-header style="text-align:center; font-size: 16px">
              <h1>数据管理</h1>
            <div class="toolbar">
              <el-dropdown>

                <el-icon style="margin-right: 8px; margin-top: 1px">
                  <setting />
                </el-icon>

                <template #dropdown>
                  <el-dropdown-menu>
                    <el-dropdown-item>View</el-dropdown-item>
                    <el-dropdown-item>Add</el-dropdown-item>
                    <el-dropdown-item>Delete</el-dropdown-item>
                  </el-dropdown-menu>
                </template>

              </el-dropdown>
  
            </div>
          </el-header>
  
          <el-main>
            <el-scrollbar>
              <el-table :data="tableData">
                <el-table-column prop="name" label="名称" width="160" />
                <el-table-column prop="group" label="客户群" width="160" />
                <el-table-column prop="contact" label="联系人" width="160" />
                <el-table-column prop="phone" label="联系方式" width="160" />
                <el-table-column prop="media" label="媒介" width="160" />
                <el-table-column prop="business" label="商务" width="160" />
                <el-table-column prop="creditLimit" label="垫款额度" width="160" />
                <el-table-column prop="temporaryCredit" label="临时垫款额度" width="160" />
                <el-table-column prop="paymentCycle" label="回款周期" width="160" />
                <el-table-column prop="spareFunds" label="备用金" width="160" />
                <el-table-column prop="other" label="其他" />
              </el-table>
            </el-scrollbar>
          </el-main>
        </el-container>
      </el-container>
    </div>
  </template>
  
  <script lang="ts" setup>
  import { ref } from 'vue'
  import { Menu as IconMenu, Message, Setting } from '@element-plus/icons-vue'
  
  const item = {
    name: "刘海宇",
    group: "千川-刘海宇",
    contact: "刘海宇",
    phone: "13888888888xxx",
    media: "77",
    creditLimit: "1000000",
    other: "冤种",
  }
  const tableData = ref(Array.from({ length: 20 }).fill(item))
  </script>
  
  <style scoped>
  html, body {
    height: 100%;
    margin: 0;
    padding: 0;
  }
  
  .layout-container-demo {
    height: 100vh; /* 设置高度为视口高度 */
    display: flex;
    flex-direction: column;
  }
  
  .layout-container-demo .el-header {
    position: relative;
    background-color: var(--el-color-primary-light-7);
    color: var(--el-text-color-primary);
    font-family: 'Arial', sans-serif;
    font-weight: 500;
    line-height: 1.5;
  }
  
  .layout-container-demo .el-aside {
    color: var(--el-text-color-primary);
    background: var(--el-color-primary-light-8);
    font-family: 'Arial', sans-serif;
  }
  
  .layout-container-demo .el-menu {
    border-right: none;
  }
  
  .layout-container-demo .el-main {
    padding: 0;
    font-family: 'Arial', sans-serif;
    line-height: 1.5;
  }
  
  .layout-container-demo .toolbar {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    right: 20px;
  }
  </style>