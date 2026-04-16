# Day11-Vue3入门

## 为什么要学Vue3

![16e95ab7-f82f-4d46-8172-d0621bba4257](./Typedown/16e95ab7-f82f-4d46-8172-d0621bba4257.png)

### Vue3的优势

![6bf35c11-6cc9-4fcd-8236-e420d6589ea2](./Typedown/6bf35c11-6cc9-4fcd-8236-e420d6589ea2.png)

### Vue2 选项式 API vs Vue3 组合式API

![d4a22ac7-6b70-4e39-8045-9bbc203229a4](./Typedown/d4a22ac7-6b70-4e39-8045-9bbc203229a4.png)

需求：点击按钮，让数字 +1

![d02ccfca-fc04-4409-a864-acc5c7462dfc](./Typedown/d02ccfca-fc04-4409-a864-acc5c7462dfc.png)

## create-vue搭建Vue3项目

### 认识 create-vue

`create-vue`是`Vue`官方新的脚手架工具，底层切换到了 `vite`（下一代构建工具），为开发提供极速响应

![e89d418a-0482-406f-a6c6-3833d3837b29](./Typedown/e89d418a-0482-406f-a6c6-3833d3837b29.png)

### 使用create-vue创建项目

1. 前提环境条件
   已安装 `16.0` 或更高版本的 `Node.js`
   <mark>node -v</mark>

2. 创建一个`Vue`应用
   <mark>npm init vue@latest</mark>
   这一指令将会安装并执行 `create-vue`

![0ecac5dd-a640-4215-8cbe-6fcadb3985bf](./Typedown/0ecac5dd-a640-4215-8cbe-6fcadb3985bf.png)

### 项目目录和关键文件

![513fcad2-35b9-45e0-a501-f05a1c414e59](./Typedown/513fcad2-35b9-45e0-a501-f05a1c414e59.png)

![948ad0ca-59ec-48dc-a1e6-bc541c2aad54](./Typedown/948ad0ca-59ec-48dc-a1e6-bc541c2aad54.png)

![ef85db42-3a88-465f-90d4-72aad8d7d79d](./Typedown/ef85db42-3a88-465f-90d4-72aad8d7d79d.png)

![cc2a6790-cd73-4ab4-9a7e-4d969a005022](./Typedown/cc2a6790-cd73-4ab4-9a7e-4d969a005022.png)

## 组合式API - setup选项

### setup选项的写法和执行时机

![728a86e3-1cc5-461b-957b-342d34f946f9](./Typedown/728a86e3-1cc5-461b-957b-342d34f946f9.png)

![84186a79-15db-4c8a-b116-9cd78b83d423](./Typedown/84186a79-15db-4c8a-b116-9cd78b83d423.png)

### setup选项中写代码的特点

![20279c1d-4a07-4aa9-9ca9-18912d435f20](./Typedown/20279c1d-4a07-4aa9-9ca9-18912d435f20.png)

![5124ed90-faad-4fae-abf7-3fca5931c926](./Typedown/5124ed90-faad-4fae-abf7-3fca5931c926.png)

### <script setup> 语法糖

![996f7fc0-d9b1-4628-bb3a-0b2abc6e89cb](./Typedown/996f7fc0-d9b1-4628-bb3a-0b2abc6e89cb.png)

![1af4097e-34a2-45cf-8308-89b1cf446338](./Typedown/1af4097e-34a2-45cf-8308-89b1cf446338.png)

原理:

![8c606e2f-ba91-4986-8544-65f04863be1b](./Typedown/8c606e2f-ba91-4986-8544-65f04863be1b.png)

## 组合式API - reactive和ref函数

### reactive()

**作用：接受对象类型数据的参数传入 并返回一个响应式的对象**

核心步骤：

1. 从 `vue `包中<mark>导入 reactive 函数</mark>

2. 在 `<script setup>` 中<mark>执行 reactive 函数</mark>并传入<mark>类型为对象</mark>的初始值，并使用变量接收返回值

![d1745f68-42d8-45ee-8d75-9bd187a2d056](./Typedown/d1745f68-42d8-45ee-8d75-9bd187a2d056.png)

### ref()

**作用：接收简单类型或者对象类型的数据传入并返回一个响应式的对象**

核心步骤：

1. 从 `vue `包中<mark>导入 ref 函数</mark>

2. 在 `<script setup>` 中<mark>执行 ref 函数</mark>并传入初始值，使用变量接收 `ref `函数的返回值

![8435d5c0-8304-4253-9b33-dcaa02ed1ad8](./Typedown/8435d5c0-8304-4253-9b33-dcaa02ed1ad8.png)

## 组合式API - computed

### computed计算属性函数

计算属性基本思想和`Vue2`的完全一致，组合式`API`下的计算属性<mark>只是修改了写法</mark>

核心步骤：

1. <mark>导入</mark>`computed`函数

2. <mark>执行函数</mark> 在回调参数中<mark>`return`基于响应式数据做计算的值</mark>，用<mark>变量接收</mark>

![e6dd3847-40f7-4cdc-a39f-4d288a64fbd0](./Typedown/e6dd3847-40f7-4cdc-a39f-4d288a64fbd0.png)

![bd0075e5-9ef3-442d-b9ed-d06de6ebf8df](./Typedown/bd0075e5-9ef3-442d-b9ed-d06de6ebf8df.png)

## 组合式API - watch

**作用: 侦听一个或者多个数据的变化，数据变化时执行回调函数**

俩个额外参数：1. `immediate`（立即执行） 2. `deep`（深度侦听）

### 基础使用 - 侦听单个数据

1. <mark>导入watch</mark>函数

2. <mark>执行watch</mark>函数传入要侦听的响应式数据(<mark>ref对象</mark>)和回调函数

![b58d428f-2e90-4511-848f-1c330d3b0bb0](./Typedown/b58d428f-2e90-4511-848f-1c330d3b0bb0.png)

![a8875cdb-6da0-47ac-9447-078379072e6c](./Typedown/a8875cdb-6da0-47ac-9447-078379072e6c.png)

### 基础使用 - 侦听多个数据

说明：同时侦听多个响应式数据的变化，不管哪个数据变化都需要执行回调

![a4ae0f28-d476-47ba-ba15-6b6f816d8d8f](./Typedown/a4ae0f28-d476-47ba-ba15-6b6f816d8d8f.png)

![38ec5984-37a9-485e-b3ad-500c860a3e8d](./Typedown/38ec5984-37a9-485e-b3ad-500c860a3e8d.png)

### immediate

说明：在侦听器<mark>创建时立即触发</mark>回调, 响应式数据变化之后继续执行回调

![2c6cd113-aa07-485a-84a8-d4adcaa44e01](./Typedown/2c6cd113-aa07-485a-84a8-d4adcaa44e01.png)

![88c5c3fb-a9e4-4760-b294-81e578a526ee](./Typedown/88c5c3fb-a9e4-4760-b294-81e578a526ee.png)

### deep

默认机制：通过watch监听的ref对象默认是<mark>浅层侦听的，直接修改嵌套的对象属性不会触发回调执行</mark>，需要开启deep选项

![80a3f061-15c5-4c10-a9e0-72b93df29f7a](./Typedown/80a3f061-15c5-4c10-a9e0-72b93df29f7a.png)

![896cab11-3dd3-4891-892d-0d0d7671eeab](./Typedown/896cab11-3dd3-4891-892d-0d0d7671eeab.png)

### 精确侦听对象的某个属性

需求：在不开启deep的前提下，侦听age的变化，只有age变化时才执行回调

![e9f429b2-a961-4a84-b30e-fca202ddf0b1](./Typedown/e9f429b2-a961-4a84-b30e-fca202ddf0b1.png)

![e6d886e9-797c-40d0-ac76-20868f762890](./Typedown/e6d886e9-797c-40d0-ac76-20868f762890.png)

## 组合式API - 生命周期函数

### Vue3的生命周期API （选项式 VS 组合式）

![2b2d4f89-46ce-434b-bd6f-c2c3a8744dcc](./Typedown/2b2d4f89-46ce-434b-bd6f-c2c3a8744dcc.png)

### 生命周期函数基本使用

1. 导入生命周期函数

2. 执行生命周期函数 传入回调

### 执行多次

生命周期函数是可以执行多次的，多次执行时传入的回调会在时机成熟时依次执行

![2916e956-d8f6-4d9c-bdae-9807a7fa9d02](./Typedown/2916e956-d8f6-4d9c-bdae-9807a7fa9d02.png)

## 组合式API - 父子通信

### 组合式API下的父传子

基本思想

1. 父组件中给<mark>子组件绑定属性</mark>

2. 子组件内部<mark>通过props选项接收</mark>

![4ceccabb-6a29-4d41-b201-d6e40d44ab5d](./Typedown/4ceccabb-6a29-4d41-b201-d6e40d44ab5d.png)

`defineProps `原理：就是编译阶段的一个标识，实际编译器解析时，遇到后会进行编译转换

![1badc416-3307-4064-857a-a369db13765e](./Typedown/1badc416-3307-4064-857a-a369db13765e.png)

### 组合式API下的子传父

基本思想

1. 父组件中给<mark>子组件标签通过@绑定事件</mark>

2. 子组件内部通过 <mark>emit 方法触发事件</mark>

![796cd379-65b5-47d8-85ab-bf25e4562d6d](./Typedown/796cd379-65b5-47d8-85ab-bf25e4562d6d.png)

![74a1c671-77f3-40e7-8465-4c65e947994d](./Typedown/74a1c671-77f3-40e7-8465-4c65e947994d.png)

## 组合式API - 模版引用

### 模板引用的概念

通过<mark>ref标识</mark>获取真实的<mark>dom对象或者组件实例对象</mark>

![6c3f86b3-640a-40c4-a5b9-f9eca86c3fb5](./Typedown/6c3f86b3-640a-40c4-a5b9-f9eca86c3fb5.png)

### 如何使用（以获取dom为例 组件同理）

1. 调用`ref`函数生成一个`ref`对象

2. 通过`ref`标识绑定`ref`对象到标签

![9e2c0632-458f-4a01-baec-9c514ac43787](./Typedown/9e2c0632-458f-4a01-baec-9c514ac43787.png)

### defineExpose()

默认情况下在`<script setup>`语法糖下<mark>组件内部的属性和方法</mark>是不开放给父组件访问的，

可以通过`defineExpose`编译宏<mark>指定哪些属性和方法允许访问</mark>

![a0e5e980-9ca7-451b-aaf1-7c3b33e72284](./Typedown/a0e5e980-9ca7-451b-aaf1-7c3b33e72284.png)

## 组合式API - provide和inject

**作用和场景: 顶层组件向任意的底层组件<mark>传递数据和方法</mark>，实现<mark>跨层组件通信</mark>**

![6d0f0528-1768-4ca2-9630-3783b0c2f581](./Typedown/6d0f0528-1768-4ca2-9630-3783b0c2f581.png)

### 跨层传递普通数据

1. 顶层组件通过`provide`函数提供数据

2. 底层组件通过`inject`函数获取数据

![938a12f0-e08f-48b4-bb66-83f7b6176e9f](./Typedown/938a12f0-e08f-48b4-bb66-83f7b6176e9f.png)

### 跨层传递响应式数据

在调用`provide`函数时，第二个参数设置为`ref`对象

![f5cdec5b-db25-407d-92f1-5bbc93e94a05](./Typedown/f5cdec5b-db25-407d-92f1-5bbc93e94a05.png)

### 跨层传递方法

顶层组件可以向底层组件传递方法，底层组件调用方法修改顶层组件中的数据

![d413c5ff-9300-4b34-a620-d3b9bc882691](./Typedown/d413c5ff-9300-4b34-a620-d3b9bc882691.png)

![a90e17c0-d3c9-4e20-b7af-90867db7a0d5](./Typedown/a90e17c0-d3c9-4e20-b7af-90867db7a0d5.png)

解决需求性的问题

![61971660-0782-4fb6-b8ab-ff13912c26d0](./Typedown/61971660-0782-4fb6-b8ab-ff13912c26d0.png)

## Vue3.3新特性-defineOptions

背景说明：

有 `<script setup>` 之前，如果要定义 `props`, `emits `可以轻而易举地添加一个与 `setup `平级的属性。

但是用了 `<script setup>` 后，就没法这么干了 `setup `属性已经没有了，自然无法添加与其平级的属性。

![a4f87c91-9db8-4bdf-a0c6-6f0001edf574](./Typedown/a4f87c91-9db8-4bdf-a0c6-6f0001edf574.png)

为了解决这一问题，引入了 `defineProps `与 `defineEmits `这两个宏。但这只解决了 `props `与 `emits `这两个属性。

如果我们要定义组件的 `name `或其他自定义的属性，还是得回到最原始的用法——再添加一个普通的 `<script>` 标签。

这样就会存在两个 `<script>` 标签。让人无法接受。

所以在 Vue 3.3 中新引入了 <mark>defineOptions </mark>宏。顾名思义，主要是用来定义 <mark>Options API</mark> 的选项。可以用

defineOptions 定义任意的选项， props, emits, expose, slots 除外（因为这些可以使用 defineXXX 来做到）

![d5b06800-ba9b-41a3-860a-1af5853fc1fe](./Typedown/d5b06800-ba9b-41a3-860a-1af5853fc1fe.png)

## Vue3.3新特性-defineModel

**Vue3 中的 v-model 和 defineModel**

在Vue3中，自定义组件上使用v-model, 相当于传递一个modelValue属性，同时触发 update:modelValue 事件

![4d8f1e5f-28e3-4b6e-bbed-876868f41e55](./Typedown/4d8f1e5f-28e3-4b6e-bbed-876868f41e55.png)

我们需要先定义 props，再定义 emits 。其中有许多重复的代码。如果需要修改此值，还需要手动调用 emit 函数。

![20955180-05b6-44eb-80b7-bfee03048cc0](./Typedown/20955180-05b6-44eb-80b7-bfee03048cc0.png)

代码示例:

![9454c394-3aef-426b-9316-b1e23e985797](./Typedown/9454c394-3aef-426b-9316-b1e23e985797.png)

## Pinia 快速入门

### 什么是Pinia

Pinia 是 Vue 的最新 状态管理工具 ，是 Vuex 的 替代品

![03e5ca8a-fc9d-4928-aecc-2e6fc4d3c11d](./Typedown/03e5ca8a-fc9d-4928-aecc-2e6fc4d3c11d.png)

1. 提供更加简单的`API `（去掉了 `mutation `）

2. 提供符合，组合式风格的`API `（和 Vue3 新语法统一）

3. 去掉了 modules 的概念，每一个 store 都是一个独立的模块

4. 配合 TypeScript 更加友好，提供可靠的类型推断

### 手动添加Pinia到Vue项目

在实际开发项目的时候，关于Pinia的配置，可以在项目创建时自动添加

现在我们初次学习，从零开始：

1. 使用 Vite 创建一个空的 Vue3 项目
   npm create vue@latest

2. 按照[官方文档](https://pinia.vuejs.org/zh/introduction.html) 安装 pinia 到项目中

![930d0415-cfbd-4b7e-a96c-b56db7c47ed2](./Typedown/930d0415-cfbd-4b7e-a96c-b56db7c47ed2.png)

### Pinia基础使用 - 计数器案例

1. 定义store

2. 组件使用store

![ff3452c2-0676-47d6-bc25-7c17438a6670](./Typedown/ff3452c2-0676-47d6-bc25-7c17438a6670.png)

### action异步实现

编写方式：异步`action`函数的写法和组件中获取异步数据的写法完全一致

接口地址：http://geek.itheima.net/v1_0/channels

需求：在`Pinia`中获取频道列表数据并把数据渲染App组件的模板中

![46850f23-56a6-4739-8e1f-dd1e17cb927b](./Typedown/46850f23-56a6-4739-8e1f-dd1e17cb927b.png)

### storeToRefs工具函数

使用`storeToRefs`函数可以辅助保持数据`（state + getter）`的响应式解构

![813b89d9-4c77-457a-9b91-859bae03c5c5](./Typedown/813b89d9-4c77-457a-9b91-859bae03c5c5.png)

![d647fe12-3af3-446f-98ca-e9e38b2f2b3a](./Typedown/d647fe12-3af3-446f-98ca-e9e38b2f2b3a.png)

### Pinia持久化插件

[官方文档](https://prazdevs.github.io/pinia-plugin-persistedstate/zh/guide/)

1. 安装插件 `pinia-plugin-persistedstate`
   
   ```shell
   npm i pinia-plugin-persistedstate
   ```

2. `main.js` 使用
   
   ```js
   import persist from 'pinia-plugin-persistedstate'
   
   ...
   
   app.use(createPinia().use(persist))
   ```

3. `store`仓库中，`persist: true` 开启

# Vue3 大事件管理系统

![094e3f6d-326c-4434-9058-7d6e4c81a849](./Typedown/094e3f6d-326c-4434-9058-7d6e4c81a849.png)

## 大事件项目介绍 和 创建

Vue3 大事件管理系统

在线演示： https://fe-bigevent-web.itheima.net/login

接口文档： https://apifox.com/apidoc/shared-26c67aee-0233-4d23-aab7-08448fdf95ff/api-93850835

基地址： http://big-event-vue-api-t.itheima.net

 ![ee58452d-28e4-4688-a9e6-0909d081289f](./Typedown/ee58452d-28e4-4688-a9e6-0909d081289f.png)

### pnpm 包管理器 - 创建项目

一些优势：比同类工具快2倍左右、节省磁盘空间... https://www.pnpm.cn/

安装方式：npm install -g pnpm

创建项目：pnpm create vue

![27e82d56-dd4a-4e0f-b012-3abb7dd7cce8](./Typedown/27e82d56-dd4a-4e0f-b012-3abb7dd7cce8.png)

![98c0dc22-8afa-431b-b405-336b9795347a](./Typedown/98c0dc22-8afa-431b-b405-336b9795347a.png)

### Eslint & prettier配置代码风格

**Eslint主要是用于纠错功能（规范）**

**prettier专注于代码的美观度（格式化工具）**

**环境同步：**

1. **安装了插件 ESlint，开启保存自动修复**
2. **禁用了插件 Prettier，并关闭保存自动格式化**

![f0d5dd1f-a1c3-46c2-8511-a1b68efba6d8](./Typedown/f0d5dd1f-a1c3-46c2-8511-a1b68efba6d8.png)

配置文件 `.eslint.config.js`

1. `prettier `风格配置 https://prettier.io
   <mark>单引号
   不使用分号
   宽度80字符
   不加对象，数组最后逗号
   换行符号不限制（win mac 不一致）</mark>

2. `vue`组件名称多单词组成（忽略`index.vue`）

3. `props`解构（关闭）

![93f10140-3a8d-4bce-b503-bb4493247514](./Typedown/93f10140-3a8d-4bce-b503-bb4493247514.png)

![44eb83fd-366a-4cbd-bfb0-75ae6058b593](./Typedown/44eb83fd-366a-4cbd-bfb0-75ae6058b593.png)

有以上Eslint和prettier辅助，我们写的代码应该是非常规范化，但总会有些小疏忽，然后直接提交到仓库显然是不合理的

### 配置代码检查工作流

husky是基于git的一个工具，理解为git的一个钩子，可以在特定的时机执行特定的命令，它在我们代码提交之前做一点事情

提交前做代码检查

1. 初始化 `git `仓库，执行 `git init` 即可
   ![73daa8a7-cb46-464d-9cfb-f54e18f7c395](./Typedown/73daa8a7-cb46-464d-9cfb-f54e18f7c395.png)

2. 初始化 `husky `工具配置，执行 `pnpm dlx husky-init && pnpm install` 即可
   https://typicode.github.io/husky/
   ![dde740ea-25d8-4120-a9cb-a39a0dee02e0](./Typedown/dde740ea-25d8-4120-a9cb-a39a0dee02e0.png)

3. 修改 `.husky/pre-commit` 文件
   这里我当时遇到了一个错误，解决：还要安装一下`pnpm`
   ![9b3e8418-c2cf-4b3b-a390-ed1c8ae3b8cb](./Typedown/9b3e8418-c2cf-4b3b-a390-ed1c8ae3b8cb.png)

![d4d1badf-4d6d-40df-a566-fd5f132ef5f2](./Typedown/d4d1badf-4d6d-40df-a566-fd5f132ef5f2.png)

![bb25abb9-fecd-48c3-915b-f17aa469b9b1](./Typedown/bb25abb9-fecd-48c3-915b-f17aa469b9b1.png)

![f18b6f2e-4026-42b9-8011-d3770c06d5c3](./Typedown/f18b6f2e-4026-42b9-8011-d3770c06d5c3.png)

<mark>问题：pnpm lint 是全量检查，耗时问题，历史问题。</mark> 因为lint是对所有的文件都进行检查

### 暂存区 eslint 校验

**只会校验暂存区新添加的代码**

1. 安装 `lint-staged` 包 `pnpm i lint-staged -D`

2. `package.json` 配置 `lint-staged` 命令

3. `.husky/pre-commit` 文件修改

![b129e9d6-3d74-4c06-9e12-5acc1e56e41f](./Typedown/b129e9d6-3d74-4c06-9e12-5acc1e56e41f.png)![fa21c8c4-9ba0-4079-ba63-724c1b1b258c](./Typedown/fa21c8c4-9ba0-4079-ba63-724c1b1b258c.png)

![7e44fd02-3b63-42f2-bcef-fdcd19799ab7](./Typedown/7e44fd02-3b63-42f2-bcef-fdcd19799ab7.png)

### 目录调整

默认生成的目录结构不满足我们的开发需求，所以这里需要做一些自定义改动。

主要是以下工作：

1. 删除一些初始化的默认文件

2. 修改剩余代码内容

3. 新增调整我们需要的目录结构

4. 拷贝全局样式和图片，安装预处理器支持

![def26f1d-cc9c-4e5e-ac1a-a42ba6c2c2f9](./Typedown/def26f1d-cc9c-4e5e-ac1a-a42ba6c2c2f9.png)![68e315c1-44ed-42b3-8911-eefe911f70f7](./Typedown/68e315c1-44ed-42b3-8911-eefe911f70f7.png)

### vue-router4 路由代码解析

路由初始化

![6d8c3ae9-1434-41c1-8f97-1c5306eaa5ec](./Typedown/6d8c3ae9-1434-41c1-8f97-1c5306eaa5ec.png)

如何使用router进行跳转

![bac99fae-b506-4e02-96fa-f9e699c45692](./Typedown/bac99fae-b506-4e02-96fa-f9e699c45692.png)

### 引入Element-plus组件库

参照官方文档： https://element-plus.org/zh-CN/guide/quickstart.html

1. 安装： 
   
   ```shell
   pnpm install element-plus
   ```

2. 配置按需导入：
   先安装这两个插件
   
   ```shell
   pnpm add -D unplugin-vue-components unplugin-auto-import
   ```

3. 配置`vite.config.js`
   
   ```js
   import { defineConfig } from 'vite'
   import AutoImport from 'unplugin-auto-import/vite'
   import Components from 'unplugin-vue-components/vite'
   import { ElementPlusResolver } from 'unplugin-vue-components/resolvers'
   
   export default defineConfig({
     // ...
     plugins: [
       // ...
       AutoImport({
         resolvers: [ElementPlusResolver()],
       }),
       Components({
         resolvers: [ElementPlusResolver()],
       }),
     ],
   })
   ```

以上步骤完整后，就可以直接使用了，也不需要导入什么的，这就是上面插件的神奇之处

![7627b108-c0c5-43fe-8a12-a761d046e5a1](./Typedown/7627b108-c0c5-43fe-8a12-a761d046e5a1.png)

### Pinia 构建仓库 和 持久化

![a2d84513-dab3-4d39-926c-89a4d0230582](./Typedown/a2d84513-dab3-4d39-926c-89a4d0230582.png)

构建仓库：

![63a1bc76-7623-44b5-9bcb-550dd4417dbb](./Typedown/63a1bc76-7623-44b5-9bcb-550dd4417dbb.png)

持久化处理

1. 安装插件 `pinia-plugin-persistedstate` 
   
   ```shell
   pnpm add pinia-plugin-persistedstate -D
   ```

2. 使用 `main.js` 
   
   ```js
   import persist from 'pinia-plugin-persistedstate'
   ...
   app.use(createPinia().use(persist))
   ```

3. 配置 `stores/user.js` 
   
   ```js
   import { defineStore } from 'pinia'
   import { ref } from 'vue'
   
   // 用户模块
   export const useUserStore = defineStore(
     'big-user',
     () => {
       const token = ref('') // 定义 token
       const setToken = (t) => (token.value = t) // 设置 token
   
       return { token, setToken }
     },
     {
       persist: true // 持久化
     }
   )
   ```

### Pinia 仓库统一管理

![bd7a1c56-a242-413b-b323-7201d2c7c107](./Typedown/bd7a1c56-a242-413b-b323-7201d2c7c107.png)

pinia 独立维护

- 现在：初始化代码在 `main.js` 中，仓库代码在 `stores `中，代码分散职能不单一

- 优化：由 `stores `统一维护，在 `stores/index.js` 中完成 `pinia `初始化，交付 `main.js` 使用

![fcfd2c25-efde-466d-8814-f7235993719c](./Typedown/fcfd2c25-efde-466d-8814-f7235993719c.png)

仓库 统一导出

- 现在：使用一个仓库 import { useUserStore } from `./stores/user.js` 不同仓库路径不一致

- 优化：由 `stores/index.js` 统一导出，导入路径统一 `./stores`，而且仓库维护在 `stores/modules` 中

![f52a6e01-c504-4d8c-923a-63f62a05f59f](./Typedown/f52a6e01-c504-4d8c-923a-63f62a05f59f.png)

![d19db9db-48ec-48f8-b4f7-f6df41955685](./Typedown/d19db9db-48ec-48f8-b4f7-f6df41955685.png)

### 数据交互 - 请求工具设计

![44d49659-35f5-48d5-a0a8-0b7d17045953](./Typedown/44d49659-35f5-48d5-a0a8-0b7d17045953.png)

```js
import axios from "axios";
import { useUserStore } from "@/stores";
import { ElMessage } from "element-plus";
import router from "@/router";

const baseURL = 'http://big-event-vue-api-t.itheima.net';

const instance = axios.create({
  baseURL,
  timeout: 10000,
});

// 添加请求拦截器
instance.interceptors.request.use(function (config) {
    // 在发送请求之前做些什么
    const userStore = useUserStore()
    const token = userStore.token
    if(token){
        config.headers.Authorization = token
    }
    return config;
  }, function (error) {
    // 对请求错误做些什么
    return Promise.reject(error);
  });

// 添加响应拦截器
instance.interceptors.response.use(function (response) {
    // 2xx 范围内的状态码都会触发该函数。
    // 对响应数据做点什么
    if(response.data.code === 0) {
        return response
    }
    ElMessage({ message: response.data.message || '服务异常', type: 'error'})
    return Promise.reject(response.data);
  }, function (error) {
    // 超出 2xx 范围的状态码都会触发该函数。
    // 对响应错误做点什么
    ElMessage({ message: error.response.data.message || '服务异常', type: 'error' })
    console.log(error)
    if (error.response?.status === 401) {
      router.push('/login')
    }
    return Promise.reject(error);
  });

  export default instance
```

### 整体路由设计

![efce56df-bfce-4920-a5fb-0dbc9edc97c3](./Typedown/efce56df-bfce-4920-a5fb-0dbc9edc97c3.png)

## 具体业务功能实现

### 登录注册页面 [element-plus 表单 & 表单校验]

功能需求说明：

1. 注册登录 静态结构 & 基本切换
   安装 `element-plus` 图标库
   
   ```shell
   pnpm i @element-plus/icons-vue
   ```
   
   静态结构准备
   
   ```html
   <script setup>
   import { User, Lock } from '@element-plus/icons-vue'
   import { ref } from 'vue'
   const isRegister = ref(true)
   </script>
   
   <template>
     <el-row class="login-page">
       <el-col :span="12" class="bg"></el-col>
       <el-col :span="6" :offset="3" class="form">
         <el-form ref="form" size="large" autocomplete="off" v-if="isRegister">
           <el-form-item>
             <h1>注册</h1>
           </el-form-item>
           <el-form-item>
             <el-input :prefix-icon="User" placeholder="请输入用户名"></el-input>
           </el-form-item>
           <el-form-item>
             <el-input
               :prefix-icon="Lock"
               type="password"
               placeholder="请输入密码"
             ></el-input>
           </el-form-item>
           <el-form-item>
             <el-input
               :prefix-icon="Lock"
               type="password"
               placeholder="请输入再次密码"
             ></el-input>
           </el-form-item>
           <el-form-item>
             <el-button class="button" type="primary" auto-insert-space>
               注册
             </el-button>
           </el-form-item>
           <el-form-item class="flex">
             <el-link type="info" :underline="false" @click="isRegister = false">
               ← 返回
             </el-link>
           </el-form-item>
         </el-form>
         <el-form ref="form" size="large" autocomplete="off" v-else>
           <el-form-item>
             <h1>登录</h1>
           </el-form-item>
           <el-form-item>
             <el-input :prefix-icon="User" placeholder="请输入用户名"></el-input>
           </el-form-item>
           <el-form-item>
             <el-input
               name="password"
               :prefix-icon="Lock"
               type="password"
               placeholder="请输入密码"
             ></el-input>
           </el-form-item>
           <el-form-item class="flex">
             <div class="flex">
               <el-checkbox>记住我</el-checkbox>
               <el-link type="primary" :underline="false">忘记密码？</el-link>
             </div>
           </el-form-item>
           <el-form-item>
             <el-button class="button" type="primary" auto-insert-space
               >登录</el-button
             >
           </el-form-item>
           <el-form-item class="flex">
             <el-link type="info" :underline="false" @click="isRegister = true">
               注册 →
             </el-link>
           </el-form-item>
         </el-form>
       </el-col>
     </el-row>
   </template>
   
   <style lang="scss" scoped>
   .login-page {
     height: 100vh;
     background-color: #fff;
     .bg {
       background: url('@/assets/logo2.png') no-repeat 60% center / 240px auto,
         url('@/assets/login_bg.jpg') no-repeat center / cover;
       border-radius: 0 20px 20px 0;
     }
     .form {
       display: flex;
       flex-direction: column;
       justify-content: center;
       user-select: none;
       .title {
         margin: 0 auto;
       }
       .button {
         width: 100%;
       }
       .flex {
         width: 100%;
         display: flex;
         justify-content: space-between;
       }
     }
   }
   </style>
   ```

2. 注册功能 (校验 + 注册)
   校验：
   
   ```html
   <script setup>
   import { User, Lock } from '@element-plus/icons-vue'
   import { ref } from 'vue'
   const isRegister = ref(false)
   
   // 注册表单数据
   const registerForm = ref({
     username: '',
     password: '',
     repassword: '',
   })
   
   // 自定义确认密码校验
   // validator：(rule, value, callback)
   // rule 当前校验规则相关的信息
   // value 所校验的表单元素目前的表单值
   const validateConfirmPassword = (rule, value, callback) => {
     if (value !== registerForm.value.password) {
       callback(new Error('两次输入的密码不一致'))
     } else {
       callback()
     }
   }
   
   // 注册表单的校验规则
   const registerRules = {
     username: [
       // 非空校验，如果没输入就显示“请输入用户名”，trigger代表什么时候触发，blur失去焦点时触发，change代表实时触发，改变时触发
       { required: true, message: '请输入用户名', trigger: 'blur' },
       // min和max长度校验
       { min: 3, max: 10, message: '长度在 3 到 10 个字符', trigger: 'blur' },
     ],
     password: [
       { required: true, message: '请输入密码', trigger: 'blur' },
       // pattern 代表正则规则
       { pattern: /^\S{6,15}$/, message: '密码必须是6到15位的非空字符', trigger: 'blur' },
     ],
     repassword: [
       { required: true, message: '请再次输入密码', trigger: 'blur' },
       { pattern: /^\S{6,15}$/, message: '密码必须是6到15位的非空字符', trigger: 'blur' },
       { validator: validateConfirmPassword, trigger: 'blur' },
     ],
   }
   </script>
   
   <template>
     <el-row class="login-page">
       <el-col :span="12" class="bg"></el-col>
       <el-col :span="6" :offset="3" class="form">
         <el-form ref="registerFormRef" size="large" autocomplete="off" :model="registerForm" :rules="registerRules" v-if="isRegister">
           <el-form-item>
             <h1>注册</h1>
           </el-form-item>
           <el-form-item prop="username">
             <el-input v-model="registerForm.username" :prefix-icon="User" placeholder="请输入用户名"></el-input>
           </el-form-item>
           <el-form-item prop="password">
             <el-input
               v-model="registerForm.password"
               :prefix-icon="Lock"
               type="password"
               placeholder="请输入密码"
             ></el-input>
           </el-form-item>
           <el-form-item prop="repassword">
             <el-input
               v-model="registerForm.repassword"
               :prefix-icon="Lock"
               type="password"
               placeholder="请输入再次密码"
             ></el-input>
           </el-form-item>
           <el-form-item>
             <el-button class="button" type="primary" auto-insert-space>
               注册
             </el-button>
           </el-form-item>
           <el-form-item class="flex">
             <el-link type="info" :underline="false" @click="isRegister = false">
               ← 返回
             </el-link>
           </el-form-item>
         </el-form>
         <el-form ref="form" size="large" autocomplete="off" v-else>
           <el-form-item>
             <h1>登录</h1>
           </el-form-item>
           <el-form-item>
             <el-input :prefix-icon="User" placeholder="请输入用户名"></el-input>
           </el-form-item>
           <el-form-item>
             <el-input
               name="password"
               :prefix-icon="Lock"
               type="password"
               placeholder="请输入密码"
             ></el-input>
           </el-form-item>
           <el-form-item class="flex">
             <div class="flex">
               <el-checkbox>记住我</el-checkbox>
               <el-link type="primary" :underline="false">忘记密码？</el-link>
             </div>
           </el-form-item>
           <el-form-item>
             <el-button class="button" type="primary" auto-insert-space
               >登录</el-button
             >
           </el-form-item>
           <el-form-item class="flex">
             <el-link type="info" :underline="false" @click="isRegister = true">
               注册 →
             </el-link>
           </el-form-item>
         </el-form>
       </el-col>
     </el-row>
   </template>
   ```
   
   注册（请求后台）：
   `src/api/user.js:`
   
   ```js
   import request from '@/utils/request'
   
   export const registerSubmit = (username, password, repassword) => {
       return request.post('/api/reg', {
           username,
           password,
           repassword
       })
   }
   ```
   
   `LoginPage.vue:`
   ![84d85832-a8b6-4d2f-b518-98a12fd979a7](./Typedown/84d85832-a8b6-4d2f-b518-98a12fd979a7.png)
   `eslint.config.js`中声明全局变量名, 解决 `ElMessage` 报错问题
   ![ac3ee4f3-c30c-4cad-b034-13f22edd736a](./Typedown/ac3ee4f3-c30c-4cad-b034-13f22edd736a.png)
   这样的话，可能会报错，那是因为我们的`eslint`认为你没有引入该组件，故只需要在`eslint.config.js`中添加配置即可解决报错问题
   ![bf932bc1-efc8-4d8f-9ca8-bb3a85f5de4c](./Typedown/bf932bc1-efc8-4d8f-9ca8-bb3a85f5de4c.png)

3. 登录功能 (校验 + 登录 + 存token)
   校验登录
   
   ```jsx
   // 登录表单数据
   const loginForm = ref({
     username: '',
     password: ''
   })
   // 登录表单的校验规则
   const loginRules = {
     username: [
       { required: true, message: '请输入用户名', trigger: 'blur' },
       { min: 1, max: 10, message: '长度在 1 到 10 个字符', trigger: 'blur' },
     ],
     password: [
       { required: true, message: '请输入密码', trigger: 'blur' },
       { pattern: /^\S{6,15}$/, message: '密码必须是6到15位的非空字符', trigger:'blur'}
     ]
   }
   
   ```

登录接口：

`LoginPage.vue`

```jsx
  // 创建登录组件的引用
const loginFormRef = ref(null)
const login = async () => {
  const userStore = useUserStore()
  await loginFormRef.value.validate()
  const res = await loginSubmit(loginForm.value.username, loginForm.value.password)
  userStore.setToken(res.data.token)
  ElMessage.success('登录成功')
  router.push('/')
}
```

`user.js:`

```jsx
export const loginSubmit = (username, password) => {
    return request.post('/api/login', {
        username,
        password
    })
}
```

### 首页 layout 架子

![21c255f4-15a7-4b12-87c3-42ca8a01af49](./Typedown/21c255f4-15a7-4b12-87c3-42ca8a01af49.png)

```jsx
<script setup>
import {
  Management,
  Promotion,
  UserFilled,
  User,
  Crop,
  EditPen,
  SwitchButton,
  CaretBottom
} from '@element-plus/icons-vue'
import avatar from '@/assets/default.png'
</script>

<template>
  <el-container class="layout-container">
    <el-aside width="200px">
      <div class="el-aside__logo"></div>
      <el-menu
        active-text-color="#ffd04b"
        background-color="#232323"
        :default-active="$route.path"
        text-color="#fff"
        router
      >
        <el-menu-item index="/article/channel">
          <el-icon><Management /></el-icon>
          <span>文章分类</span>
        </el-menu-item>
        <el-menu-item index="/article/manage">
          <el-icon><Promotion /></el-icon>
          <span>文章管理</span>
        </el-menu-item>
        <el-sub-menu index="/user">
          <template #title>
            <el-icon><UserFilled /></el-icon>
            <span>个人中心</span>
          </template>
          <el-menu-item index="/user/profile">
            <el-icon><User /></el-icon>
            <span>基本资料</span>
          </el-menu-item>
          <el-menu-item index="/user/avatar">
            <el-icon><Crop /></el-icon>
            <span>更换头像</span>
          </el-menu-item>
          <el-menu-item index="/user/password">
            <el-icon><EditPen /></el-icon>
            <span>重置密码</span>
          </el-menu-item>
        </el-sub-menu>
      </el-menu>
    </el-aside>
    <el-container>
      <el-header>
        <div>黑马程序员：<strong>小帅鹏</strong></div>
        <el-dropdown placement="bottom-end">
          <span class="el-dropdown__box">
            <el-avatar :src="avatar" />
            <el-icon><CaretBottom /></el-icon>
          </span>
          <template #dropdown>
            <el-dropdown-menu>
              <el-dropdown-item command="profile" :icon="User"
                >基本资料</el-dropdown-item
              >
              <el-dropdown-item command="avatar" :icon="Crop"
                >更换头像</el-dropdown-item
              >
              <el-dropdown-item command="password" :icon="EditPen"
                >重置密码</el-dropdown-item
              >
              <el-dropdown-item command="logout" :icon="SwitchButton"
                >退出登录</el-dropdown-item
              >
            </el-dropdown-menu>
          </template>
        </el-dropdown>
      </el-header>
      <el-main>
        <router-view></router-view>
      </el-main>
      <el-footer>大事件 ©2023 Created by 黑马程序员</el-footer>
    </el-container>
  </el-container>
</template>

<style lang="scss" scoped>
.layout-container {
  height: 100vh;
  .el-aside {
    background-color: #232323;
    &__logo {
      height: 120px;
      background: url('@/assets/logo.png') no-repeat center / 120px auto;
    }
    .el-menu {
      border-right: none;
    }
  }
  .el-header {
    background-color: #fff;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .el-dropdown__box {
      display: flex;
      align-items: center;
      .el-icon {
        color: #999;
        margin-left: 10px;
      }

      &:active,
      &:focus {
        outline: none;
      }
    }
  }
  .el-footer {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 14px;
    color: #666;
  }
}
</style>
```

#### 登录访问拦截

**需求：只有登录页，可以未授权的时候访问，其他所有页面，都需要先登录再访问**

![707e4ce6-e521-44b5-89db-c50a8eab6196](./Typedown/707e4ce6-e521-44b5-89db-c50a8eab6196.png)

#### 用户基本信息渲染

![80dd5cf4-c67d-44c5-b98b-564477416d3d](./Typedown/80dd5cf4-c67d-44c5-b98b-564477416d3d.png)

#### 退出按钮

![db313ce6-255f-40ec-a738-c66fd67bc5f9](./Typedown/db313ce6-255f-40ec-a738-c66fd67bc5f9.png)

### 文章分类页面

![36fe470c-5d51-4905-91a0-babdd073cccb](./Typedown/36fe470c-5d51-4905-91a0-babdd073cccb.png)

`PageContainer.vue`

```html
<script setup>
defineProps({
    title: {
        required: true,
        type: String
    }
})
</script>
<template>
  <el-card class="page-container">
    <template #header>
      <div class="header">
        <span>{{ title }}</span>
        <div class="extra">
            <slot name="extra"></slot>
        </div>
      </div>
    </template>
    <slot></slot>
  </el-card>
</template>

<style lang="scss" scoped>
.page-container {
  min-height: 100%;
  box-sizing: border-box;
  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}
</style>
```

`api/article.js`

```js
import request from '@/utils/request'
export const artGetChannelsService = () => {
    return request.get('/my/cate/list')
}
```

ArticleChannel.vue

```html
<script setup>
import { artGetChannelsService } from '@/api/article'
import { Edit, Delete } from '@element-plus/icons-vue'
import { ref } from 'vue'
import { onMounted } from 'vue'

const channelList = ref([])
const loading = ref(false)
const getChannelList = async () => {
  loading.value = true
  const res = await artGetChannelsService()
  channelList.value = res.data.
  loading.value = false
}
onMounted(() => {
  getChannelList()
  console.log(channelList.value)
})

const onEditChannel = (row, $index) => {
  console.log(row, $index)
}

const onDelChannel = (row) => {
  console.log(row)
}
</script>
<template>
  <page-container title="文章分类">
    <template #extra>
        <el-button>添加分类</el-button>
    </template>

    <el-table v-loading="loading" :data="channelList" style="width: 100%">
      <el-table-column label="序号" width="100" type="index"> </el-table-column>
      <el-table-column label="分类名称" prop="cate_name"></el-table-column>
      <el-table-column label="分类别名" prop="cate_alias"></el-table-column>
      <el-table-column label="操作" width="100">
        <!-- row 就是 channelList 的一项, $index 下标 -->
        <template #default="{ row }">
          <el-button
            :icon="Edit"
            circle
            plain
            type="primary"
            @click="onEditChannel(row)"
          ></el-button>
          <el-button
            :icon="Delete"
            circle
            plain
            type="danger"
            @click="onDelChannel(row)"
          ></el-button>
        </template>
      </el-table-column>
      <template #empty>
        <el-empty description="没有数据" />
      </template>
    </el-table>

  </page-container>
</template>

<style lang="scss" scoped></style>
```


