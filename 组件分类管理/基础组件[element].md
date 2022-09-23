## 标准组件

> 注明：以下有部分会用到图标 图标地址在 /data?id=9999999 这个api中 如有需要 请从

| 组件名     | 说明                     | 页面说明链接                                 |
| ---------- | ----------------------- | ------------------------------------------- |
| search     | 搜索框                  | [组件说明](#search)                          |
| steps      | 步骤条组件              | [组件说明](#steps)                           |
| c-button   | 各类跳转按钮            | [组件说明](#c-button)                         |

### search

#### 配置项说明

| 属性            | 作用            | 默认值                             |
| --------------- | --------------- | ---------------------------------- |
| loadAPI         | 加载列表数据    | https://api.mock.smallsaas.cn/data |
| id              | loadAPI对应的id | 12311                              |
| field           | 搜索的字段      | name                               |
| itemModule.name | 列表子项        | stateSearchItem                    |

#### 子组件 stateSearchItem

| 属性                      | 说明                 | 类型                 |
| ------------------------- | -------------------- | -------------------- |
| itemNavigation            | 跳转路由             | String[值不带/pages] |
| list                      | 跳转列表             | Array                |
| list.id                   | 跳转参数             | String               |
| list.name                 | 列表中的参数【名称】 | String               |
| list.address              | 列表中的参数【地址】 | String               |
| list.state                | 列表中的参数【状态】 | Object               |
| list.state.example.number | 检查状态数值         | number               |
| list.state.example.status | 检查状态是否开启     | Boolean              |
| list.state.example.number | 自查状态数值         | number               |
| list.state.example.status | 检查状态是否开启     | Boolean              |


#### 自增 Search 子项方法

进入component/search/item

添加，props仅传item，编码完成后，在search中的子项添加处加入自己的组件即可

```json
{  
    "loadAPI":"https://api.mock.smallsaas.cn/data",
    "id":"12311",
    "field":"address",
    "itemModule":{
        "name":"stateSearchItem"
    }
}
```

一个搜索组件 只有一个子项

```json
{
	"version":"1",
	"name":"search",
	"title":"search展示",
	"pageStyle":{},
	"moduleContainer":{
	},
	"modules":[
		{
			"type":"search",
			"name":"",
			"key":"89084045-v4d5-7122-3300-1623511112885"
		}
	],
	"moduleData":{
		"89084045-v4d5-7122-3300-1623511112885":{
			"loadAPI":"http://xxx/page",
            "itemNavigation":"/pages/xxx",
            "params":{},//额外提交值
            "pn":true,//是否使用pageNo
            "pz":true,//是否使用pageSize
            "addIcon":true,//是否使用右上角的增加按钮
            "addUrl":"/pages/xxx/add",//右上角的增加按钮跳转的页面
            "hasEdit":true,//是否可编辑
            "settingUrl":"/page/xxx/edit",//编辑按钮跳转的页面
            "field":"name",//搜索对应api的字段，比如说 通过name搜索
            "itemModule":{
                "name":"stateSearchItem" //暂时只有该子项
            }
		}
	}
}
```

### steps

```json
{
	"version":"1",
	"name":"steps",
	"title":"steps展示",
	"pageStyle":{},
	"moduleContainer":{
	},
	"modules":[
		{
			"type":"steps",
			"name":"",
			"key":"89084045-v4d5-7122-3300-1623511112885"
		}
	],
	"moduleData":{
		"89084045-v4d5-7122-3300-1623511112885":{
			"steps":{
            	"step":[
                    {
						"text":"文本1"
                    },
                    {
                    	"text":"文本2"
                    },
                    {
                        "text":"文本3"
                    }
                ],
                "active":1 //被激活的条数
            }
		}
	}
}
```

### c-button

一个可以兼容多种跳转方式的按钮

```json
{
	"version":"1",
	"name":"cButton",
	"title":"cButton展示",
	"pageStyle":{},
	"moduleContainer":{
	},
	"modules":[
		{
			"type":"cButton",
			"name":"",
			"key":"89084045-v4d5-7122-3300-1623511112885"
		}
	],
	"moduleData":{
		"89084045-v4d5-7122-3300-1623511112885":{
			"type":"back",
            "value":1
            /* type类型说明
               back:返回，需要带value，不带返回上一页，value的值为何，则返回多少层
               exit:关闭当前页面，并跳转至某一页 需要带url
               jump:不关闭当前页面，跳转至某一页 需要带url
               reLaunch:关闭所有页面，跳转至某一页 需要带url
               tab:跳转至tab页 需要带url
            */
		}
	}
}
```