# M01W02
Data Structure(IoU, NMS, and Histogram)

## Sự khác biệt giữa Immutable và Mutable
Dưới là 2 ví dụ đơn giản:
```python
#Immutable
def square1(data):
  results = []
  for value in data:
    results.append(value*value)
  return results
```

```python
#Mutable
def square2(data)
  for i in range(len(data)):
    data[i] = data[i]*data[i]
```
Sự khác biệt giữa 2 hàm 'square1' và 'square2' là hàm 1 truyền vào 'data' và trả về results, trong khi đó hàm số 2 cũng truyền vào data và output cũng là 'data' vậy nên, hàm 1 sẽ không làm ảnh hưởng tới 'data', còn hàm 2 sẽ thay đổi 'data'
