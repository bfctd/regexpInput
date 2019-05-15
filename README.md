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
    text: '您输入的不符合',
    show: "bottom"
  },
  {el: '.code', event: 'blur', role: 'code', text: '请正确输入验证码'}
]

```
### new一个实例化对象并且配置参数
```
    new LoadingImgDelay({
        imgSrcList: imgSrc, // 真实图片列表数组,
        imgClassOrNodeName: 'img', // 要懒加载的图片标签名或class值，默认是img标签
        srcNameString: 'data-src' // 存储真实图片的data-*，默认是'data-src'
    })
```

# 注
### 1、所有图片默认的图为数组第一项
### 2、真实图片列表和所对应的img不对应，则不会更改

