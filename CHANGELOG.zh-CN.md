## 更新日志

### 1.1.3
*2017-01-09*

- 修复 DatePicker 页面加载后首次清空不会触发 `change` 事件，#2167
- 修复 DatePicker 选择下一年时，年份计算错误，#2152
- 新增 Table 的 `default-sort-prop` 和 `default-sort-order` 属性，#2182（by @njleonzhang）
- 修复有默认值的可搜索 Select 其他数据被过滤的问题，#2196
- 新增自定义 i18n 处理方法，方便和除了 `vue-i18n` 之外的插件使用，#2129
- 新增 Input `resize` 属性，#2263（by @Kingwl）
- 修复 Autocomplete 在 blur 事件触发时没有隐藏下拉列表的问题，#2247
- 修复 Tabs 嵌套使用时的样式问题，#2212（by @Kingwl）
- 修复 Tabs 默认激活非第一项时 tabBar 的显示位置不正确的问题，#2192

### 1.1.2
*2016-12-30*

- 修复 Vue 2.1.7 升级导致的 Table `sortable` 和 `fixed` 无法使用的问题
- 修正 Input Number 在手动输入越界值时，blur 触发时没有重置为原来的值的问题，#2098
- 移除 Collapse 的 `title` scoped slot, 并新增 `title` named slot，#2100
- 修复 TimePicker 范围选择无法使用的问题
- 修复 Tabs 删除非当前激活的 tab 后，当前激活的 tab 变化的问题，#2106
- 修复 Select 在使用方向键导航时控制台报错的问题，#2120
- 修复 Form 中可搜索的 Select 验证时机错误的问题，#2120

### 1.1.1
*2016-12-29*

- 修复由于编译而出现的不兼容新版 Vue 的问题

### 1.1.0 Helium
*2016-12-29*

新特性：
- 新增 Carousel、Collapse 组件
- 支持 SSR
- 组件内的滚动条样式优化
- Table 支持通过 [Scoped Slots](http://vuejs.org/v2/guide/components.html#Scoped-Slots) 传入模板；原来的 `inline-template` 仍然兼容，但是不再推荐使用，未来可能会被移除
- Table 支持展开行功能(Expandable rows)
- DatePicker 支持指定周起始日(first day of week)
- TimeSelect 支持设置 `maxTime`
- Autocomplete 新增 `popper-class`属性
- Tab-Pane 新增 name 为 label 的具名 `slot`，用于实现自定义标签内容

修复：
- DatePicker 的 `change` 事件错误地触发多次的问题，#2070
- Tabs 组件内 tab-pane 初始化时宽度抖动的问题，#1883

非兼容性更新：
- 最低兼容 Vue 2.1.6
- Form validateField() 方法回调的参数更新
- Alert 取消了 render-content 属性，现在自定义模板需要通过默认 slot 传入
- Input 和 Select 盒模型从 `block` 修改为 `inline-block`
- Tabs 盒模型从 `inline-block` 修改为 `block`，Tab-Pane 移除 `label-content` 属性
- Autocomplete 下拉列表现在直接插入到 `<body>` 标签下，而不是 `<el-autocomplete>` 下

### 1.0.9
*2016-12-27*

- 修复 DatePicker 不能正确触发 input 事件的问题，现在只有当日期改变时才触发，#1834
- 修复 Tree 在 Firefox 下会提示 event is undefined 的问题，#1945
- 新增 DatePicker 的 `change` 事件，返回和输入框一致的格式化后的值，#1841
- 新增 Table 的 `header-align` 属性，#1424
- 修复单选的 Table 在数据移除时，高亮状态仍然存在的问题，#1890
- 修复可搜索的 Select 在选项较多时的卡顿问题，#1933
- 修复多选的 Select 在禁用状态下仍然能够手动删除选中项的问题，#2001
- 修复 Col `xs` 分辨率下样式无效的问题，#2011
- 新增 Tab 组件的 `value` 属性并支持 `v-model` 用法，#2008
- 修复 Input Number 在某些条件下 change 事件被触发多次的问题，#1999
- 新增 DatePicker 的 `clearable` 属性，#1994
- 修复 Form 异步验证时某些条件下总是验证通过的问题，#1936

### 1.0.8
*2016-12-20*

- 修复 Popup 在叠加使用时阻止事件冒泡，#1677
- 修复 DatePicker 类型为 datetimerange 时无法选择时间的问题，#1758
- 修复 Slider 的 `change` 事件不能正确触发的问题，#1809
- 修复 Loading 的 spinner 在某些情况下转动时出现碎片的问题，#1786
- 新增 Select 的 `loading-text`、`no-data-text`、`no-match-text` 属性和 `visible-change` 事件，#1849
- 新增 DatePicker、Select 和 Tooltip 的 `popper-class` 属性，#1806
- 新增 Tree 的 `expand-on-click-node`、`current-node-key` 属性和 `current-change` 事件，#1805 #1807
- 新增 Table `row-click` 事件的第三个参数 `column`，#1808
- 修复 Checkbox 的在路由切换时因为 computed 属性被缓存导致的bug，#1860
- 新增 TabPanel `label-content` 渲染钩子方法中增加 tab 实例的参数，#1857
- 新增 NavMenu 组件增加无限级子菜单（vertical模式）的支持，#1851
- 新增 Checkbox 现在支持不绑定 value 也可以正常使用，#1818
- 新增 Progress 的 `onProgress` 钩子函数，#1782
- 修复 Tab 组件 active bar 在动态 label 下没有更新的问题，#1761
- 新增 Table 的 `filter-change` 事件和 TableColumn 的 `column-key` 属性，#1876
- 新增 Dropdown `hide-on-click` 属性，#1879

### 1.0.7
*2016-12-14*

- 修复 DatePicker 在有值的情况下 hover 清空按钮时会错误地显示弹框
- 修复 DatePicker 设置默认值为 null 会错误地显示时间值
- 新增 Table 的 `row-contextmenu` 事件和 `max-height` 属性，#1663 #1674
- 新增 MessageBox 的 `customClass` 属性，#1707
- 新增 Message 和 Notification 的 `iconClass` 和 `customClass` 属性，#1671
- 新增 Table 支持 empty slot，#1737
- 改进 InputNumber change 事件增加 old value 的参数

### 1.0.6
*2016-12-09*

- 新增 Tabs 组件的 `disabled` 属性，#1620
- 新增 DatePicker 的 input 支持 `size`，#1440
- 修复 DatePicker 为 `datetimerange` 类型并设置初始值时，面板未显示正确日期的问题，#1129
- 修复 DatePicker 切换年份时显示异常的问题，#1607
- 修复 DatePicker 点击 icon 未触发 clickoutside 的问题，#1604
- 修复 TimePicker 点击清空按钮后再次点击不会更新初始值的问题，#1583
- 修复 Select 远程搜索且 value 为对象类型时的显示问题，#1593
- 修复 Select 为 `disabled` 时，`clearable` 仍然可以工作的问题，#1619
- 修复 自定义背景颜色的 Switch 在动态切换 `disabled` 时，背景颜色错误的问题，#1627
- 修复 Table 的一些样式问题

### 1.0.5
*2016-12-06*

- 修复 Select 异步获取选项和绑定值时，输入框中显示 value 而不是 label 的问题，#1537
- 修复 Select 的初始值为一个空对象时会报错的问题，#1533
- 修复 Select 远程搜索有时不显示下拉框的问题，#1531
- 修复 Slider 拖动释放后，滑块有几率产生一小段位移的问题，#1546
- 修复 IE9 下 Steps 的样式问题，#1543
- 新增 Upload 对所有文件类型生成 URL 的功能，#1530
- 修复 TimeSelect 的样式，移除 flexbox, #1335

### 1.0.4
*2016-12-02*

- 新增 Input Number 的 `controls` 属性，#1473
- 修复 Checkbox Group、Radio Group 在异步赋值时出现的问题，#1511 #1514
- 增加 Notification 的 `offset` 属性，#1419
- 修复 Slider 在快速拖动时取值不准确的问题，#1458
- 修复 Slider 在某些情况下绑定值为多位小数的问题，#1450
- 修复 Select 在某些情况下绑定值和显示值不同步的问题
- 新增 Select 的 `multiple-limit` 和 `allow-create` 属性
- 修复 Tree 的叶子节点在点击展开后三角图标不消失的问题，#1438
- 修复 Tree 有时在获取子级数据后视图不更新的问题，#1439
- 修复 Table 在 windows 系统下的若干样式问题，#1464 #1507
- 修复 Table 多级表头与固定列同时使用时，多级表头第一列 label 不显示的问题，#1451
- 新增 Table 的 `row-dblclick` 事件，#1362

### 1.0.3
*2016-11-28*

- 修复 Pagination 的 `currentPage` 在某些情况下设置无效的情况，#1336
- 修复 DatePicker 为 `month` 且设置了 `disabledDate` 的情况下切换年份时界面未更新的问题，#1158
- 修复 DatePicker readonly 时未禁用清除按钮的问题，#1238
- 修复 Slider 绑定值为 `NaN` 以及 `step` 小于 1 时无法正常工作的问题，#1239 #1282
- 增加 Table 的多表头功能，#1312
- 增加 Table 的 `rowStyle` 属性，#1348
- 修复 TableColumn 的某些属性无法动态设置的问题，#1314
- 增加 Tree 的 `filter-node-method` 属性和 `filter` 方法，#1257
- 增加 Tree 的 `getCheckedKeys` 和 `setCheckedKeys` 方法，#1254
- 重构 Checkbox/Radio 支持嵌套 Group 绑定值，#1152
- 修复 Popper 在 keep-alive 下无法触发销毁的问题，#1359
- 增加 Form 中深对象验证的支持，#1363
- 增加 Autocomplete 里的 `append` 和 `prepend` API，#1369
- 增加 Pagination `pageSizes` 属性的动态支持，#1372
- 增加 Radio Button 自定义选中按钮样式的 API，#1380
- 增加 Menu Group 支持通过 slot 来设置 title，#1382
- 修复 DatePicker 选择年的 bug，#1385
- 新增 Upload 默认已上传的文件列表 API，#1393
- 增加 Checkbox `label` 属性绑定的多类型支持，#1400
- 增加 Tree 的 `setChecked` 方法，#1422

### 1.0.2
*2016-11-18*

- 新增 Table `context` 属性，可以指定自定义 column 内部可获取的上下文，#1161
- 新增 多种语言支持
- 修复 没有正确动态渲染语言的问题，#1160
- 新增 Alert 的 `render-content` 属性，#568
- 新增 Button 的 focus 样式，#982
- 修复 Switch 的 `change` 事件触发时机错误的问题，#1162
- 修复 TimeSelect 开始时间设置 `00:00` 后会被禁用的问题，#676
- 新增 Table `show-header` 属性，`header-click` 事件。#1195
- 完善 Table 的 `height` 属性，当 `height` 属性为字符串的时候，表示 Table 的高度受外部样式控制，#1195
- 修复 Table 的 `selection-change` 在某些情况下不触发的问题，#1198
- 修复 Table 动态修改 `fixed` 属性可能会造成锁定列不消失的问题，#1182

### 1.0.1
*2016-11-16*

- 修复 Pagination 错误地多次触发 `current-change` 事件的问题
- 修复 Switch 在 Form 中的样式错误，#967
- 修复 Loading 在某些情况下错误地锁定 `body` 滚动的问题，#968
- Col 组件的 `span` 属性不再是必填属性，在省略的情况下其默认值为 `24`
- 新增 DatePicker `disabled` 和 `editable` 属性，#976
- 修复 DatePicker 的 `readonly` 与原生行为一致，现在通过设置 editable=false 禁止输入但是可通过弹框选日期，#976
- 新增 Message 和 Notification 的 `close` 方法，用于手动关闭实例
- 新增 DatePicker 清除功能，#759
- 修复 Form 重置日期报错，#937
- 修复 Tab 设置active-name不是首个tab时的样式问题，#1034
- 修复 Table 的 inline-template 在 vue-loader 9.9.0 渲染报错
- 新增 Step 支持内容居中对齐，#994
- 修复 Upload 单独引入时提示 Progress 组件不存在，#1013
- Layout 支持响应式布局
- 新增 Dialog `show-close` 属性
- 修复 和 `vue-i18n` 一起使用时，未初始化 i18n 会报错，#973
- 修复 DatePicker 设置初始值后界面未更新 #1050
- 修复 DatePicker 月份选择器直接切换年份并未更新年份数据 #1070
- 新增 $loading 服务，用以调用 Loading
- 新增 Popover 可手动控制显示隐藏，将 trigger 设置为 `manual`
- 新增 Tree 的 `nodeKey`、`emptyText`、`checkStrictly`、`defaultExpandAll`、`autoExpandParent`、`defaultCheckedKeys`、`defaultExpandedKeys` 属性，`setCheckedNodes` 方法。


### 1.0.0

*2016-11-9*

- 修复 TimePicker 选择范围时结束时间小于开始时间会重置开始时间, #894
- 修复结合 `vue-i18n` 使用时会提示不能覆盖 `$t` 方法的问题
- 新增 Loading 自定义加载文案的功能，并优化了视觉表现
- 修复 Input blur 事件的参数不是 event 对象的问题
- `window.ELEMENT.locale.use` 改成 `window.ELEMENT.locale`

### 1.0.0-rc.9

*2016-11-07*

- 新增 MessageBox 确定按钮自动获取焦点, #721
- 修复 Popover focus 失效, #734
- 修复 Clickoutside 报错, #729
- 修复 DatePicker 选择日期范围时当选中同一天再调整时间会出错
- 更新 TimePicker 滚动条在 IE10+ 下隐藏
- 新增 Dropdown 的 command api #432
- 修复 Slider 在 Form 中的显示问题
- 修复 Upload 在 onSuccess、onError 钩子无法拿到服务端返回信息的问题
- 改善 tabs 现在支持动态更新
- Table 新增 highlightCurrentRow 属性、新增 current-change 事件
- TableColumn 的 showTooltipWhenOverflow 更名为 showOverflowTooltip（两个属性均可用）
- TableColumn 新增属性 render-header
- Pagination 新增属性 pageCount
- DatePicker 修复重置 value 后默认选中日期没有重置, #878

#### 非兼容性更新

- Upload on-error 钩子函数参数变更为 function(err, response, file), on-success 钩子函数参数变更为 function(response, file, fileList)

### 1.0.0-rc.8

*2016-10-28*

- 修复 Form reset method 对日期控件不起效的问题
- 修复 Dialog/Message Box/Tooltip/Popover/... 等若干组件的样式错误
- 修复 Message Box 的 prompt 在打开时会携带之前的验证状态的问题
- 修复 Autocomplete 的弹出框不会消失 #439
- 新增 Input 图标的点击事件 #444
- 修复 Loading 关闭后有几率滚动失效的问题
- 修复 远程搜索的 Select 不能正确渲染默认初始值的问题
- 修复 Switch 的 width 属性无效的问题
- Table 增加 rowClassName 属性
- TableColumn 增加 fixed 属性，可选值：true, false, left, right
- TableColumn 增加属性：filters、filterMultiple、filterMethod、filteredValue
- TableColumn[type="selection"] 增加 selectable 属性
- 修复 Input textarea 在动态赋值时 autosize 没有触发的问题
- 修复 Input Number min max 属性设置后点击加减出现的崩溃的bug
- 优化 TimePicker/DatePicker 输入日期行为
- 修复 DatePicker 输入禁用状态的日期却生效的问题 #484
- 新增 Slider 的 disabled 属性
- 新增 Menu 的 menu-trigger 属性
- 新增 i18n 的支持

#### 非兼容性更新

- Tabs 组件的 click 和 remove 事件回调参数从 name 改为事件对应的 tab 组件实例
- 全屏 Loading 现在默认不再锁定屏幕滚动。如果需要的话，可添加 `lock` 修饰符
- Table 删除属性 fixedColumnCount、customCriteria、customBackgroundColors、selectionMode
- Table 的 selectionchange、cellmouseenter、cellmouseleave、cellclick 事件更名为 selection-change、cell-mouse-enter、cell-mouse-leave、cell-click。
- Pagination 的 currentchange、sizechange 事件更名为 current-change、size-change

### 1.0.0-rc.7

*2016-10-13*

- Upload 新增 Data 属性支持额外数据的传输
- DatePicker 修复 `$t` 报错
- Popper 重构 vue-popper
- Pagination 修复输入后再点击切换，输入框的值不更新
- Step: 修复自定义 icon 的样式
- 修复 Tree 组件 checkbox 点击失效的问题
- Breadcrumb 增加路由跳转的功能
- 修复 可清空的 Select 中清空按钮的不恰当动画
- DatePicker 修复使用 Tab 键切换时弹出框未隐藏

### 1.0.0-rc.6

*2016-10-11*

- 修复 Tabs 切换后 Tab-panel 被销毁的问题
- 修复 TimePicker 错误的隐藏面板
- 修复 Table Cell 的样式, #204
- 修复 Menu default-active 属性不能为空的问题, #200
- 修复 Menu unique-opened 开启后无法展开子菜单的问题, #200
- 为 Notification 和 Message 的不同 type 添加独立的调用方法
- 为 Message Box 和 Dialog 添加 lockScroll 属性，用于定义是否在弹框出现时将 body 滚动锁定
- 新增 Input textarea 类型的 rows, autosize 属性
- 为 Tree 添加 getCheckedNodes 方法和 node-click、check-change 回调
- 新增 DatePicker 禁用日期功能 #253
- 修复 多选可搜索的 Select 下拉选项自动展开的问题
- 为 Dialog 添加 top 属性
- 修复 Menu 组件垂直模式下开启 router 属性会立刻跳转的问题 #295
- Checkbox change 事件现在只能被人为的交互操作所触发
- 新增 Checkbox checked 属性
- 修复 Select 远程搜索时使用键盘选择选项无法更新 v-model 的问题

#### 非兼容性更新

- Dropdown 组件重构，现在可以以更加的灵活方便的形式来自定义触发下拉的元素，以及可以定义下菜单的样式

### 1.0.0-rc.5

*2016-09-30*

- 修复 Table 头部不同步的问题
- 修复 Menu 组件 default-active 绑定动态值无法更新的问题
- 新增特性 Menu 组件中若选中子菜单项现在会自动展开所有父级菜单
- 修复 vue-popper 引入 popper 路径错误
- 修复 DatePicker 初始值是合法时间类型但无法设置成功的问题
- 修复 Pagination 的图标没有正确切换样式, #163
- 修复 Row 组件 align 属性不生效的问题
- 修复 Tabs 关闭标签页时对应 Tab-panel 没有移除的问题
- 新增 Menu 组件中 MenuItem 的 route 属性

#### 非兼容性更新
- Menu 组件的 `unique-opend` 属性修正为 `unique-opened`

### 1.0.0-rc.4

*2016-09-21*

- 修复 Select 多选时选项变为空数组后 placeholder 不出现的问题
- 修复 Time Picker 时间选择可滚动
- 修复 Tooltip 有时会错位的问题
- 修复 丢失的组件 css 文件
- 修复 Table 在 Safari 下边框没对齐
- 修复 TimePicker 图标样式被默认图标样式覆盖
- 修复 在 mounted 钩子函数中改变 Select 绑定值不生效的问题
- 修复 在多个依次出现的 Dialog 或 Message Box 全部关闭后页面有几率不可滚动的问题
- 修复 Table 初次渲染时宽度重新计算 #78
- 新增 时间、日期选择器增加 align 属性，可设置对齐方式
- 新增 TableColumn 的 align 属性
- 新增 autocomplete 的 select 事件

#### 非兼容性更新
- Select 组件样式的 `display` 属性默认值修改为 `block`

### 1.0.0-rc.3

*2016-09-09*

- 修复 Slider 存在输入框时，输入框与 Slider 的值不同步的问题
- 修复 Steps 样式
- 修复 无法安装的问题

### 1.0.0-rc.2

*2016-09-09*

- 修复 Upload 上传的问题，并增加上传成功和失败的钩子函数
- Button 组件增加 `nativeType` 属性，用于组件内 `<button>` 标签的原生 `type` 属性，默认值为 `button`
- 修复 Table 自定义模板中渲染静态数据错误
- 修复 Table 中被固定列的高度不与其他列的高度协调的问题
- 修复 Time Picker 的 `picker-options` 属性
- 修复一些组件图标丢失的问题
- 修复 远程搜索的 Select 在 Form 中的显示问题
- 修复 Input Number 输入小数和非数字值时的问题
- 修复 Select 选中 value 为 0 的值时绑定值不更新的问题
- 修复 Tree 取消选择某节点后，其同级节点均被取消的问题
- 修复 Upload 的 headers 属性设置无效
- 修复 Pagination 包含 sizes 子组件时 page-size 无效的问题
- 优化 增加打包成 commonjs 且不压缩的文件，默认引入 commonjs

#### 非兼容性更新
- Menu 组件 `mode` 属性默认值修改为 `vertical`
- Progress 组件升级，增加环形进度条的类型，以及增加了诸多属性，详细请查阅文档
- Popover 现在可以通过 slot 指定 reference

### 1.0.0-rc.1

*2016-08-30*

Element 1.0.0-rc.1 发布
