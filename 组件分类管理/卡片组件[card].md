## 卡片标准组件

| 子类型名称            | 子类型说明                                        | 所有属性                                            |
| ---------------- | ---------------------------------------------------- | --------------------------------------------------- |
| MagicItem        | 一个图标在上，标题在下的路由导航栏                      | `[img,color,title,nav,container,size]`              |
| CardItem         | 一个图标在左，标题再右的路由导航栏                      | `[img,color,title,nav,container,size]`              |
| SubtitleCardItem | 同`CardItem`, 有副标题属性的路由导航栏                 | `[img,color,title,subtitle,nav,container,size]`     |
| RowItem          | 一个图标在左侧, 紧靠标题, 右侧是箭头                    | `[img,color,title,nav,group,container,size]`        |
| BoxItem          | 统计数字在上，标题在下的统计项，无路由属性, 有数据值格式  | `[number,title,format,container,size]`              |
| ToggleItem       | 用于设置项                                            | `[img,color,title,navon,navoff,container,size]`     |
| PaletteItem      | 用于单选项，右上角可以显示标记                          | `[tag,palette,color,badge,container,size]`                  |


### `PaletteItem` 的参数说明
| 参数             | 组件参数说明                                       |
| ---------------- | ------------------------------------------------- |
| tag              | 标签名称                                           |
| palette          | 标签颜色色板名称                                    |
| color            | 颜色值`#`,不是`#`开头为颜色索引名称                  |
| badge            | 用于在标题右则显示标识内容                           |
| badge.content    | 显示内容                                           |
| badge.container  | `css`风格集                                        |
| badge.cname      | 或传 `css`风格集名称                                |
| container        | 自定义`css`修饰                                    |
| size             | 大小选项 `[large,normal,small]`                    |


## 列表项子项组件
> 页面复合组件

| 组件名              | 组件                                                  | 组件参数说明                                                                           |
| ------------------ | ----------------------------------------------------- | ------------------------------------------------------------------------------------- |
| SubjectItem        | 主题信息组件[标题,副标题,图片,标签]                      | `[img,avatar,size, title,badge,tag, subtitle,tags[], status]`                          |
| MultiSubjectItem   | 多主题信息组件                                         | `[subjects[img,size,avatar, title,tag, subtitle,tags[], content, spacer[1x,2x,3x,4x]], actions:[], notes:[]]`
| ColumnItem         | 列信息组件[图标,标题,副标题,操作按钮],所有元素默认居中     | `[img,avatar,size, title,tag, subtitle, navigation:{icon, label, nav, navoff}, alignment]` |    


### 关于路由 `nav` 的说明
- 路由可以是页面的跳转路由，也可以是一个`api`, `api` 通常需要定义`method`,以及`parameters`,  `method`直接放在在`api`前面,如 `GET /api/v1/query/profile?userid=Bob`
- 参数则通过在`url`后面增加`?`指定。如 `GET /api/v1/query/profile?userid=Bob`
- `POST`/`PUT` 参数通常是`body`, 也是跟`GET`方式一样通过`?`提供，标准组件或框架基于`method`如果是`POST`或`PUT`自动转换为 `body` 形式提交, 如 `PUT /api/v1/profile/users/Bob?age=23&gentle=M`

### `SubjectItem` 的参数说明
> 左右靠展示信息的组件, 较通用, 右侧通常用于展示状态, 切换操作, 小按钮列表靠右上角从右开始排列

| 参数          | 组件参数说明                                            |
| ------------- | ------------------------------------------------------ |
| alignment     | 对齐方式,默认居中 `[center,left,right]`                 |
| bar           | 组件的左侧颜色状态条, 修饰作用                           |
| bar.color     | 状态条颜色,由状态决定,并通过父组件`binding`转换           |
| bar.width     | 状态条宽度，没有配置用默认值                             |
| bar.offset    | 偏离左侧容器的`padding`, 默认为`0`                      |
| bar.padding   | 垂直方向的`padding`大小, 默认为`0`                      |
| img           | 图片`img`, 默认显示为圆角图像                           |
| size          | 头像大小`[large,normal,small]`,默认为 `normal`          |
| boxSize       | 头像容器大小,用于占位, 留空                              |
| avatar        | 头像标识, `img`图片显示为头像, 值为任意字符,有定义即为头像 |
| title         | 标题, 由全局 theme 决定                                 |
| badge         | 用于在标题右则显示数量                                   |
| tag           | 标题右侧标签(单个)                                      |
| subheading    | 子标题, 在标题或`tag`的右侧                              |
| subtitle      | 副标题, 由全局 theme 决定                               |
| tags          | 副标题下面小标签                                        |
| content       | 格式化内容, 支持图标+表情格式化, 通过绑定转换             |
| status        | 组件右侧状态信息                                         |
| menus         | 组件右上角的菜单，一个固定的灰色小图标`..`                |
| menus[].label | 菜单名称                                                |
| menus[].nav   | 菜单操作路由                                            |
| actions       | 组件右上角的操作列表，灰色小图标靠右排列,大小固定          |
| actions[].img | 图标链接                                                |
| actions[].nav | 点击图标触发的路由                                      |
| navigation                     | 操作按钮定义, 数据类型为`object`       |
| navigation.status              | 保持按钮状态                          |
| navigation.icon                | 按钮图标                              |
| navigation.label               | 按钮标题                              |
| navigation.container           | 按钮容器风格`css`,或风格集名称         |
| navigation.nav                 | 默认`api`                            |
| navigation.switchoff.label     | 切换后标题                            |
| navigation.switchoff.icon      | 切换后图标                             |
| navigation.switchoff.container | 切换后图标                             |
| navigation.switchoff.nav       | 切换`api`                             |
| navigation.button              | 直接引用框架定义的按钮名称(字符), 或一个组件引用     |
| notes                          | 组件右侧信息展示栏, 可通过绑定进行格式化展示         |
| notes[].bullet                 | 信息展示项前端的字符或图标                         |
| notes[].content                | 信息格式化信息展示,支持图标+表情格式化, 通过绑定转换 |


>
> 以下数据通过`navlist`, `autolist`框架组件通过绑定传入
```json
{
    "img":"http://",
    "avatar":"any",
    "size":"normal",
    "bar":{
        "color": "#5566EE",
        "width": "8rpx",
        "offset": "4rpx"
    },
    "tag":"主题",
    "title":"标题",
    "subtitle":"副标题",
    "badge": 5,
    "tags":["客厅","餐厅"],
    "status": "待审批",
    "navigation": {
    },
    "actions": [
        "img":"https://",
        "nav":"POST/api/action/refresh"
    ]
}
```

### `MultiSubjectItem` 的参数说明
> 基本与`SubjectItem`的定义一致, 支持多主题垂直排列, 右侧展示信息面板, 此组件主要用于展示较大量的信息

| 参数                    | 组件参数说明                                            |
| ----------------------- | ------------------------------------------------------ |
| subjects[].alignment    | 当前`subject`的对齐方式 `[left,center,right,between]`   |
| subjects[].bar          | 当前`subject`左侧颜色状态条, 效果修饰作用                |
| subjects[].bar.color    | 状态条颜色,由状态决定,并通过父组件`binding`转换           |
| subjects[].bar.width    | 状态条宽度，没有配置用默认值                             |
| subjects[].bar.offset   | 偏离左侧容器的`padding`                                 |
| subjects[].padding      | 垂直方向的`padding`大小, 默认为`0`                       |
| subjects[].img          | 图片`img`, 默认显示为圆角图像                            |
| subjects[].avatar       | 头像标识, `img`图片显示为头像, 值为任意字符,有定义即为头像 |
| subjects[].size         | 组件大小`[large,normal,small]`,默认为 `normal`          |
| subjects[].boxSize      | 头像容器大小,用于占位, 留空                              |
| subjects[].title        | 标题, 由全局 theme 决定                                 |
| subjects[].tag          | 标题右侧的 tag                                          |
| subjects[].subheading   | 子标题, 在标题或`tag`的右侧                              |
| subjects[].bullet       | 信息展示项前端的字符或图标,可以是`https://`               |
| subjects[].content      | 格式化内容, 支持图标+表情格式化,通过绑定转换               |
| subjects[].spacer       | 与下一个`subject`的间隔选项`[1x,2x,3x,4x]`,`1x`代表`8rpx`|
| menus                   | 组件右上角的菜单，一个固定的灰色小图标`..`                |
| menus[].label           | 菜单名称                                                |
| menus[].nav             | 菜单操作路由                                            |
| notes                   | 组件右侧信息展示栏, 可通过绑定进行格式化展示               |
| notes[].bullet          | 信息展示项前端的字符或图标                                |
| notes[].content         | 信息格式化信息展示                                       |


### `ColumnItem` 的参数说明
> 所有信息全部居中展示, 同时支持按钮进行切换操作

| 参数                           | 组件参数说明                                        |
| ------------------------------ | ------------------------------------------------- |
| alignment                      | 对齐方式,默认居中 `[center,left,right]`             |
| img                            | 图片链接                                           |
| tag                            | 检签风格信息                                        |
| title                          | 标题, 由全局 theme 决定                             |
| subtitle                       | 副标题, 由全局 theme 决定                           |
| navigation                     | 按钮路由信息, 数据类型为 `object`                    |
| navigation.icon                | 按钮图标                                           |
| navigation.label               | 按钮标题                                           |
| navigation.nav                 | 默认`api`                                          |
| navigation.container           | 按钮容器风格`css`,或风格集名称                       |
| navigation.switchoff.label     | 切换后标题                                          |
| navigation.switchoff.icon      | 切换后图标                                          |
| navigation.switchoff.container | 切换后图标                                          |
| navigation.switchoff.nav       | 切换`api`                                          |
| navigation.button              | 直接引用框架定义的按钮名称(字符), 或一个组件引用       |




## Deprecated

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
    "title":"标题",
    "tag":"主题",
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

### `LinearRowItem` 的参数说明
> 仅有文字, 没有图像, 没有`tag`, 通过颜色修饰的简洁组件

| 参数                | 组件参数说明                                    |
| ------------------- | ---------------------------------------------- |
| bar                 | 左侧颜色状态条                                  |
| bar.color           | 状态条颜色,由状态决定,并通过父组件`binding`转换   |
| bar.width           | 状态条宽度，没有配置用默认值                     |
| title               | 标题, 由全局 theme 决定                         |
| subtitle            | 副标题, 由全局 theme 决定                       |
| content             | 其他信息内容 (挨着标题)                         |
| status              | 状态信息                                       |
