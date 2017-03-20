# F-Secure

- PUS: Potentially Unwanted Software
  - possible of getting false signature
- APT: advance persistent threat
- botnet: bot master + slave (zombie)
- IOC: indicator of compromise
- generic: positive malware but not categorized yet
- some malware is identifiable by office hour

## How do they infect/propagate?
- spam email: commonly for ransomware, to get bitcoin
- exploit kit
- flash drive
- Anti-analysis technique:
  - anti sandbox
  - anti vm
  - isDebuggerPresent
  - GetTickCount: another way to evade vm
  - Sleep

## How we detech them
- generic signature
- behaviour pattern
- YARA

## Tools: Malware Analysis
- static
  - ida pro
- dynamic
  - ollydbg, windbg

## Reverse Engineering
- DWORD = double word
- control transfer instructions
- ebx inside bracket (`[ebx]`) means 
- assembly: 1 line = 1 instruction
