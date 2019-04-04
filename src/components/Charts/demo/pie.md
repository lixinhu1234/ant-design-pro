---
order: 5
title: 饼状图
---

```jsx
import { Pie, yuan } from 'ant-design-pro/lib/Charts';

const salesPieData = [
  {
    x: '业务域',
    y: 4544,
  },
  {
    x: '数据层',
    y: 3321,
  },
    
];

ReactDOM.render(
  <Pie
    hasLegend
    title="合计"
    subTitle="合计"
    total={() => (
      <span
        dangerouslySetInnerHTML={{
          __html: yuan(salesPieData.reduce((pre, now) => now.y + pre, 0))
        }}
      />
    )}
    data={salesPieData}
    valueFormat={val => <span dangerouslySetInnerHTML={{ __html: yuan(val) }} />}
    height={294}
  />,
  mountNode,
);
```
