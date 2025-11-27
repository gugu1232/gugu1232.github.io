### 关于pwd和cd

* “Present Working Directory” 指的是你**当前所在的文件夹路径**。



* `cd` 是 “change directory” 的缩写。

  ```bash
  cd Documents
  ```

  表示进入当前目录下的 `Documents` 文件夹。

* 其他常见用法：

  ```bash
  cd ~        # 回到用户主目录
  cd ..       # 返回上一级目录
  cd /        # 到系统根目录
  cd /path/to/folder  # 直接进入指定路径
  ```



**使用 `ls` 命令列出当前目录下的文件和文件夹**

-





















pixi

pixi init
pixi shell #进入pixi环境

---



关于if 
“These conditions are necessarily exhaustive.”
中文意思是：“这些条件必定涵盖所有情况。”
也就是说，这个 if–elif–else 结构一定会执行其中一个分支，不会出现“所有条件都不满足而什么都不执行”的情况。

在 Python 中：
if 先判断第一个条件，
如果它不成立，接着判断第一个 elif，
再不成立就判断下一个 elif，
如果所有前面的条件都不成立，就执行 else。

这张图片的问题是：

> **if / elif / elif / else 块在 Python 中是什么样的？**

正确答案（绿色框）是：

> **short-circuit（短路）**，意思是：
> 只有第一个条件为 `True` 的语句块会被执行。
> 如果没有任何条件为 `True`，则执行 `else` 块。

---

“**短路 (short-circuit)**” 的意思是：一旦某个条件满足（即结果为 `True`），Python 就不会再检查后面的条件。

举个例子：

```python
if a:
    print("A")
elif b:
    print("B")
elif c:
    print("C")
else:
    print("D")
```

执行逻辑是：

1. 如果 `a` 为真 → 执行 `print("A")`，**跳过后面的所有 elif/else**。
2. 如果 `a` 为假但 `b` 为真 → 执行 `print("B")`，也不会再检查 `c` 或执行 `else`。
3. 如果 `a`、`b`、`c` 都为假 → 执行 `else`。

---

⚠️ 这和右边选项中提到的 “using Boolean logic, inclusive or（包容性或）” 不同。
在那种情况下，如果逻辑是 `if a or b or c: ...`，那么多个条件可能被一起评估。
但在 `if/elif/else` 结构中，**只会执行一个分支**，不会多个同时执行。




---

## 🚀 一、常规工作流程概览

```
(修改文件)
 ↓
git status        # 查看修改了哪些文件
 ↓
git add .         # 暂存修改
 ↓
git commit -m "Your commit message"
 ↓
git pull origin main --rebase   # 更新远端代码（防止冲突）
 ↓
git push origin main            # 推送到远端仓库
```

---

### 1️⃣ 修改文件后查看状态

```bash
git status
```

查看哪些文件被修改（红色的为未暂存的更改）。

---

### 2️⃣ 暂存修改

```bash
git add .
```

意思是把所有修改加入暂存区（也可以针对单个文件加，比如 `git add tools.py`）。

---

### 3️⃣ 提交修改

```bash
git commit -m "fix: corrected function name in tools.py"
```

---

### 4️⃣ （推荐）先更新远端再推送

```bash
git pull origin main --rebase
```

这样能把别人刚 push 的更新同步到你本地，避免冲突。
`--rebase` 选项会让提交历史更整洁。

---

### 5️⃣ 推送到 GitHub

```bash
git push origin main
```

这会把你的最新 commit 推送到远端仓库的 `main` 分支。

---

### 3如果有冲突（merge conflict）

Git 会提示你冲突的文件，比如：

```
CONFLICT (content): Merge conflict in tools_evaluations.py
```

解决方式：

1. 打开冲突文件，手动删除 `<<<<<<<`、`=======`、`>>>>>>>` 这些标记；
2. 保留正确的代码；
3. 再执行：

   ```bash
   git add .
   git rebase --continue
   ```

   或者（如果是普通 merge）：

   ```bash
   git commit
   ```

---

### 4.确认推送成功

执行：

```bash
git log --oneline -5
```
---
如果是非pixi环境（kernel）运行jupytor notebook
<img width="1202" height="160" alt="image" src="https://github.com/user-attachments/assets/119b571a-2d80-4f1f-9f53-4be23f480381" />
例如这里我选择python 3.10.0
不能直接现在用pip Install 去下载例如pandas
可能会装错环境
   ```
Requirement already satisfied: tzdata==2022.1 in
c:\users\刘心怡\appdata\local\programs\python\python38\lib\site-packages
...
Requirement already satisfied: pandas (2023.x)

   ```
pip 把 pandas 装到了这个路径的 Python 里：
但你 notebook 里的 kernel 不是用的这个 Python，而是别的
应该：保证安装 pandas 的 Python”和“运行 notebook 的 Python”是同一个
1.在 notebook 里查清楚“自己现在用的是哪个 Python”
```bash
import sys
print(sys.executable)
print(sys.version)

```
输出的路径就是当前 kernel 用的 Python
2. 终端里对这个Python安装pandas
(注意powershell语法)
```
& "D:\Wizards98\Python\python.exe" -m pip install --upgrade pip
& "D:\Wizards98\Python\python.exe" -m pip install pandas
```
（或者因为路径中没有空格，不用外面的引号）
```
D:\Wizards98\Python\python.exe -m pip install --upgrade pip
D:\Wizards98\Python\python.exe -m pip install pandas
```
再回到notebook
```
import pandas as pd
pd.__version__
```

---
*** numpy
np.array
https://numpy.org/doc/stable/reference/routines.array-creation.html
