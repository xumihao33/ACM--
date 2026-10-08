# ACM 学习路线与环境配置指南

更新日期：2026-10-08  
适用情况：有较好的 C 语言基础，尚未系统学习 C++；持有 AcWing 网课内容和《C++ Primer Plus：中文版（第六版）》，没有配套习题资料。  
默认投入：每天约 3 小时，每周学习 6 天；时间减半时，可以把学习周期相应延长。

## 1. 总体路线

**先用 7–10 天掌握竞赛常用的 C++，随后以算法学习和刷题为主。不要把读完整本 C++ 教材作为开始刷题的前提。**

推荐学习流程：

> AcWing 视频学习算法 →《C++ Primer Plus》补充语言知识 → 公开题库完成练习 → 限时训练检验 → GitHub 保存代码和复盘。

各项资料和工具的分工：

| 资料或工具 | 用途 |
| --- | --- |
| AcWing 网课内容 | 学习算法思路、证明、复杂度和实现 |
| 《C++ Primer Plus》第六版 | 查阅不理解的 C++ 语法和标准库知识 |
| 洛谷等公开题库 | 获取题目、提交代码、获得评测结果 |
| VS Code + G++ + GDB | 本地编写、编译、运行、调试 |
| Git + GitHub | 管理代码版本，保存学习笔记和复盘 |

网盘中的课程内容不代表拥有 AcWing 官网课程和配套题目的访问权限。遇到需要课程权限的练习，可以换公开题目训练同一个知识点。开始学习不需要再购买一套习题。

本文尚未依据你的实际网课章节逐节匹配，下面按知识点安排。若视频章节顺序不同，以知识依赖和掌握情况为准。

## 2. 第一轮：16 周基础训练

以下是建议节奏，不是获奖时间表。未达到阶段验收要求时，可以延长一周，不必为了赶进度跳过薄弱知识。

| 时间 | 核心内容 | 阶段验收 |
| --- | --- | --- |
| 第 1–2 周 | C++ 常用语法、STL、复杂度基础 | 能独立使用容器、排序和查找完成简单题 |
| 第 3–4 周 | 排序、二分、前缀和、差分、双指针、离散化、区间合并 | 能解释算法适用条件、边界及复杂度 |
| 第 5–6 周 | 栈、队列、单调栈、单调队列、堆、并查集、哈希、Trie | 会使用 STL，理解常用结构的核心实现 |
| 第 7–9 周 | DFS、BFS、回溯、图的存储、拓扑排序、最短路、最小生成树 | 能根据图的条件选择算法，理解正确性 |
| 第 10–12 周 | 贪心、背包、线性 DP、区间 DP、简单树形 DP | 编码前能说清状态、转移、初始化和遍历顺序 |
| 第 13–14 周 | 最大公约数、质数、筛法、快速幂、模运算、基础组合计数 | 能正确处理整数范围、乘法溢出及取模 |
| 第 15–16 周 | 混合题、限时训练、补题、薄弱专题复习 | 不看算法标签也能独立选择解法 |

练习量可以从每周 10–15 道开始，难题增多后适当减少。能讲清思路、独立实现、隔几天还能重做，比题量更重要。

从第 3 周开始，每周进行一次 90–120 分钟的限时练习，先用已经学过的内容组题。基础齐全后增加整场模拟。如果目标是 ICPC/CCPC，逐步加入队内读题、分工、沟通和共用一台电脑的训练。

第一轮完成后，再根据比赛和补题暴露的问题学习树状数组、线段树、LCA、字符串算法和进阶 DP 等内容。

## 3. 前 7–10 天：从 C 过渡到竞赛 C++

| 时间 | 学习内容 | 动手任务 |
| --- | --- | --- |
| 第 1 天 | 编译运行、`cin/cout`、命名空间、`long long` | 将 3 道熟悉的 C 语言题改写为 C++ |
| 第 2 天 | `string`、`vector`、引用、`const` | 字符串处理和数组统计 |
| 第 3 天 | `sort`、`pair`、结构体、比较函数 | 多关键字排序 |
| 第 4 天 | 迭代器、范围 `for`、`auto`、简单 lambda | 容器遍历、排序和去重 |
| 第 5 天 | `stack`、`queue`、`deque`、`priority_queue` | 括号匹配、队列模拟、取最值 |
| 第 6 天 | `set`、`map`、`unordered_map` | 去重和频次统计 |
| 第 7 天 | `lower_bound`、`upper_bound`、常用操作复杂度 | 有序数组查找和一次小测 |
| 第 8–10 天 | 查漏补缺、综合练习 | 独立完成若干简单题，不依赖模板照抄 |

优先掌握这些容易出错的细节：

- `vector` 的合法下标范围是 `0` 到 `size() - 1`；空容器不能直接访问元素。
- `vector` 扩容可能使已有的迭代器、指针和引用失效。
- `sort` 比较函数应满足严格弱序，不能把常规升序比较写成 `a <= b`。
- 在通常的有序数组用法中，先排序，再使用 `lower_bound` 或 `upper_bound`。
- 使用 `1LL * a * b` 让乘法按 `long long` 进行，仍需保证结果不超过其范围。
- 理解 `const vector<int>&` 如何避免复制并限制通过该引用修改容器。
- `priority_queue<int>` 默认是大根堆。
- 学会从数据范围估计复杂度，不要只判断样例能否通过。

继承、多态、复杂模板和智能指针的深入机制可以后学。先理解基本的类、对象、成员函数，就可以开始使用 STL。

## 4. 《C++ Primer Plus》怎么读

第六版包含 C++11 内容。建议本地练习统一使用 C++17，参赛时按评测平台支持的标准选择。书中章节安排可参考[出版社目录](https://www.informit.com/store/c-plus-plus-primer-plus-9780132781152)。

| 章节 | 建议读法 |
| --- | --- |
| 第 2–7 章 | 快速浏览，重点找与 C 不同的部分，熟悉的循环和数组无需反复学 |
| 第 8 章 | 重点读引用、函数重载、函数模板基础 |
| 第 9 章 | 掌握作用域、存储期和命名空间 |
| 第 10–11 章 | 理解类、成员函数、构造函数和简单运算符重载 |
| 第 16 章 | 提前读，重点掌握字符串、容器、迭代器和算法 |
| 第 17 章 | 按需查阅输入输出 |
| 第 18 章 | 选读 `auto`、范围循环、lambda 等实用内容 |

无需先补完中间所有章节才读 STL。遇到必要的前置概念，再回到对应章节补充。

## 5. 没有配套习题，如何练习

### 5.1 第一组公开题目

先使用洛谷作为主要练习平台。下面题目链接已在整理本指南时核对；提交代码通常需要登录账户。

| 顺序 | 题目 | 建议训练内容 |
| --- | --- | --- |
| 1 | [P1001 A+B Problem](https://www.luogu.com.cn/problem/P1001) | 熟悉 C++ 编写、编译、提交和评测流程 |
| 2 | [P1046 陶陶摘苹果](https://www.luogu.com.cn/problem/P1046) | 输入、循环、判断 |
| 3 | [P1914 小书童——凯撒密码](https://www.luogu.com.cn/problem/P1914) | `string`、字符遍历、取模 |
| 4 | [P1059 明明的随机数](https://www.luogu.com.cn/problem/P1059) | 分别尝试 `vector + sort` 和 `set` 完成排序去重 |
| 5 | [P1093 奖学金](https://www.luogu.com.cn/problem/P1093) | 结构体、排序、多关键字比较 |
| 6 | [P2249 查找](https://www.luogu.com.cn/problem/P2249) | 学过二分后做，分别尝试手写二分和 `lower_bound` |

前两题用来检查工具流程。你已有 C 基础，不必长期停留在这一难度；从第三题起，有意识地使用新学的 C++ 功能。表中的方法是训练建议，题目本身不限制必须使用这些方法。

完成后，可以用 [AtCoder Beginners Selection](https://atcoder.jp/contests/abs/tasks) 补充基础实现训练，并逐渐适应英文题面。

### 5.2 每个视频知识点对应一个练习闭环

1. 看讲解，记录算法解决什么问题、适用条件和复杂度。
2. 关闭视频，自己实现核心算法，手动检查一个小例子。
3. 做一道直接应用题，确认能完整实现。
4. 再做两三道变式题，训练识别条件和边界。
5. 隔天重做看过题解的题，一周后再抽查。

卡住 30–45 分钟且没有新进展时，可以看一小段提示。看过完整题解后通过的题，应标为“待独立重做”，不要直接视作掌握。

### 5.3 每天和每周怎么安排

每天 3 小时的参考分配：

| 环节 | 时间 |
| --- | --- |
| 视频或教材学习 | 40 分钟 |
| 独立做题 | 100 分钟 |
| 补题与复盘 | 30 分钟 |
| 整理代码和 Git 提交 | 10 分钟 |

每周用一次限时练习替换当天普通训练，再安排一次集中补题。根据错误原因决定下周重点：不会建模就练分析，知道算法但写不对就练实现，总是超时就重新分析复杂度。

建议每题只记录以下内容：

```text
题目链接：
核心思路：
正确性依据：
时间 / 空间复杂度：
本次错误与反例：
是否独立完成：
下次重做日期：
```

## 6. Windows + VS Code 配置

### 6.1 你的环境检查记录

下表来自 2026-10-07 的本机检查，后续若有安装或更新，以实际环境为准。

| 项目 | 检查结果 |
| --- | --- |
| VS Code | 已安装，命令入口位于 `D:\program\Microsoft VS Code\bin` |
| G++ | 已安装，版本 15.2.0，位于 `D:\MSYS2\ucrt64\bin\g++.exe` |
| Git | 已安装，版本 2.53.0.windows.2 |
| GDB | 当时 PATH 中未找到，`D:\MSYS2\ucrt64\bin\gdb.exe` 也不存在 |
| 已有插件 | C/C++、Error Lens、Git Graph、中文包、Code Runner 等 |

因此优先沿用已有环境，补齐 GDB。下面是操作指南，不表示这些安装、配置和上传已经代你执行。

### 6.2 安装 GDB

从开始菜单打开 **MSYS2 UCRT64** 终端，执行更新：

```bash
pacman -Syu
```

如果提示关闭终端，按提示关闭并重新打开，再执行一次更新。更新完成后安装调试器：

```bash
pacman -S --needed mingw-w64-ucrt-x86_64-gdb
```

`pacman` 命令在 MSYS2 终端中执行。更新过程参考 [MSYS2 官方说明](https://www.msys2.org/docs/updating/)。

你的 G++ 已经能从 PATH 找到，通常无需重新配置。如果新终端无法识别工具，检查 Windows 用户环境变量 `Path` 是否包含：

```text
D:\MSYS2\ucrt64\bin
```

若以后在新电脑上从零安装，可以从 [MSYS2 官网](https://www.msys2.org/) 安装，再在完成更新后安装完整工具链：

```bash
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

完全关闭并重新打开 VS Code，在 PowerShell 终端验证：

```powershell
g++ --version
gdb --version
git --version
```

三条命令都应输出版本。C/C++ 插件本身不包含编译器，G++ 负责实际编译。[官方 Windows GCC 配置指南](https://code.visualstudio.com/docs/cpp/config-mingw)

### 6.3 打开整个学习目录

在 PowerShell 执行：

```powershell
Set-Location 'C:\Users\Xu\Desktop\ACM之路'
code .
```

建议目录结构：

```text
ACM之路/
├── .vscode/
│   ├── tasks.json
│   ├── launch.json
│   └── c_cpp_properties.json
├── cpp-basics/
├── luogu/
├── atcoder/
├── contests/
├── templates/
├── notes/
├── .gitignore
└── README.md
```

每道题单独一个 `.cpp` 文件，例如 `luogu/P1059.cpp`。每个文件有自己的 `main()`，编译时只编译当前题目。

### 6.4 编译配置：`.vscode/tasks.json`

在项目根目录创建 `.vscode` 文件夹，再创建下面三个文件。路径按你现有的 `D:/MSYS2` 编写；更换电脑后需同步修改。

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "build-current-cpp",
      "type": "process",
      "command": "D:/MSYS2/ucrt64/bin/g++.exe",
      "args": [
        "-std=c++17",
        "-g",
        "-O0",
        "-Wall",
        "-Wextra",
        "${file}",
        "-o",
        "${fileDirname}/${fileBasenameNoExtension}.exe"
      ],
      "options": {
        "cwd": "${fileDirname}"
      },
      "problemMatcher": ["$gcc"],
      "group": {
        "kind": "build",
        "isDefault": true
      }
    }
  ]
}
```

`-g -O0` 便于调试，`-Wall -Wextra` 打开常用警告。需要观察优化后的运行速度时，可另外用 `-O2` 编译；本地速度不能完全代表评测机速度。

### 6.5 调试配置：`.vscode/launch.json`

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug current C++",
      "type": "cppdbg",
      "request": "launch",
      "program": "${fileDirname}/${fileBasenameNoExtension}.exe",
      "args": [],
      "stopAtEntry": false,
      "cwd": "${fileDirname}",
      "environment": [],
      "externalConsole": false,
      "MIMode": "gdb",
      "miDebuggerPath": "D:/MSYS2/ucrt64/bin/gdb.exe",
      "preLaunchTask": "build-current-cpp",
      "setupCommands": [
        {
          "description": "Enable pretty printing",
          "text": "-enable-pretty-printing",
          "ignoreFailures": true
        }
      ]
    }
  ]
}
```

启动调试会先执行编译任务。程序输入放在运行时打开的终端里；`miDebuggerPath` 必须指向实际安装好的 GDB。[调试配置说明](https://code.visualstudio.com/docs/cpp/launch-json-reference)

### 6.6 代码提示配置：`.vscode/c_cpp_properties.json`

```json
{
  "version": 4,
  "configurations": [
    {
      "name": "Windows GCC",
      "compilerPath": "D:/MSYS2/ucrt64/bin/g++.exe",
      "intelliSenseMode": "windows-gcc-x64",
      "cppStandard": "c++17",
      "cStandard": "c17"
    }
  ]
}
```

这里的标准设置控制代码分析；实际编译标准由 `tasks.json` 中的 `-std=c++17` 决定，两者应保持一致。[C/C++ 配置说明](https://code.visualstudio.com/docs/cpp/customize-cpp-settings)

### 6.7 验证编译、输入和断点

新建 `main.cpp`：

```cpp
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int n;
    if (!(cin >> n)) return 0;

    vector<int> a(n);
    for (int& x : a) cin >> x;

    sort(a.begin(), a.end());

    for (int x : a) cout << x << ' ';
    cout << '\n';
    return 0;
}
```

操作步骤：

1. 保存文件，保持 `main.cpp` 为当前编辑页。
2. 按 `Ctrl + Shift + B` 编译。
3. 在 `sort` 那一行左侧点击，设置断点。
4. 按 `F5`，如提示选择配置，选择 `Debug current C++`。
5. 在终端输入下面的数据，确认程序停在断点处。
6. 按 `F10` 单步执行，再按 `F5` 继续运行。

输入：

```text
5
3 1 5 2 4
```

预期输出：

```text
1 2 3 4 5
```

也可以先手动编译，理解“源代码 → 可执行文件 → 运行”的过程：

```powershell
g++ -std=c++17 -Wall -Wextra -g -O0 main.cpp -o main.exe
```

确认编译成功后再运行：

```powershell
.\main.exe
```

使用示例中的 `ios::sync_with_stdio(false)` 后，同一道题内统一使用 `cin/cout`，避免与 `scanf/printf` 混用。提交题目时不要输出“请输入数字”等额外提示。

### 6.8 常见问题

| 现象 | 优先检查 |
| --- | --- |
| 找不到 `g++` 或 `gdb` | 是否安装、PATH 是否正确、VS Code 是否完全重启 |
| `miDebuggerPath` 无效 | `D:/MSYS2/ucrt64/bin/gdb.exe` 是否存在 |
| 能编译，但标准库头文件标红 | `compilerPath` 是否与实际 G++ 一致 |
| 按 F5 编译了 JSON 文件 | 切回需要运行的 `.cpp` 文件再启动 |
| 输入不了数字 | 在程序终端输入，不要在输出面板或调试控制台输入 |
| 提示多个 `main` | 只编译当前题目，不要把所有题目一起链接 |
| 无法覆盖 `.exe` | 停止上一次仍在运行或调试的程序后再编译 |

## 7. 推荐的 VS Code 插件

先用好已有插件，再按需要添加。基础 Git 操作和 Markdown 预览已经内置，不必为了开始学习安装很多扩展。

| 插件 | 当前情况 | 用途 |
| --- | --- | --- |
| [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) | 已安装 | 代码补全、跳转、诊断、调试 |
| [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) | 已安装 | 在代码行旁显示诊断信息 |
| [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph) | 已安装 | 查看提交历史和改动 |
| [Competitive Programming Helper](https://marketplace.visualstudio.com/items?itemName=DivyanshuAgrawal.competitive-programming-helper) | 推荐新增 | 保存输入输出样例，批量运行测试 |
| [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) | 按需新增 | 编辑题解、笔记和 README |

可以在 VS Code 扩展面板搜索安装，也可以在终端执行：

```powershell
code --install-extension DivyanshuAgrawal.competitive-programming-helper
code --install-extension yzhang.markdown-all-in-one
```

CPH 可以手动添加测试，也能配合浏览器扩展 Competitive Companion 导入其支持网站的题目。先跑通普通编译和调试，再将 CPH 的 C++ 编译器设为 `D:/MSYS2/ucrt64/bin/g++.exe`，编译参数设为 `-std=c++17 -O2 -Wall -Wextra`。CPH 有自己的编译设置，不会自动复用上述构建任务。[CPH 使用说明](https://marketplace.visualstudio.com/items?itemName=DivyanshuAgrawal.competitive-programming-helper)

已有的 Code Runner 可以保留，前期统一使用构建任务和 F5。单文件刷题暂时不需要 CMake。独立练习时先自己分析和实现，再用辅助工具解释错误，避免用生成答案代替训练。

## 8. GitHub 仓库配置与日常流程

### 8.1 先准备文件

在项目根目录创建 `.gitignore`：

```gitignore
*.exe
*.o
*.obj
*.out
*.pdb
build/
```

编译产物不需要上传。`.vscode` 配置可以提交，方便恢复环境；其中的本机编译器路径换电脑后需要调整。

`README.md` 写学习目标、当前进度、目录说明和环境配置。网课原始资料单独保存，仓库主要放自己的源代码和笔记。

### 8.2 新建空仓库的情况

1. 在 GitHub 新建仓库，例如 `acm-training`。
2. 自行选择公开或私有。
3. 创建时不要勾选自动生成 README、`.gitignore` 和 License，本地将进行初始化。
4. 在学习目录的 PowerShell 终端逐行执行以下命令。先替换姓名、邮箱、用户名和仓库名；每步成功后再继续。

```powershell
git init -b main
git config user.name "你的名字"
git config user.email "你的GitHub邮箱"
git add .
git diff --cached --stat
git commit -m "Initialize ACM training repository"
git remote add origin https://github.com/你的用户名/acm-training.git
git push -u origin main
```

`git diff --cached --stat` 用来检查准备提交哪些文件。这里的姓名和邮箱配置只影响当前仓库；可以使用 GitHub 账户设置提供的隐私邮箱。[GitHub 官方上传流程](https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github)

Git 的姓名和邮箱不是登录认证。首次推送时，如果 Git for Windows 配置了 Git Credential Manager，按浏览器提示登录；若未出现登录流程，可按官方说明检查凭据管理器。[GitHub 身份验证说明](https://docs.github.com/en/get-started/git-basics/caching-your-github-credentials-in-git)

### 8.3 GitHub 仓库已经有文件的情况

优先克隆已有仓库，再在克隆后的目录中整理资料和写代码，跳过上一节的新仓库初始化流程：

```powershell
git clone https://github.com/你的用户名/你的仓库名.git
```

用 VS Code 打开克隆生成的文件夹，将自己的代码和笔记复制进去。不要通过强制推送处理第一次连接时的历史冲突。

### 8.4 每天学习后的提交

在仓库根目录执行：

```powershell
git status
git add .
git diff --cached --stat
git commit -m "Practice binary search and record boundary mistakes"
git push
```

没有改动时无需提交。如果你在另一台电脑或 GitHub 网页修改过文件，开始当天工作前先检查本地状态，在工作区干净时运行 `git pull --ff-only`；若出现冲突或分支分叉提示，先查看原因。

理解命令后，也可以通过 VS Code 的“源代码管理”进行暂存、提交和推送。[VS Code GitHub 使用说明](https://code.visualstudio.com/docs/sourcecontrol/github)

**题目网站负责评测答案，GitHub 负责保存学习记录。只把代码上传到 GitHub，不代表题目已经通过。**

## 9. 第一周执行清单

- [ ] 补齐 GDB，确认 `g++`、`gdb`、`git` 都能输出版本。
- [ ] 在 VS Code 中完成编译、运行、输入和一次断点调试。
- [ ] 注册或登录题库账户，通过 P1001，熟悉提交流程。
- [ ] 学习 `string`、`vector`、引用、`sort` 和比较函数。
- [ ] 完成第一组公开题目中与已学知识对应的题。
- [ ] 建立 GitHub 仓库，完成首次提交和推送。
- [ ] 为至少一道出错的题写下反例和原因。
- [ ] 不看题解，重做一道之前需要提示的题。

今天先完成四件事：**补齐 GDB、跑通排序程序并打断点、完成首次 GitHub 推送、用 C++ 独立做 3 道熟悉的简单题。**
