## 卡片标准组件

| 子类型名称            | 子类型说明                                        | 所有属性                                            |
| ---------------- | ---------------------------------------------------- | --------------------------------------------------- |
| MagicItem        | 一个图标在上，标题在下的路由导航栏                      | `[img,color,title,nav,container,size]`              |
| CardItem         | 一个图标在左，标题再右的路由导航栏                      | `[img,color,title,nav,container,size]`              |
| SubtitleCardItem | 同`CardItem`, 有副标题属性的路由导航栏                 | `[img,color,title,subtitle,nav,container,size]`     |
| RowItem          | 一个图标在左侧, 紧靠标题, 右侧是箭头                    | `[img,color,title,nav,group,container,size]`        |
| BoxItem          | 统计数字在上，标题在下的统计项，无路由属性, 有数据值格式  | `[number,title,format,container,size]`              |
| ToggleItem       | 用于设置项                                            | `[img,color,title,navon,navoff,container,size]`     |


## 列表项子项组件
> 页面复合组件

| 组件名              | 组件                                               | 组件参数说明                                                                           |
| ------------------ | -------------------------------------------------- | ------------------------------------------------------------------------------------- |
| SubjectItem        | 行信息组件[标题,副标题,图片,标签]                     | `[img, tag, title, subtitle, avatar, badge, tags[], status]`                          |
| ColumnItem         | 列信息组件[图标,标题,副标题,操作按钮],所有元素默认居中  | `[img, tag, title, subtitle, navigation:{icon, label, nav, navoff}, alignment]` |    
| ChecklistItem      | 清单组件[图标,标签,标题,属性列],属性个数不限制         | `[img, tag, title, subtitle, bullet, checklist[binding, format] ]`                    |


### `SubjectItem` 的参数说明
| 参数         | 组件参数说明                                            |
| ------------ | ------------------------------------------------------ |
| img          | 图片`img`, 默认显示为圆角图像                            |
| tag          | 标题右侧标签(单个)                                      |
| title        | 标题, 由全局 theme 决定                                 |
| subtitle     | 副标题, 由全局 theme 决定                               |
| avatar       | 头像标识, `img`图片显示为头像, 值为任意字符,有定义即为头像 |
| badge        | 用于在标题右则显示数量                                   |
| tags         | 副标题下面小标签                                        |
| status       | 组件右侧状态信息                                        |

>
> 以下数据通过`navlist`, `autolist`框架组件通过绑定传入
```json
{
    "img":"http://",
    "tag":"主题",
    "title":"标题",
    "subtitle":"副标题",
    "avatar":"any",
    "badge": 5,
    "tags":["客厅","餐厅"],
    "status": "待审批"
}
```


### `ColumnItem` 的参数说明
| 参数              | 组件参数说明                                        |
| ----------------- | -------------------------------------------------- |
| img               | 图片链接                                           |
| tag               | 检签风格信息                                        |
| title             | 标题, 由全局 theme 决定                             |
| subtitle          | 副标题, 由全局 theme 决定                           |
| navigation        | 路由信息, 数据类型为`object`                        |
| navigation.icon   | 操作接口                                           |
| navigation.label  | 操作标题,与`icon`二选一, 也可以同时展示              |
| navigation.nav    | 默认`api`                                          |
| navigation.navoff | 如果是切换操作, 为关闭`api`                         |
| alignment         | 默认居中 `[center,left,right]`                      |


>
```json
{
    "img":"http://",
    "tag":"主题",
    "title":"标题",
    "subtitle":"副标题",
    "bullet":"http://",
    "checklist":[
        {
            "binding":"floors",
            "format":"共{}层"
        },
        {
            "binding":"layer",
            "format":"第{}楼"
        }
    ]
}
```


### `ChecklistItem` 的参数说明
| 参数                | 组件参数说明                                   |
| ------------------- | --------------------------------------------- |
| img                 | 大图片链接                                     |
| tag                 | 检签                                           |
| title               | 标题, 由全局 theme 决定                         |
| subtitle            | 副标题, 由全局 theme 决定                       |
| bullet              | checklist前的标识符号, 可是字符, 也可以是`http://xy.url.svg` |
| checklist[]         | 绑定字段名称                                    |
| checklist[].binding | 绑定的props参数名称                           |
| checklist[].format  | 绑定参数的展示格式 `{"format": "{}行"}`          |

```json
{
    "img":"http://",
    "tag":"主题",
    "title":"标题",
    "subtitle":"副标题",
    "bullet":"http://",
    "checklist":[
        {
            "binding":"floors",
            "format":"共{}层"
        },
        {
            "binding":"layer",
            "format":"第{}楼"
        }
    ]
}
```