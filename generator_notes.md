
#  Python Generator 系列筆記整理

---

##  一、什麼是 Generator？

- **Generator 是一種延遲計算（lazy evaluation）** 的函式。
- 每次呼叫 `yield` 只產生一筆資料，**節省記憶體使用量**。
- Generator 會回傳一個特殊物件 `<generator object ...>`，需透過 `next()` 逐個取值。

---

##  二、基本語法與使用

###  定義 generator 函式
```python
def my_gen():
    yield 42
```

###  使用 generator
```python
g = my_gen()
print(next(g))  # 輸出 42
print(type(g))  # <class 'generator'>
```

---

##  三、List vs Generator 的記憶體比較

###  List：一次性產生所有資料，佔記憶體
```python
def get_list():
    return [1, 2, 3]
```

###  Generator：逐一產生資料，節省記憶體
```python
def get_generator():
    yield 1
    yield 2
    yield 3
```

###  記憶體節省範例：
```python
def make_list(n):
    return [i for i in range(n)]  # 占大量記憶體

def make_gen(n):
    for i in range(n):
        yield i  # 幾乎不占記憶體
```

---

##  四、for 迴圈與 next()

###  正確使用：
```python
for i in my_gen():
    print(i)
```

###  錯誤使用（不要對 i 用 next）：
```python
for i in my_gen():
    print(next(i))  #  TypeError：'int' object is not an iterator
```

---

##  五、Python `for` vs C++ `for`

目的 -  Python: 走訪 iterable,                 C++: 控制流
原理 - Python: 自動使用 iter() + next(),       C++: 使用索引或疊代器增減
範例 - Python: for i in iterable:,            C++: for (int i = 0; i < n; ++i) 
延伸用途 - Python: 適合串流、大資料處理         C++: 適合範圍控制、STL 遍歷


---

## 六、C++ 中的 next 類似操作

```cpp
vector<int> v = {1, 2, 3};
for (auto it = v.begin(); it != v.end(); ++it) {
    cout << *it;  // ++it 類似 Python 的 next()
}
```

---

## 小結與學習建議

Quension:何時使用Generator？
Ans:處理大量資料、逐行讀檔、即時串流

Quension:為什麼不用 list？
Ans:一次產生太多資料會導致記憶體爆炸

Quension:for 會自動用 next() 嗎？
Ans:是的，Python for 自動處理 iterator