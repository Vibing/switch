
# switch
由自己编写的switch开关插件，支持beforeChange、afterChange和change事件。支持设置checked属性和disabled属性

# 使用

```html
<link rel="stylesheet" href="switch.css">
<script src="switch.js"></script>
```

##html

```html
<input type="checkbox" class="switchbox" text-on="ON" text-off="OFF" checked disabled >
```
##js
```javascript
  //初始化 如果有beforeChange回调，则必须执行next()函数，才会继续执行后面的回调
  $('.switchbox').switch({
    beforeChange:function(obj, state, next){
        console.log('before',obj,state);
        next();
    },
    afterChange:function(obj, state){
        console.log('after',obj,state);
    },
    change:function(obj, state){
        console.log('change',obj,state);
    }
  });
  
  //当checked状态改变时，默认会触发之前配置的beforeChange、afterChange和change回调函数
  $('.switchbox').setSwitch({
    trigger: true,  // false：不触发回调, 默认为true
    checked: false,
    disabled: true
  });
```
