# 리눅스 명령어

## top 명령어
top 명령어는 리눅스 시스템의 cpu사용량, 메모리 사용량 등을 보여주는 명령어이다.

command 창에 다음 명령어를 치면 사용할 수 있다.
```
top
```


![top_command0](images/top/top_command0.png)

### 간단 정보
![스크린샷 2024-05-26 160419](https://github.com/Cheems9/README_TEST/assets/170844889/5b27f2fd-8166-422b-add4-24dd3d796695)
1. top: 현재 업타임을 표시한다. displays uptime information
2. Tasks: 프로세스 상태 정보를 표시한다. displays process status information
3. %Cpu(s): 프로세스가 사용하는 cpu리소스를 표시한다. displays various processor values
   - us: 사용자 레벨의 CPU 사용률
   - sy: 시스템 레벨의 CPU 사용률
   - ni: 프로세스의 우선순위 설정에 사용하는 CPU 사용률
   - id: 유휴 상태의 CPU 사용 비중
   - wa: I/O를 대기 중인 cpu 사용률
   - hi: 하드웨어 인터럽트에 사용되는 CPU 사용률
   - si: 소프트웨어 인터럽트에 사용되는 CPU 사용률
   - st: CPU를 VM에서 사용하여 대기하는 CPU 비율
4. MiB Mem: 물리 메모리 사용률을 보여준다. displays physical memory utilization
5. MiB Swap: 가상 메모리 사용률을 보여준다. displays virtual memory utilization

### 세부 정보
![스크린샷 2024-05-26 160428](https://github.com/Cheems9/README_TEST/assets/170844889/79f1d4b3-1e64-4d54-a7b6-3f9ebf455660)
- PID: 프로세스 ID
- USER: 프로세스를 시작한 유효한 사용자의  ID
- PR: Scheduling Prority, 즉 작업의 우선순위
- NI: 우선순위에 영향을 주는 값으로 음수이면 우선순위가 높고 양수라면 낮음
- VIRT: 가상메모리(Virtual Memory) 크기, 프로세스가 사용하고 있는 가상메모리 용량
- RES: 상주메모리(Resident Memory)  크기, 프로세스가 실제로 사용하고 있는 물리 메모리 용량
- SHR: 공유메모리(Shared Memory) 크기, 다른 프로세스와 공유하고 있는 공유 메모리 용량
- S: 프로세스의 상태
  - R: Runnung
  - S: Sleeping
  - I: Idle
  - D: Uninterruptable Sleep
  - T: 작업 제어 신호에 의해 중지됨
  - t: Trace 중 디버거에 의해 중지됨
  - Z: Zombie
- %CPU: CPU 사용량. 
- %MEM: 메모리 사용량. 현재 사용한 실제 메모리 양
- TIME+: 프로세스가 사용한 CPU 시간. 작업이 시작된 이후 사용한 총 CPU 시간
- COMMAND: 명령어 이름. 작업을 시작할 때 사용되는 명령어 라인 혹은 프로그램의 이름을 표시



### 참조 블로그들
https://code-lab1.tistory.com/332

https://velog.io/@ljk0509/EC2-top-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0

https://velog.io/@ljk0509/EC2-top-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0



## ps 명령어
1. Only foreground applications are allowed to be used.
2. Debugging can be enabled via adb command.

## jobs 명령어

## kill 명령어
