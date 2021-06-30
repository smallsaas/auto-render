## 如何使用？

### 配置项说明

| 属性            | 作用            | 默认值                             |
| --------------- | --------------- | ---------------------------------- |
| loadAPI         | 加载列表数据    | https://api.mock.smallsaas.cn/data |
| id              | loadAPI对应的id | 12311                              |
| field           | 搜索的字段      | name                               |
| itemModule.name | 列表子项        | stateSearchItem                    |

### 例

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





## 搜索子项

### stateSearchItem

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



## 自增Search子项方法

进入component/search/item

添加，props仅传item，编码完成后，在search中的子项添加处加入自己的组件即可