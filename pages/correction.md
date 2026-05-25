---
layout: correctionLayout
kicker: Correction
title: Suggested correction
caption: Scroll the code when the solution exceeds the available height.
slide_info: false
---

```ts {all|1-4|6-8|10-19|all} twoslash
type Student = {
  name: string
  grade: number
}

function isPassing(student: Student): boolean {
  return student.grade >= 10
}

function formatPassingStudents(students: Student[]): string[] {
  return students
    .filter(isPassing)
    .map((student) => `${student.name}: ${student.grade}/20`)
}

const result = formatPassingStudents([
  { name: 'Ada', grade: 16 },
  { name: 'Grace', grade: 9 },
])
```
