# Logic Programming

**_ใช้ภาษาโปรแกรมมิ่งใดเขียนก็ได้_**

ให้ออกแบบและเขียน function เพื่อสร้างคำสั่ง SQL สำหรับ query ข้อมูลจากตาราง 1 ตาราง
โดย

- รับชื่อ field ที่ต้องการ select โดยรับได้มากกว่า 1 field
- รับชื่อตารางที่ต้องการ query
- รับเงื่อนไขการ query ได้มากกว่า 1 เงื่อนไข โดยกำหนดให้เงื่อนไขเป็นการเปรียบเทียบ `=` เท่านั้น และแต่ละเงื่อนไขเชื่อมกันด้วย `AND` operator เพียงอย่างเดียว


_ตัวอย่างการใช้งานในภาษา JS (ไม่จำเป็นต้องรับข้อมูลตามตัวอย่างนี้ก็ได้)_

```js
const fields = ['first_name', 'last_name', 'age', 'gender'];
const table = 'students';
const conditions = [
    {field: 'group', value: 10},
    {field: 'year', value: 2021},
    {field: 'flag', value: true}
];
const strSQL = genStrSQL(fields, table, conditions);

/* output strSQL
"SELECT first_name, last_name, age, gender
FROM students
WHERE group = 10 AND
	year = 2021 AND
	flag = true;"
*/
```