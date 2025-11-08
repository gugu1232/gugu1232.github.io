# 关于pwd和cd

* “Present Working Directory” 指的是你**当前所在的文件夹路径**。
* 当你打开终端（Terminal）时，你其实“站在”某个文件夹里执行命令，这个位置就是你的“当前工作目录”。

📍举例：

```bash
/home/student/projects
```

如果你当前的目录是这样，那么你运行的所有命令（如创建文件、运行程序）默认都会在这个目录下执行。

---

### 💻 2. Use the `pwd` command to display your working directory

**使用 `pwd` 命令显示当前所在目录**

* 含义：告诉你当前所在的位置（Present Working Directory）。

📘 `pwd` 是 “**print working directory**” 的缩写。

---

### 🧭 3. Use `cd` to navigate to different directories

**使用 `cd` 命令在不同目录间切换**

* `cd` 是 “change directory” 的缩写。

* 用法：

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

---

### 📂 4. Use `ls` to list directories

**使用 `ls` 命令列出当前目录下的文件和文件夹**

* 命令：

  ```bash
  ls
  ```

* 输出示例：

  ```
  Desktop  Documents  Downloads  Pictures
  ```

  表示当前目录中有这些子文件夹。

* 常见选项：

  ```bash
  ls -l   # 以详细列表形式显示（包含权限、大小、日期等）
  ls -a   # 显示隐藏文件（以 . 开头的）
  ```

---

### ✅ 总结表

| 命令    | 含义       | 示例输出                  |
| ----- | -------- | --------------------- |
| `pwd` | 显示当前目录路径 | `/home/user/Desktop`  |
| `cd`  | 切换目录     | `cd Documents`        |
| `ls`  | 列出文件/目录  | `file1.txt  folderA/` |



## 🧠 三、理解路径的逻辑（重要概念）

| 类型   | 示例                   | 说明                           |
| ---- | -------------------- | ---------------------------- |
| 绝对路径 | `/home/user/Desktop` | 从根目录 `/` 开始写的完整路径            |
| 相对路径 | `../Downloads`       | 相对当前目录的路径（`..` 表示上一级）        |
| 当前目录 | `.`                  | 代表当前所在目录                     |
| 主目录  | `~`                  | 代表你的 home 目录（如 `/home/user`） |

---

## 📘 四、练习目标总结

| 目标      | 对应命令    |
| ------- | ------- |
| 了解当前路径  | `pwd`   |
| 列出当前内容  | `ls`    |
| 切换到其他目录 | `cd`    |
| 回到上一级   | `cd ..` |
| 回到主目录   | `cd ~`  |






















在使用 **Pixi（或其他项目环境，比如 Python、Node、Git 等）** 时，你常常会看到说明里写类似这样的步骤：

```bash
git clone https://github.com/username/project-name.git
cd project-name
pixi run start
```

这里的 **“clone”** 和 **“navigate”** 是两个关键动作

**Clone（克隆）** 指的是从远程仓库（例如 GitHub）下载一份完整的项目副本到你的电脑上。

命令：

```bash
git clone https://github.com/username/project-name.git
```

意思是：

> 从这个网址下载项目代码，复制到你本地的一个新文件夹 `project-name/` 中。

执行后，你的电脑上会出现一个文件夹，比如：

```
D:\Projects\project-name\
```

**Navigate（导航/切换目录）** 是指进入刚刚克隆下来的项目文件夹。

命令：

```bash
cd project-name
```

意思是：

> 进入你刚刚下载的项目目录。

你可以用 `pwd`（在 PowerShell 或 macOS/Linux 里）查看你现在所在的路径。

---

### ⚙️ 3️⃣ 然后再运行 Pixi 命令

当你在正确的项目目录下时（就是包含 `pixi.toml` 或 `.pixi` 文件的地方），你才能运行：

```bash
pixi run start
```

或者其他命令（比如 `pixi shell`、`pixi install` 等）。

---

### ✅ 总结一下：

| 动作      | 英文命令                   | 含义        |
| ------- | ---------------------- | --------- |
| 克隆项目    | `git clone <repo_url>` | 下载项目到本地   |
| 切换目录    | `cd <folder_name>`     | 进入项目文件夹   |
| 运行 Pixi | `pixi run <command>`   | 在该环境中执行命令 |

---

📌 举个具体例子：

```bash
git clone https://github.com/prefix-dev/pixi-examples.git
cd pixi-examples/getting-started
pixi run python main.py
```

* 第一步：下载 `pixi-examples` 项目。
* 第二步：进入其中的 `getting-started` 文件夹。
* 第三步：在 Pixi 环境下运行 Python 程序。

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


