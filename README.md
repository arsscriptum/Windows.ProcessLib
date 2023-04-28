# process
Some code related to the process

Description of this library:
This library mainly contains process-related content, such as:
1. Process and environment variables, Job, PEB
2. Threads, TEB, APC, TLS, impersonation/proxy
3. Modules,
4. Service,
5. Schedule tasks,
6. Shut down
7. Memory, heap, stack, file mapping
8. handle, object
9. Token, user, session, etc.

特别注释：文件映射不属于文件，属于内存管理（对象或句柄）的概念范畴。


Several rules for the design of this library:
1. Try not to call the log function.
  When starting out, also consider whether to use logs, and what kind of logs.
2. Because of the previous item, if the code fails, detailed information should be returned, which is the reason for the failure.
3. Because of the above two reasons, the user should check the return value and record the log.
4. The code will not actively throw exceptions. The code shields exceptions as much as possible. But that doesn't mean there are no exceptions in the code.
  The code tries to catch exceptions and return information

5. The exported (exposed) functions are all in NTAPI call format.
6. The code should try to use SAL (source-code annotation language: source code annotation language).
7. The code format is similar to go and python.
8. Try not to use hard coding in the code.
9. The code turns on static syntax checking (enables Microsoft Code Analysis, turns off Clang-Tidy).
10. The level of warning is level 4, and warnings are considered errors.
11. The operation of the code must pass: Driver Verifier/Application Verifier/gflags.exe.
12. Prohibit the use of assertions (it is estimated that there are still many assertions in the code).
13. The parameters of the interface are only basic types and pointers (no classes, templates and references).
14. Only rely on the library of the operating system, no longer rely on third-party libraries, including CRT.
15. All interfaces are C interfaces, namely EXTERN_C.
16. C language standard selection: ISO C17 (2018) standard (/std:c17).
17. C++ language standard choice: ISO C++17 standard (/std:c++17) or: preview - features in the latest C++ working draft (/std:c++latest).

Special Note:
This library only provides c/c++ calling interface documents,
Others, such as: ASM, C#, GO, PYTHON, JAVA, PHP, etc. are defined by themselves.


Notice:
How to call the interface or callback stdcall or cdecl or fastcall。

