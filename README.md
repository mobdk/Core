# Core
Core bypass Windows Defender and execute any binary converted to shellcode

Core uses syscall to execute shellcode, any kind of shellcode, in this PoC Mimikatz is converted to shellcode (.exe version)
Core is not calling any API but create memory mapped file and then calls the Nt or Zw functions.

The inner soul of syscalls is in 64bit:

