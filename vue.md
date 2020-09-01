### 001.说一下vue中的MVVM？

即Model-View-ViewModel。

Vue是以数据为驱动的，Vue自身将DOM和数据进行绑定，一旦创建绑定，DOM和数据将保持同步，每当数据发生变化，DOM会跟着变化

ViewModel是Vue的核心，它是Vue的一个实例。Vue实例时作用域某个HTML元素上的，这个HTML元素可以是body，也可以是某个id所指代的元素。

DOM Listeners和Data Bindings是实现双向绑定的关键。DOM Listeners监听页面所有View层DOM元素的变化，当发生变化，Model层的数据随之变化；Data Bindings监听Model层的数据，当数据发生变化，View层的DOM元素随之变化。

### 002.v-show与v-if的区别

条件渲染指令，与v-if不同的是，无论v-show的值为true或false，元素都会存在于HTML代码中；而只有当v-if的值为true，元素才会存在于HTML代码中。v-show指令只是设置了元素CSS的style值

### 003.指令keep-alive

在vue-router写着keep-alive，keep-alive的含义：如果把切换出去的组件保留在内存中，可以保留它的状态或避免重新渲染。为此可以添加一个keep-alive指令

### 004.路由嵌套

路由嵌套会将其他组件渲染到该组件内，而不是进行整个页面跳转。
 router-view本身就是将组件渲染到该位置，

### 005.说一下v-model的原理？

简单的说，就是 :value 和 @input 的结合使用，v-model就是他们两个的语法糖。

### 006.vue中使用事件名

在vuejs中，我们经常要绑定一些事件，有时候给DOM元素绑定，有时候给组件绑定。
 绑定事件在HTML中用v-on:click="event"，可以简写为：@click="event"

### 007.vue.js是什么

Vue.js是一套构建用户界面的 渐进式框架。与其他重量级框架不同的是，Vue 采用自底向上增量开发的设计。
 Vue 的核心库只关注视图层，并且非常容易学习，非常容易与其它库或已有项目整合。
 另一方面，Vue 完全有能力驱动采用单文件组件和Vue生态系统支持的库开发的复杂单页应用。
 Vue.js 的目标是通过尽可能简单的 API 实现响应的数据绑定和组合的视图组件

### 008.route 和 router 的区别是什么？

route是“路由信息对象”，包括path,params,hash,query,fullPath,matched,name等路由信息参数。

router是“路由实例对象”，包括了路由的跳转方法(push、replace)，钩子函数等。

### 009.mvvm和mvc区别?它和其它框架(jquery)的区别是什么?哪些场景适合?

mvc和mvvm其实区别并不大。都是一种设计思想。主要就是mvc中Controller演变成mvvm中的viewModel。mvvm主要解决了mvc中大量的DOM 操作使页面渲染性能降低，加载速度变慢，影响用户体验。

区别：vue数据驱动，通过数据来显示视图层而不是节点操作。

场景：数据操作比较多的场景，更加便捷

### 010.vue的优点是什么?

低耦合。视图(View)可以独立于Model变化和修改，一个ViewModel可以绑定到不同的"View"上，当View变化的时候Model可以不变，当Model变化的时候View也可以不变。

可重用性。你可以把一些视图逻辑放在一个ViewModel里面，让很多view重用这段视图逻辑。

独立开发。开发人员可以专注于业务逻辑和数据的开发(ViewModel)，设计人员可以专注于页面设计。

可测试。界面素来是比较难于测试的，而现在测试可以针对ViewModel来写。

### 011.vuex面试相关

(1)vuex是什么?

vue框架中状态管理。

(2)vuex有哪几种属性?

有五种，分别是 State、 Getters、Mutations 、Actions、 Module

vuex的State特性

A、Vuex就是一个仓库，仓库里面放了很多对象。其中state就是数据源存放地，对应于一般Vue对象里面的data

B、state里面存放的数据是响应式的，Vue组件从store中读取数据，若是store中的数据发生改变，依赖这个数据的组件也会发生更新

C、它通过mapState把全局的 state 和 getters 映射到当前组件的 computed 计算属性中

vuex的Getters特性

A、getters 可以对State进行计算操作，它就是Store的计算属性

B、 虽然在组件内也可以做计算属性，但是getters 可以在多组件之间复用

C、 如果一个状态只在一个组件内使用，是可以不用getters

vuex的Mutations特性

Actions 类似于 mutations，不同在于：Actions 提交的是 mutations，而不是直接变更状态;Actions 可以包含任意异步操作。

(3)不用Vuex会带来什么问题?

可维护性会下降，想修改数据要维护三个地方;

可读性会下降，因为一个组件里的数据，根本就看不出来是从哪来的;

增加耦合，大量的上传派发，会让耦合性大大增加，本来Vue用Component就是为了减少耦合，现在这么用，和组件化的初衷相背。

### 012.如何让CSS只在当前组件中起作用

将当前组件的<style>修改为<style scoped>

### 013.响应式系统简述:

- 任何一个 Vue Component 都有一个与之对应的 Watcher 实例
- Vue 的 data 上的属性会被添加 getter 和 setter 属性
- 当 Vue Component render 函数被执行的时候, data 上会被 触碰(touch), 即被读, getter 方法会被调用, 此时 Vue 会去记录此 Vue component 所依赖的所有 data。(这一过程被称为依赖收集)
- data 被改动时（主要是用户操作）, 即被写, setter 方法会被调用, 此时 Vue 会去通知所有依赖于此 data 的组件去调用他们的 render 函数进行更新

### 014.谈谈你对虚拟DOM的理解？

首先,我们都知道在前端性能优化的一个秘诀就是尽可能少地操作DOM,不仅仅是DOM相对较慢,更因为频繁变动DOM会造成浏览器的回流或者重回,这些都是性能的杀手,因此我们需要这一层抽象,在patch过程中尽可能地一次性将差异更新到DOM中,这样保证了DOM不会出现性能很差的情况.

其次,现代前端框架的一个基本要求就是无须手动操作DOM,一方面是因为手动操作DOM无法保证程序性能,多人协作的项目中如果review不严格,可能会有开发者写出性能较低的代码,另一方面更重要的是省略手动DOM操作可以大大提高开发效率.

### 015.vue 中 key 值的作用？

当 Vue.js 用 v-for 正在更新已渲染过的元素列表时，它默认用“就地复用”策略。如果数据项的顺序被改变，Vue 将不会移动 DOM 元素来匹配数据项的顺序， 而是简单复用此处每个元素，并且确保它在特定索引下显示已被渲染过的每个元素。key 的作用主要是为了高效的更新虚拟DOM。

### 016.vue 中怎么重置 data?

使用Object.assign()，vm.$data可以获取当前状态下的data，
 vm.$options.data可以获取到组件初始化状态下的data。
 `Object.assign(this.$data, this.$options.data())`

### 017.组件中写 name 有什么作用？

- 项目使用 keep-alive 时，可搭配组件 name 进行缓存过滤
- DOM 做递归组件时需要调用自身 name
- vue-devtools 调试工具里显示的组见名称是由vue中组件name决定的

### 018.为什么需要 nextTick，nextTick 是做什么的?

Vue 是异步修改 DOM 的并且不鼓励开发者直接接触 DOM，但有时候业务需要必须对数据更改--刷新后的 DOM 做相应的处理，这时候就可以使用 Vue.nextTick(callback)这个 api 了。

$nextTick 是在下次 DOM 更新循环结束之后执行延迟回调，在修改数据之后使用 $nextTick，则可以在回调中获取更新后的 DOM

### 019.vue 首屏加载优化方案

- 把不常改变的库放到 index.html 中，通过 cdn 引入
- vue 路由的懒加载
- 不生成 map 文件（找到 config/index.js，修改为 productionSourceMap: false）
- vue 组件尽量不要全局引入
- 使用更轻量级的工具库
- 开启gzip压缩
- 首页单独做服务端渲染

### 020.vue3.0 有没有过了解？

关于vue 3.0，大致说了三个点，
 第一个是关于提出的新API setup()函数，
 第二个说了对于Typescript的支持，
 最后说了关于替换 Object.defineProperty 为 Proxy 的支持。

详细说了下关于Proxy代替带来的性能上的提升，因为传统的原型链拦截的方法，无法检测对象及数组的一些更新操作，但使用Proxy又带来了浏览器兼容问题。

### 021.说一下vue的双向绑定数据的原理

vue 实现数据双向绑定主要是：采用数据劫持结合发布者-订阅者模式的方式，通过 Object.defineProperty() 来劫持各个属性的 setter，getter，在数据变动时发布消息给订阅者，触发相应监听回调。

### 022.vue如何实现按需加载配合webpack设置？

webpack中提供了require.ensure()来实现按需加载。以前引入路由是通过import 这样的方式引入，改为const定义的方式进行引入。

不进行页面按需加载引入方式：import home from ‘…/…/common/home.vue’

进行页面按需加载的引入方式：const home = r => require.ensure( [], () => r (require(’…/…/common/home.vue’)))

### 023.vue 组件 data 为什么必须是函数?

因为js本身的特性带来的，如果 data 是一个对象，那么由于对象本身属于引用类型，当我们修改其中的一个属性时，会影响到所有Vue实例的数据。如果将 data 作为一个函数返回一个对象，那么每一个实例的 data 属性都是独立的，不会相互影响了

### 024.计算属性 computed 和事件 methods 有什么区别

我们可以将同一函数定义为一个 method 或者一个计算属性。对于最终的结果，两种方式是相同的

不同点：

- computed: 计算属性是基于它们的依赖进行缓存的,只有在它的相关依赖发生改变时才会重新求值
- 对于 method ，只要发生重新渲染，method 调用总会执行该函数

[Vue中watch、computed与methods的联系和区别](https://juejin.im/post/6844904086349807624)

### 025.vue 等单页面应用的优缺点：

优点：

- 良好的交互体验
- 良好的前后端工作分离模式
- 减轻服务器压力

缺点：

- SEO难度较高
- 前进、后退管理
- 初次加载耗时多

### 026.vue生命周期

vue的生命周期主要分为:创建前后、载入前后、更新前后、销毁前后
 beforeCreate，created，beforeMount，mounted，beforeUpdate，updated，beforeDestroy,destroyed

[Vue 生命周期与钩子函数](https://juejin.im/post/6844903905722122254#heading-0)

### 027.Vue 导航守卫(路由的生命周期)

全局的

- router.beforeEach
- router.beforeResolve
- router.afterEach

单个路由独享的

- beforeEnter

组件级的

- beforeRouteEnter
- beforeRouteUpdate
- beforeRouteLeave

[Vue 导航守卫(路由的生命周期)](https://juejin.im/post/6844903912340717575)

### 028.常见的跨域解决方案

前端配置vue.config.js
 后端配置各种头
 jsonp（只能解决get）

> 步骤：
>  1).去创建一个script标签
>  2).script的src属性设置接口地址   3).接口参数，必须要带一个自定义函数名，要不然后台无法返回数据   4).通过定义函数名去接受返回的数据

[常见的跨域解决方案](https://juejin.im/post/6844903912370110472)

### 029.什么是webpack及其优点

- 打包：可以把多个JavaScript文件打包成一个文件，减少服务器压力和下载宽带
- 转换：把扩展语言转换成为普通的JavaScript，让浏览器顺利运行。
- 优化：肩负起了优化和提升性能的责任

### 030.vue中项目如何优化？

- data优化
- SPA首屏加载优化
- 组件优化
- 巧妙利用指令v-if(show)，使用v-for要绑定key
- 使用Object.freeze
- 路由懒加载
- 动态导入组件
- 图片懒加载
- 第三方模块按需导入
- 骨架屏
- PWA缓存
- 预渲染
- 服务端渲染SSR
- 缓存和压缩
- HTTP优化

### 031.vue递归组件的使用

[递归组件](https://juejin.im/post/6844903913250881550)

### 032.vue的mode中hash与history的区别

hash模式重新加载的时候只加载#后面的
 history模式则是整个地址重新加载，不过他可以保存历史记录，方便前进后退

vue-router 有 3 种路由模式：hash、history、abstract

- hash:  使用 URL hash 值来作路由。支持所有浏览器，包括不支持 HTML5 History Api 的浏览器；
- history :  依赖 HTML5 History API 和服务器配置。具体可以查看 HTML5 History 模式；
- abstract :  支持所有 JavaScript 运行环境，如 Node.js 服务器端。如果发现没有浏览器的 API，路由会自动强制进入这个模式.

[Vue的mode中 hash 与 history 的区别](https://juejin.im/post/6844903902928879623)

### 033.vue中常用的命令

v-if   v-show区别
 v-for
 v-model
 v-bind
 v-on

[Vue 指令总结](https://juejin.im/post/6844903897291554824)

### 034.vue 的父组件和子组件生命周期钩子函数执行顺序？

vue 的父组件和子组件生命周期钩子函数执行顺序？

- 加载渲染过程
   父 beforeCreate -> 父 created -> 父 beforeMount -> 子 beforeCreate -> 子 created -> 子 beforeMount -> 子 mounted -> 父 mounted
- 子组件更新过程
   父 beforeUpdate -> 子 beforeUpdate -> 子 updated -> 父 updated
- 父组件更新过程
   父 beforeUpdate -> 父 updated
- 销毁过程
   父 beforeDestroy -> 子 beforeDestroy -> 子 destroyed -> 父 destroyed

### 035.在哪个生命周期内调用异步请求？

可以在钩子函数 created、beforeMount、mounted 中进行调用，因为在这三个钩子函数中，data 已经创建，可以将服务端端返回的数据进行赋值。但是本人推荐在 created 钩子函数中调用异步请求，因为在 created 钩子函数中调用异步请求有以下优点：

- 能更快获取到服务端数据，减少页面 loading 时间；
- ssr 不支持 beforeMount 、mounted 钩子函数，所以放在 created 中有助于一致性；

### 036.组件中 data 为什么是一个函数？

因为组件是用来复用的，且 JS 里对象是引用关系，如果组件中 data 是一个对象，那么这样作用域没有隔离，子组件中的 data 属性值会相互影响。

如果组件中 data 选项是一个函数，那么每个实例可以维护一份被返回对象的独立的拷贝，组件实例之间的 data 属性值不会互相影响；而 new Vue 的实例，是不会被复用的，因此不存在引用对象的问题。

### 037.vue组件间通信有哪几种方式？

- props
- $emit
- $attr
- $listener
- provide  inject  (隔代通信)
- $parent  $children
- vuex

[Vue组件之间的数据传递(通信、交互)详解](https://juejin.im/post/6844903911564787720)

### 038.Proxy 与 Object.defineProperty 优劣对比

Proxy 的优势如下:

- Proxy 可以直接监听对象而非属性；
- Proxy 可以直接监听数组的变化；
- Proxy 有多达 13 种拦截方法,不限于 apply、ownKeys、deleteProperty、has 等等是 Object.defineProperty 不具备的；
- Proxy 返回的是一个新对象,我们可以只操作新的对象达到目的,而 Object.defineProperty 只能遍历对象属性直接修改；
- Proxy 作为新标准将受到浏览器厂商重点持续的性能优化，也就是传说中的新标准的性能红利；

Object.defineProperty 的优势如下:

- 兼容性好，支持 IE9，而 Proxy 的存在浏览器兼容性问题,而且无法用 polyfill 磨平，因此 Vue 的作者才声明需要等到下个大版本( 3.0 )才能用 Proxy 重写。

### 039.虚拟 DOM 的优缺点？

优点：

- 保证性能下限： 框架的虚拟 DOM 需要适配任何上层 API 可能产生的操作，它的一些 DOM 操作的实现必须是普适的，所以它的性能并不是最优的；但是比起粗暴的 DOM 操作性能要好很多，因此框架的虚拟 DOM 至少可以保证在你不需要手动优化的情况下，依然可以提供还不错的性能，即保证性能的下限；
- 无需手动操作 DOM： 我们不再需要手动去操作 DOM，只需要写好 View-Model 的代码逻辑，框架会根据虚拟 DOM 和 数据双向绑定，帮我们以可预期的方式更新视图，极大提高我们的开发效率；
- 跨平台： 虚拟 DOM 本质上是 JavaScript 对象,而 DOM 与平台强相关，相比之下虚拟 DOM 可以进行更方便地跨平台操作，例如服务器渲染、weex 开发等等。

缺点：

- 无法进行极致优化： 虽然虚拟 DOM + 合理的优化，足以应对绝大部分应用的性能需求，但在一些性能要求极高的应用中虚拟 DOM 无法进行针对性的极致优化。

### 040.虚拟 DOM 实现原理？

虚拟 DOM 的实现原理主要包括以下 3 部分：

- 用 JavaScript 对象模拟真实 DOM 树，对真实 DOM 进行抽象；
- diff 算法 — 比较两棵虚拟 DOM 树的差异；
- pach 算法 — 将两个虚拟 DOM 对象的差异应用到真正的 DOM 树。

### 041.vue插槽的使用？

默认插槽
 具名插槽
 作用域插槽

[Vue 插槽(slot)使用(通俗易懂)](https://juejin.im/post/6844903920037281805)

### 042.active-class是哪个组件的属性？

vue-router模块的router-link组件。

### 043.怎么定义vue-router的动态路由以及如何获取传过来的动态参数？

在router目录下的index.js文件中，对path属性加上/:id。使用route对象的params.id。

[Vue 路由传值(传参)详解](https://juejin.im/post/6844903938752282631)

### 044.vue-loader是什么？使用它的用途有哪些？

vue文件的一个加载器。
 用途：js可以写es6、style样式可以scss或less、template可以加jade等根据官网的定义，

vue-loader 是 webpack 的一个 loader，用于处理 .vue 文件.

### 045.为什么避免 v-if 和 v-for 用在一起？

当Vue 处理指令时，v-for 比 v-if 具有更高的优先级，这意味着v-if将分别重复运行于每个v-for循环中。通过v-if 移动到容器元素，不会再重复遍历列表中的每个值。取而代之的是，我们只检查它一次，且不会在 v-if 为否的时候运算 v-for。

### 046.vue中Class 与 Style 如何动态绑定？

[Vue Class与Style绑定](https://juejin.im/post/6844903962286669837)

### 047.怎样理解 Vue 的单向数据流？

所有的 prop 都使得其父子 prop 之间形成了一个单向下行绑定：父级 prop 的更新会向下流动到子组件中，但是反过来则不行。这样会防止从子组件意外改变父级组件的状态，从而导致你的应用的数据流向难以理解。

额外的，每次父级组件发生更新时，子组件中所有的 prop 都将会刷新为最新的值。这意味着你不应该在一个子组件内部改变 prop。如果你这样做了，Vue 会在浏览器的控制台中发出警告。子组件想修改时，只能通过 $emit 派发一个自定义事件，父组件接收到后，由父组件修改。

### 048.直接给一个数组项赋值，Vue 能检测到变化吗？

由于 JavaScript 的限制，Vue 不能检测到以下数组的变动：

- 当你利用索引直接设置一个数组项时，例如：vm.items[indexOfItem] = newValue
- 当你修改数组的长度时，例如：vm.items.length = newLength

### 049.vue.js的核心是什么？

- 数据驱动（响应式）：data中的数据变了，视图才会变
- 组件化：拆组装，目的在于重用，方便，脏活累活一次干完，之后就轻松了

### 050.vue的常用修饰符？

- 事件修饰符：
   .stop  stopPropagation 阻止冒泡
   .prevent preventDefault 阻止默认行为
   .self 事件作用在自己身上才触发
   .once  事件只触发一次
- 键盘修饰符
   .enter 回车键
   .esc 退出键
- v-model 指令修饰符
   .lazy 由监听oninput事件转为onchange事件
   .number 尽量将文本框中的值转为数字，能转就转，不能转就不转
   .trim 去掉字符串的首尾空格

### 051.vue和react有什么区别？

- react整体是函数式的思想，把组件设计成纯组件，状态和逻辑通过参数传入，所以在react中，是单向数据流；
- vue的思想是响应式的，也就是基于是数据可变的，通过对每一个属性建立Watcher来监听，当属性变化的时候，响应式的更新对应的虚拟dom。

### 052.请说出vue.cli项目中src目录每个文件夹和文件的用法？

assets文件夹是放静态资源；
 components是放组件；
 router是定义路由相关的配置;
 view视图；
 app.vue是一个应用主组件；
 main.js是入口文件；

### 053.单页面应用和多页面应用区别及优缺点？

单页面应用（SPA），通俗一点说就是指只有一个主页面的应用，浏览器一开始要加载所有必须的 html, js, css。所有的页面内容都包含在这个所谓的主页面中。但在写的时候，还是会分开写（页面片段），然后在交互的时候由路由程序动态载入，单页面的页面跳转，仅刷新局部资源。多应用于pc端。

多页面（MPA），就是指一个应用中有多个页面，页面跳转时是整页刷新

单页面的优点：
 用户体验好，快，内容的改变不需要重新加载整个页面，基于这一点spa对服务器压力较小
 前后端分离
 页面效果会比较炫酷（比如切换页面内容时的专场动画）

单页面缺点：
 初次加载时耗时多
 页面复杂度提高很多
 导航不可用，如果一定要导航需要自行实现前进、后退。

### 054.vue-router单页面应用的切换？

在vue-router单页面应用中，则是路径之间的切换，也就是组件的切换。路由模块的本质 就是建立起url和页面之间的映射关系。

### 055.为什么不能用a标签？

至于为啥不能用a标签，这是因为用vue做的都是单页应用，就相当于只有一个主的index.html页面，所以你写的标签是不起作用的，必须使用vue-router来进行管理。

### 058.vue不能检测数组或对象变动问题的解决方法有哪些？

使用Proxy
 使用立即执行函数