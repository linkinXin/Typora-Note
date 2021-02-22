# PowerShell运行脚本，“因为在此系统上禁止运行脚本”问题

###### ### 个人学习整理，仅供参考

```
PS C:\Users\20678> C:\Users\20678\Desktop\同步Typora笔记.ps1
无法加载文件 C:\Users\20678\Desktop\同步Typora笔记.ps1，因为在此系统上禁止运行脚本。有关详细信息，请参阅 http://go.microsoft.com/fwlink/?LinkID=135170 中的 about_Execution_Policies。
    + CategoryInfo          : SecurityError: (:) []，ParentContainsErrorRecordException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

> ### 解决方案

+ ##### 运行PowerShell管理员模式

  ``` 
  PS C:\Windows\system32> get-ExecutionPolicy
  Restricted
  ```

  **Tip:  Restricted 说明PowerShell 执行策略被禁用了**

+ ##### 执行 set-ExecutionPolicy RemoteSigned

  ```
  PS C:\Windows\system32> set-ExecutionPolicy RemoteSigned
  
  执行策略更改
  执行策略可帮助你防止执行不信任的脚本。更改执行策略可能会产生安全风险，如
  http://go.microsoft.com/fwlink/?LinkID=135170 中的 about_Execution_Policies
  帮助主题所述。是否要更改执行策略?
  [Y] 是(Y)  [A] 全是(A)  [N] 否(N)  [L] 全否(L)  [S] 暂停(S)  [?] 帮助 (默认值为“N”): y
  ```

+ ##### 再次执行 get-ExecutionPolicy

  ```
  PS C:\Windows\system32> get-ExecutionPolicy
  RemoteSigned
  ```

+ ##### 返回RemoteSigned，问题解决