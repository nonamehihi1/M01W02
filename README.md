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

## List(Mutabel) và String(Immutable)

Trong Python, khi có 2 list giống nhau thì địa chỉ bộ nhớ sẽ khác nhau, không giống như String, 2 String giống nhau sẽ chung địa chỉ bộ nhớ, Python gọi đó là String interning (hay tái sử dụng vùng bộ nhớ)

Bạn có thể chạy 2 đoạn code dưới để biêt kết quả:
```python
List1 = [1,2,3]
list2 = [1,2,3]

print("list1_id:", id(List1))
print("list2_id:", id(list2))
```

```python
str1 = 'hello'
str2 = 'hello'

print(id(str1), id(str2))
```
## ShallowCopy và DeepCopy

Shaloowcopy chỉ sao chép 'vỏ ngoài', còn deep thì sao chép hết toàn bộ, kể cả những phần từ lồng bên trong
### Lưu ý, nếu trong các cấu trúc dữ liệu chứa kiểu dữ liệu đơn giản như 'int' hay 'str' thì sẽ không thấy sự khác biệt 
```python
import copy
a = [1,2,3]
b = copy.copy()

print(a,b)
```
Do list chỉ có 1D nên shallowcopy hay deepcopy ở trường hợp này đều giống nhau, đều không ảnh hưởng tới giá trị ban đầu

Đối với những kiểu dữ liệu khó hơn, ví dụ từ 2D trở lên, thì sẽ có sự khác biệt
```python
a = [[1, 2], [3, 4]]
b = copy.copy(a)       # shallow copy

a[0][0] = 99           # thay đổi phần tử trong list lồng

print(a)  # [[99, 2], [3, 4]]
print(b)  # [[99, 2], [3, 4]]  ❗ bị ảnh hưởng

```


