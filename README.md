# ui-action-sheet
simple and pure javascript action-sheet component
## 综述

* 版本：1.0.0
* 浏览器支持：h5所有浏览器

## 安装

```
<script src="ui-action-sheet.js"></script>
window.ActionSheet;
// or webpack
var ActionSheet = require('ui-action-sheet');
```

## 使用方法

简单用法

```
ActionSheet.show(function () {
    // 点击确定后执行此回调
});

ActionSheet.show('确定不再关注此人', function () {
    // 点击确定后执行此回调
});

ActionSheet.hide(function () {
    // 组件隐藏后执行此回调
});

```

进阶用法

```
ActionSheet.show({
    title: '请选择性别', // 默认为'请选择操作'
    label: ['男', '女', '雄', '雌'],
    fn: function (index) {
        switch (index) {
            case 1:
                // 选择"男"
                break;
            case 2:
                // 选择"女"
                break;
            case 3:
                // 选择"雄"
                break;
            case 4:
                // 选择"雌"
                break;
        };
    },
    easing: 'ease-in-out', // 动画贝塞尔曲线
    in: 300, // 动画入场时间默认300ms
    out: 300 // 动画退场时间
});
```


## API

### .show()

简单用法，部分参数使用默认值

* .show(fn)
    * fn: 点击确认按钮执行的回调函数

* .show(title, fn)
    * title {string}: 组件标题
    * fn: 点击确认按钮执行的回调函数

进阶用法，参数可自定义

* .show(option)
    * option {object}
        * title {String}: 默认为'请选择操作'
        * label {Array}: 每个选项的标题，按数组顺序从上到下排列
        * fn {Function}: 点击选项回调函数
        * easing {String}: 默认'ease-in-out', 动画贝塞尔曲线
        * in {Number}: 默认300ms, 动画入场时间
        * out {Number}: 默认300ms, 动画退场时间

### .hide()

隐藏组件

* .hide(fn)
    * fn: 组件隐藏后执行的回调
