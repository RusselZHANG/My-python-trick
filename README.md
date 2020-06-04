# My-python-trick

Accumulated python write-up
Python auto type     
## Data structure

### 1. Access to data structure
----------------------------------
* Dictionary:
```python
a = dict()
for key in a:
    value = a[key]
```
Or put this together:
```python 
keys =[]
values=[]
for k,v in a.item()：
    keys.append(k)
    values.append(v)
```
Or dict.get():
```python 
a = dict(zip(['one', 'two', 'three'], [1, 2, 3]))
dict.get('one', default='Not found')
```
* list2darray: without pre-allocating memory
The great difference between np.darray and list: np.darray[:,:] is accessible but list[:,:] not. To transform, use sentence below: 
```python
dist_2d = np.array(dist_2d, dtype=float)
```
### 2. Open/close file while using: return error information then maintain
----------------------------------
1st version: Useful but long
```python
file = open("/tmp/foo.txt")
try:
    data = file.read()
finally:
    file.close()
 ```
2nd version: with sentence 
 ```python
with open("/tmp/foo.txt") as file:
    data = file.read()
```

### 3. Heapq(priority queue)
--------------------------
Using heapq.heapify instantiate heap，it is used for sorting ，using heappush and heappop to output the result.<br>
heap[0] is the min of heap
```python
#defining:
nums = [2, 3, 5, 1, 54, 23, 132]
heapq.heapify(nums)
print(nums[0],[heapq.heappop(nums) for _ in range(len(nums))])

#value extraction
print(heapq.nlargest(3, nums))
print(heapq.nsmallest(3, nums))

"""
output：
[132, 54, 23]
[1, 2, 3]
"""

#sorting
def heapsort(iterable):
   h = []
   for value in iterable:
       heappush(h, value)
   return [heappop(h) for i in range(len(h))]
"""   
heapsort([1, 3, 5, 7, 9, 2, 4, 6, 8, 0])
output:
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
"""
```

