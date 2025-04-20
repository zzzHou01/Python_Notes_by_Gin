# Line Break, Indent, Continue - Python 換行、縮排、續行筆記 by Gin & Aaliyah

## 換行 `\n`
```python
print("第一行\n第二行")
```

## tab 縮排 `\t`
```python
print("名稱\t成績")
print("小明\t100")
print("小華\t90")
print("小美\t80")
```

## 方法一：反斜線 `\` 續行（較舊方式）
```python
text = "今天是個好日子，我想好好學習程式，" \
       "從 generator 學到 class，從 for loop 學到 AI"
print(text)
```

## 方法二：括號內自動允許換行（推薦方式）
```python
msg = (
    "今天是個好日子，"
    "我決定要學 Python，"
    "不學到會絕不放棄"
)

nums = [1, 2, 3,
        4, 5, 6,
        7, 8, 9]
```

## 方法三：三引號字串 `'''` 或 `"""`
```python
long_string = '''這是一段非常非常長的字串，
我希望可以跨行書寫，
這樣比較清楚。'''
print(long_string)
```
