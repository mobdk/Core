# Core
Core bypass Windows Defender and execute any binary converted to shellcode. Core is NOT using any mechanism to prevent
AV/EDR from debug/inspect tis code.

Core uses syscall to execute shellcode, any kind of shellcode, in this PoC Mimikatz is converted to shellcode (.exe version)
Core is not calling any API but create memory mapped file and then calls the Nt or Zw functions.

The inner soul of syscalls in 64bit:

```
mov     r10,rcx
mov     eax,0C1h
test    byte ptr [SharedUserData+0x308 (00000000`7ffe0308)],1
jne     ntdll!NtCreateThreadEx+0x15 (00007ffa`8c50e635)
syscall
ret
```
or maybe

```
mov r10, rcx
mov eax, 0xC1
syscall
ret

```

but why this syntax ? it too easy for AV/EDR reg.ex pattern matching engine to detect this, why not make more complex or foolish


```
m
```

