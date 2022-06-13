:: BASE_DOC ::

## API
### ImageViewer Props

名称 | 类型 | 默认值 | 说明 | 必传
-- | -- | -- | -- | --
closeBtn | Boolean / Slot / Function | true | 是否展示关闭按钮，值为 `true` 显示默认关闭按钮；值为 `false` 则不显示关闭按钮；也可以完全自定义关闭按钮。TS 类型：`boolean | TNode`。[通用类型定义](https://github.com/Tencent/tdesign-mobile-vue/blob/develop/src/common.ts) | N
deleteBtn | Boolean / Slot / Function | true | 是否展示删除按钮。TS 类型：`boolean | TNode`。[通用类型定义](https://github.com/Tencent/tdesign-mobile-vue/blob/develop/src/common.ts) | N
images | Array | [] | 图片数组。TS 类型：`Array<string>` | N
index | Number | - | 当前预览图片所在的下标。支持语法糖 `v-model:index` | N
defaultIndex | Number | - | 当前预览图片所在的下标。非受控属性 | N
showIndex | Boolean | false | 是否显示页码 | N
trigger | String / Slot / Function | - | 触发图片预览的元素，可能是一个预览按钮，可能是一张缩略图，完全自定义。TS 类型：`string | TNode`。[通用类型定义](https://github.com/Tencent/tdesign-mobile-vue/blob/develop/src/common.ts) | N
visible | Boolean | false | 隐藏/显示预览。支持语法糖 `v-model` 或 `v-model:visible` | N
defaultVisible | Boolean | false | 隐藏/显示预览。非受控属性 | N
onClose | Function |  | TS 类型：`(context: { trigger: 'close-btn' | 'overlay' | 'esc'; e: MouseEvent | KeyboardEvent }) => void`<br/>关闭时触发，事件参数包含触发关闭的来源：关闭按钮、遮罩层、ESC 键 | N
onIndexChange | Function |  | TS 类型：`(index: number, context: { trigger: 'prev' | 'next' }) => void`<br/>预览图片切换时触发，`context.prev` 切换到上一张图片，`context.next` 切换到下一张图片 | N

### ImageViewer Events

名称 | 参数 | 描述
-- | -- | --
close | `(context: { trigger: 'close-btn' | 'overlay' | 'esc'; e: MouseEvent | KeyboardEvent })` | 关闭时触发，事件参数包含触发关闭的来源：关闭按钮、遮罩层、ESC 键
index-change | `(index: number, context: { trigger: 'prev' | 'next' })` | 预览图片切换时触发，`context.prev` 切换到上一张图片，`context.next` 切换到下一张图片
