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

