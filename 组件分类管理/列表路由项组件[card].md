## 路由项子项标准组件

| 子类型名称            | 子类型说明                                        | 所有属性                                            |
| ---------------- | ---------------------------------------------------- | --------------------------------------------------- |
| MagicItem        | 一个图标在上，标题在下的路由导航栏                      | `[img,color,title,nav,container,size]`              |
| CardItem         | 一个图标在左，标题再右的路由导航栏                      | `[img,color,title,nav,container,size]`              |
| SubtitleCardItem | 同`CardItem`, 有副标题属性的路由导航栏                 | `[img,color,title,subtitle,nav,container,size]`     |
| RowItem          | 一个图标在左侧, 紧靠标题, 右侧是箭头                    | `[img,color,title,nav，groupFirst,container,size]`  |
| BoxItem          | 统计数字在上，标题在下的统计项，无路由属性, 有数据值格式  | `[number,title,format,container,size]`              |


## 列表项子项组件
> 页面复合组件

| 组件名              | 组件                            | 组件参数说明                                          |
| ------------------ | ------------------------------- | ---------------------------------------------------- |
| AvatarCard         | 头像组件可用于动态页面、列表项组件 | `[avatar, title, subtitle, tag, tags[]], size: flow` |


### `AvatarCard` 参数说明

- `tag` 代表`title`右则的相对较大的`tag`
- `tags` 代表多个`tag`列表，相对较小
- `size` 代表组件大小或适用范围， 包括 `[flow,card]`, 默认为 `card`,  `flow` 头像较大， 用于动态页面组件
