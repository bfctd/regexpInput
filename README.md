# regexpInput-formRuleTest
# 基于jquery自己开发的正则匹配插件


### 首先引入官方jquery文件
```
<script src="./jquery.js"></script>
```

### 再引入formRuleTest本插件
```
<script src="./LoadingImgDelay.js"></script>
```
### 创建自己的html
```
<form>
  <input />
</form>
```

### 直接使用$('节点').formRuleTest(配置对象option)
```
$("NODE").formRuleTest({ // NODE 是所需正则匹配的所含顶层节点，规则遵循就jQ，可以是类名、标签名选择器亦或是原生DOM
    set: list, // 需要进行正则匹配的列表项
    allTest: true // 查询是否所有的都匹配
})

let list = [ 
  {
    el: '.phone.p', // 【必填】只能是NODE的子元素，只能是类名或id名，类名需与其他不相同。
    event: 'blur', // 【必填】只能是jQ支持的事件名遵循jQ事件规则。
    role: 'phone', // 【二选一】匹配规则关键字[phone匹配手机号|code匹配6位验证码|icord匹配身份证号|email邮箱|mast必填项|int整数]
    regexp: '/^1$/' //【二选一】regexp和role只能出现一个，regexp为自定义的正则字符串
    show: "bottom", //【非必填】错误提示显示的位置，默认值为border
    text: '输入的不正确' //【非必填】提示文本，位置为bottom时有效，默认 “输入的不正确”
  }
]

```
## 点击提交按钮 需要验证字段中是否有无不匹配
```
    //点击提交按钮需要验证 字段中是否有无不匹配
    例子：
    $('button').on('click', () => {
        var canAcc = ($(".from").formRuleTest({set: list, allTest: true}))
        if (canAcc) {
            //ajax
        }
    })
```


