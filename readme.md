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
