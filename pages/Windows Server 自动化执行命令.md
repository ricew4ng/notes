- https://github.com/PowerShell/Win32-OpenSSH/releases
-
  1. 下载最新的 OpenSSH-Win64.zip，解压到 C:/Program FIles/下
-
  2. 执行 powershell.exe -ExecutionPolicy Bypass -File install-sshd.ps1
-
  3. sc.exe config sshd start=auto
-
  4. net start sshd
-
- 然后ansible、fabric一把梭就可以了。