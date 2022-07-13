## 小程序标准动态组件JSON开发规范

小程序的动态类型可以通过json-mock api编写json来快速生成

### 标准动态页面

标准动态页面是由多个组件组成的

最常见的动态页面的JSON格式如下

```json
{
    "verison":"1",
    "name":"company_DataBase", //一般作为表单缓存
    "title":"动态页面标题",//小程序顶部标题
    "pageStyle":{},//页面样式 支持所有CSS格式
	"moduleContainer":{},//所有组件外层布局，部分组件支持
    "modules":[	//组件组，定义时组件使用
        {
            "type":"autolist",//组件的类型
            "name":"",//部分组件支持使用name来使用组件头部标识
            "key":"6F9619FF-8B86-D011-B42D-00C04FC964FF",//组件对应moduleData中的key,一般为guid格式 也可设定其他格式
            "container":{}//单独的组件布局 优先级大于moduleContainer
        }
    ],
    "moduleData":{//组件的数据，对应modules，不同组件的不同数据不一致
        "6F9619FF-8B86-D011-B42D-00C04FC964FF":{//这里需要与上方的key对应起来
            "loadApi":"https://xxx/list",//列表加载的api
            "method":"GET",//请求方法 默认GET
            "itemNavigation":"",//下一步跳转,?后可带参数名如/list?name&value,会默认拿loadApi里通过response过滤之后对应的值
            "response":{//过滤,列表子项默认拿list数组 所以这里的前面的list需要固定
                "list":"formdata.list"//意思是拿res.data.data.formdata.list的值
            },
            "request":{//请求时候传值
                "default":{//额外传值
                    "other":"111"
                },
                "pn":"pageNo",//决定第几页的字段
                "ps":"pageSize"//决定多少条数的字段
            },
            "itemModule":{
                "name":"company-state-to-enforcement"//类型
            },
            "options":{//部分列表项会有额外参数
                "showDelete":true
            }
        }
    }
}
```

### 标准动态表单

标准动态表单是由多个表单组件组成的

最常见的动态页面JSON格式如下

```json
{
    "loadApi":"http://xxx/form",//表单加载数据的api
    "saveApi":"http://xxx/form",//保存表单的api
    "fields":[//表单子项
        {	//不同组件有不同类型
            "__config__":{
                "label":"单行文本",//组件的标签
				"tag":"el-input",//决定组件的类型
                "tagIcon":"input",//决定组件的风格 多选 单选框会使用
                "required":true,//是否必填
                "layout":"colFormItem",//组件布局  rowFormItem一般作为头部
                "placeholder":"请输入单行文本",//组件提示
                "style":{//组件样式
                    "width":"100%"
                },
                "maxlength":null,//input textarea组件特有的限制长度
                "show-word-limit":false,//是否启用字数统计,需要与maxlength配合
                "readonly":false,//是否只读
                "disabled":false,//是否不可用
                "__vModel__":"field"//绑定的字段,用于提交，获取用
            }
        }
    ],
    "formBtns":true//表单是否存在提交按钮
}
```

### 标准动态列表

标准动态列表是有多个列表项组成的

常见动态列表的JSON格式如下

```json
{
	"loadApi":"https://xxx/list",//列表加载的api
    "method":"GET",//请求方法 默认GET
    "itemNavigation":"/test?name&value",//下一步跳转,默认会跳到/pages目录下的各项,?后可带参数名如/list?name&value,会默认拿loadApi里通过response过滤之后对应的值
    "response":{//过滤,列表子项默认拿list数组 所以这里的前面的list需要固定
        "list":"formdata.list"//意思是拿res.data.data.formdata.list的值
    },
    "request":{//请求时候传值
        "default":{//额外传值
            "other":"111"
        },
        "pn":"pageNo",//决定第几页的字段
        "ps":"pageSize"//决定多少条数的字段
    },
    "itemModule":{
        "name":"company-state-to-enforcement"//类型
    },
    "options":{//部分列表项会有额外参数
        "showDelete":true
    }
}
```

