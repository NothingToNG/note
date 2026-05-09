# Github 

## SSH method

### 生成SSH key

Administrator@SuperComputer MINGW64 /d/TongPC/NOTE (main)
$ ssh-keygen -t rsa -b 4096 -C "tong.t.zhang@outlook.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/Administrator.BF-202603312006/.ssh/id_rsa):
Enter passphrase for "/c/Users/Administrator.BF-202603312006/.ssh/id_rsa" (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/Administrator.BF-202603312006/.ssh/id_rsa
Your public key has been saved in /c/Users/Administrator.BF-202603312006/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:DVJdx3344U+37L9oIb8ofXxNCVRpN6OOrQxbSlrMDuM tong.t.zhang@outlook.com
The key's randomart image is:
+---[RSA 4096]----+
|        .. ...o+.|
|       .  .  oo*+|
|      . .   . +.*|
|       . o   o .+|
|        S . + o.=|
|       o * + + +o|
|      . B B = o..|
|       E = +.=.o.|
|          ..ooo.+|
+----[SHA256]-----+

### 查看key的指令$ cat ~/.ssh/id_rsa.pub

### 复制这一段代码

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQCvN9uS2iLxYZXt0qKkLuu28Ani5tJGL36M8/lNgIDOuqn1VvbyWfQUJiL3+7Gv/YB0+IyUamYU5z7vE3EH2wyw3a0ZHTN7dnM0Z5IF0v5VwT5tHOsEBjvrsCcjkwUfdJa4mP0aTCo5ybHIjCWoGvJIZV2g77zZcw4W1uSHu/Th/JLaQIXqI+k8TVP3Yy4uVfWzkwKJIc5PnWfG1UWIHjE7a5DM6zM/J2FRCCv5i6opEy351tDF4oo0ojLHdhSHi9ETX6CTYHMU/t3H16bVtZpY0dz8s2JwOYoU0uNelG0upYIeQfoX2USYB/0DONQ7n9ATg1gGJyMDzQ0rclrk5RO9O2LP7Ny+TFQCVNBk68s7a2gj7L163WPFukSn46kYBngtoDtsHTWXK+MTQMxfuFzpx0hJiVUQslCLQR1LDWH6JEwmiC2n60fw9UXSKpmPeXlI7UrgLCudFt4wmNNsXdPBK4+gXVAbKict8MUd7hVrwGelMAfA5BWpY3y50R48+d0IkQSmFabcKLXoVQxEMpuFnwd5DtZ03rVeB6iLez5KZ7bE8qBpyVzqufxhIBzlk8k0GNkms+WaGXPBnmxWo1zWXg7sJ00DHuPiVGw+EiyXs0aorrI2RhopSb4+S1abwlq2FRWH72uMFvEe7lSgXdFu8THvWea4qBbeqN7+mykzTQ== tong.t.zhang@outlook.com

### **添加到 GitHub**：

- 登录 GitHub → 右上角头像 → **Settings**
- 左侧菜单选择 **SSH and GPG keys**
- 点击 **New SSH key**
- Title 填写：`My Windows PC`
- Key 粘贴刚才复制的公钥
- 点击 **Add SSH key**

### 验证连接

$ ssh -T git@github.com 

Hi NothingToNG! You've successfully authenticated, but GitHub does not provide shell access.

### 尝试push



1.  修改远程仓库地址为 SSH 格式
1. git remote set-url origin git@github.com:NothingToNG/note.git
1. 验证修改结果（应该显示 git@github.com 开头的地址）
1. git remote -v
1. 推送代码
1. git push -u origin main
1. `git push -u origin main`

## 本地commit

### 基本流程

```
# 1. 查看当前文件状态
git status

# 2. 添加文件到暂存区
git add <文件名>        # 添加单个文件
git add .              # 添加所有更改的文件
git add --all          # 添加所有文件（包括删除）

# 3. 提交到本地仓库
git commit -m "提交说明"
```



### commit command

```
# 带提交信息的提交（推荐）
git commit -m "修复了登录bug"

# 跳过暂存区，直接提交已跟踪的文件
git commit -a -m "更新多个文件"

# 修改最后一次提交（信息或漏掉的文件）
git commit --amend -m "新的提交信息"

# 只提交特定文件
git add file1.txt file2.txt
git commit -m "更新了两个配置文件"
```

### 提交规范

```
# 功能开发
git commit -m "feat: 添加用户登录功能"

# 修复bug
git commit -m "fix: 修复支付金额计算错误"

# 文档更新
git commit -m "docs: 更新README安装说明"

# 代码优化
git commit -m "refactor: 优化数据库查询性能"
```

### Branch

#### 基本指令

```markdown
# 查看分支
git branch                 # 查看本地分支（当前分支带 * 号）
git branch -r              # 查看远程分支
git branch -a              # 查看所有分支（本地+远程）

# 创建分支
git branch <分支名>         # 创建新分支（基于当前所在位置）
git branch <分支名> <commit-hash>  # 基于指定提交创建分支

# 切换分支
git checkout <分支名>       # 切换到指定分支
git switch <分支名>         # Git 2.23+ 推荐使用

# 创建并切换分支
git checkout -b <分支名>    # 创建并切换到新分支
git switch -c <分支名>      # Git 2.23+ 推荐使用

# 重命名分支
git branch -m <新分支名>            # 重命名当前分支
git branch -m <旧分支名> <新分支名>  # 重命名指定分支

# 删除分支
git branch -d <分支名>      # 安全删除（已合并的分支）
git branch -D <分支名>      # 强制删除（未合并也删）
```

#### 合并分支

```
# 合并分支
git checkout <目标分支>      # 先切换到要合并到的分支（如 main）
git merge <源分支>          # 将源分支合并到当前分支

# 取消合并（遇到冲突时）
git merge --abort          # 放弃本次合并

# 查看已合并/未合并的分支
git branch --merged        # 查看已合并到当前分支的分支
git branch --no-merged     # 查看未合并到当前分支的分支
```

