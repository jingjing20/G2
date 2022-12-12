---
title: selectX
order: 1
---

按照指定通道进行分组，根据 x 通道和 selector 从每组选择出数据。

## 开始使用

具体案例可以参考 [select](/api/transform/select)，下面伪代码示意一下。

```ts
chart
  .point()
  // ...
  .transform({
    type: 'selectX',
    selector: 'mean',
    /* options */
  });
```

## 选项

| 属性               | 描述                                           | 类型                     | 默认值                 |
|-------------------|------------------------------------------------|-------------------------|-----------------------|
| groupBy           | 针对指定的通道进行分组                             | `string` \| `string[]`  | `series`              |  
| selector          | 针对每个分组，使用指定的通道进行指定的数据抽取，输出到 x 通道 | `Selector`         |  `first`              |

```ts
type Selector =
  | 'min'
  | 'max'
  | 'first'
  | 'last'
  | 'mean'
  | 'median'
  | ((I: number[], V: number[]) => number[]);
```