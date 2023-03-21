# Content

```javascript
async function getData(){
      return await Promise.resolve("I made it!");
}

const data = getData();
console.log(data)
```

Đoạn code trên định nghĩa một hàm bất đồng bộ `getData` và sử dụng từ khóa `await` để đợi cho một `Promise` được giải quyết.

Trong hàm `getData()`, `Promise.resolve("I made it!")` trả về một `Promise` đã được giải quyết với giá trị "I made it!". Hàm `getData()` sử dụng `await` để đợi cho `Promise` này được giải quyết và trả về giá trị "I made it!".

Trong phần tiếp theo của đoạn code, `const data = getData();` gọi hàm `getData` và gán kết quả trả về cho biến `data`. Do hàm `getData()` trả về một `Promise`, `data` sẽ là một `Promise object`, chứ không phải là giá trị "I made it!".

Sau đó, đoạn code tiếp tục in ra giá trị của biến `data` bằng cách sử dụng `console.log(data)`. Do đó, đầu ra sẽ là một `Promise object`, không phải là giá trị "I made it!".

Nếu muốn in ra giá trị "I made it!", chúng ta cần phải chờ cho `Promise` giải quyết bằng cách sử dụng từ khóa `await`, hoặc sử dụng `.then()` để thực hiện hành động khi `Promise` được giải quyết. Ví dụ:

```javascript
async function main(){
  const data = await getData();
  console.log(data);
}

main(); // output: "I made it!"
```
