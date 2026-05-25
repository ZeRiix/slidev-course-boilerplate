---
layout: staticCodeExampleLayout
kicker: Static code
title: Read a function in multiple passes
caption: The code stays static while key lines appear as the explanation progresses.
variant: dark
slide_info: false
---

```ts {all|1-5|7-10|12-18|20|all} twoslash
type User = {
  id: number
  name: string
  isActive: boolean
}

function formatUserLabel(user: User): string {
  const status = user.isActive ? 'active' : 'inactive'
  return `${user.name} (#${user.id}) - ${status}`
}

const users: User[] = [
  { id: 1, name: 'Ada', isActive: true },
  { id: 2, name: 'Linus', isActive: false },
]

const labels = users.map(formatUserLabel)

console.log(labels)
```

::note::
Replace this note with the points to mention aloud: types, transformation, return value, edge cases.
::
