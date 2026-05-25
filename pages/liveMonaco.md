---
layout: liveMonacoLayout
kicker: Live Monaco
title: Edit code live
instructions: Ask learners to suggest a variation, then update the code in Monaco.
mode: single
slide_info: false
---

```ts {monaco} {height:'410px', lineNumbers:'on'}
type Product = {
  name: string
  price: number
}

function applyDiscount(product: Product, percent: number): Product {
  return {
    ...product,
    price: product.price * (1 - percent / 100),
  }
}

const book = { name: 'TypeScript handbook', price: 40 }
const discounted = applyDiscount(book, 15)

discounted
```
