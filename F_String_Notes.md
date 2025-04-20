# F String Notes - Python 格式化字串筆記 by Gin & Aaliyah

## 1. 基本用法
```python
name = "Gin"
print(f"Hello, World!")
print(f"Hello, {name}!")  # name 是一個變數，會被替換成它的值
```

## 2. 數學運算
```python
print(f"2 + 3 = {2 + 3}")
```

## 3. 格式化數字
```python
print(f"Pi is approximately {3.14159:.2f}")  # 保留兩位小數
print(f"Pi is approximately {3.14159:.3f}")  # 保留三位小數
```

## 4. 字串對齊與格式化
```python
print(f"Hello, {'World':<10}")  # 左對齊
print(f"Hello, {'World':>10}")  # 右對齊
print(f"Hello, {'World':^10}")  # 中間對齊
```

## 5. 標題裝飾排版
```python
title = "Gin 的成績單"
print(f"{title:-^30}")  # 輸出：--------Gin 的成績單--------
```

## 6. 使用變數與運算式
```python
name = "Gin"
age = 21
print(f"{name} is {age} years old.")
print(f"{name} will be {age + 1} next year.")
```

## 7. 使用函數
```python
def greet(n):
    return f"Hello, {n}!"
print(f"{greet(name)}")
```

## 8. 多行 f-string（搭配括號）
```python
msg = (
    f"Hi {name},\n"
    f"Your score is {95:.1f},\n"
    f"Keep it up!"
)
print(msg)
```

## 9. 巢狀函數呼叫
```python
score = 88.456
def format_score(s):
    return f"{s:.2f}"
print(f"你的分數是 {format_score(score)}")
```

## 10. 字典搭配 f-string
```python
student = {"name": "Gin", "score": 95}
print(f"{student['name']} 的成績是 {student['score']}")
```

## 11. datetime 格式化
```python
from datetime import datetime
now = datetime.now()
print(f"現在時間：{now:%Y-%m-%d %H:%M:%S}")
```

## 12. raw string 防跳脫
```python
path = r"C:\Users\Gin"
print(f"路徑為：{path}")
```

## 13. 三引號大段 f-string
```python
long_msg = f'''
Hello {name},

歡迎使用 f-string！
這是一段多行字串內容。

Have a great day!
'''
print(long_msg)
```

## 錯誤示範
```python
print("Hello, {name}")  # 沒加 f，會輸出原樣字串
```
