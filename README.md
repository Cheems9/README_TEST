# 리눅스 명령어(top, ps, jobs, kill)

## top 명령어
top 명령어는 리눅스 시스템의 cpu사용량, 메모리 사용량 등을 보여주는 명령어이다.

command 창에 다음 명령어를 치면 사용할 수 있다.
```
top
```


![top_command0](images/top/top_command0.png)
앞으로 첨부 사진들은 도커에서 실행한 우분투이다.

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
  - R: Running
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


## 그외 다른 명령어들
|명령어||
|--       |--|
|1        |cpu 코어별 사용 현황|
|m        |메모리 사용률 시각화|
|shift + p|cpu 사용률순으로 표시|
|shift + m|메모리 사용률순으로 표시|
|shift + t|Running time순으로 표시|


### 참조 블로그
https://code-lab1.tistory.com/332

https://velog.io/@ljk0509/EC2-top-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0

https://velog.io/@ljk0509/EC2-top-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0

https://blog.naver.com/hongganz/222456616664


## ps 명령어
ps 명령어는 현재 실행중인 프로세스와 상태를 표시하는 명령어이다.

command 창에 다음 명령어를 치면 사용할 수 있다.
```
top
```
![스크린샷 2024-06-01 125037](https://github.com/Cheems9/README_TEST/assets/170844889/06bb3408-5406-4280-8f26-7f98fa57ad19)

### 출력정보
|||
|--|--|
|USER (BSD), UID (System V)| 프로세스 소유자의 이름|
|PID                       | 프로세스의 식별 번호|
|PPID                      | 부모 프로세스의 PID|
|%CPU                      |CPU 사용 비율의 추정치 (BSD)|
|%MEM                      |Memory 사용 비율의 추정치(BSD)|
|VSZ                       | K 단위 또는 페이지 단위의 가상 메모리 사용량|
|RSS                       |실제 메모리 사용량|
|TTY                       |프로세스와 연결된 터미널|
|S                         | (System V)|
|STAT (BSD)                |현재 프로세스의 상태 코드|
|TIME                      | 총 CPU 사용 시간|
|COMMAND                   |프로세스의 실행 명령행|
|STIME                     |프로세스가 시작된 시간 혹은 날짜|
|C (System V), CP (BSD)    |짧은 기간 동안의 CPU 사용률|
|F                         | 플래그|
|PRI                       |실제 실행 우선순위|
|NI                        |nice 우선순위 번호|

### ps명령어 옵션
|옵션||
|--|--|
|-A |모든 프로세스를 출력|
|a(BSD)| 터미널과 연관된 프로세스를 출력, x 옵션과 같이 사용하여 모든 프로세스를 출력할 때 사용|
|-a |세션 리더를 제외하고 데몬 프로세스처럼 터미널에 종속되지 않은 모든 프로세스를 출력|
|-e |커널 프로세스를 제외한 모든 프로세스를 출력|
|-f |출력을 풀 포맷으로 표기 (유닉스 스타일) UID, PID , PPID 등이 함께 표시|
|-l (System V), l (BSD) |출력을 긴 포맷으로 표기 프로세스의 정보를 길게 보여주는 옵션으로 우선순위와 관련된 PRI 값과 NI 값을 확인|
|-o | 출력 포맷을 지정|
|-M |64비트 프로세스들을 출력|
|-m |프로세스뿐만 아니라 커널 스레드도 출력|
|-p |특정 PID를 지정하여 출력|
|-r |현재 실행 중인 프로세스 출력|
|u (BSD) |프로세스의 소유자를 기준으로 출력|
|-u [사용자] |특정 사용자의 프로세스 정보를 출력, 사용자를 지정하지 않는다면 현재 사용자 기준으로 출력|
|x (BSD) |데몬 프로세스처럼 터미널에 종속되지 않은 프로세스를 출력|
|-x| 로그인 상태에 있는 동안 아직 완료되지 않은 프로세스를 출력. <br> *유닉스 시스템은 사용자가 로그아웃한 뒤에도 임의의 프로세서가 계속 동작 가능 -> 해당 프로세서는 자신이 실행시킨 쉘이 없어도 계속 자신의 일을 수행하는 데 이 프로세스는 해당 옵션 없이는 확인이 불가능|

### 사용예시
```
top -ef
```
커널 제외한 모든 프로세스를 풀포멧으로 출력한다.
![스크린샷 2024-06-01 132217](https://github.com/Cheems9/README_TEST/assets/170844889/b2978036-b4f7-4e0f-a8c3-3068a1cbecc1)

```
top aux
```
![스크린샷 2024-06-01 132535](https://github.com/Cheems9/README_TEST/assets/170844889/74f3cfe8-0424-4a7a-9daf-0f2f44c06f2d)

### 참조 블로그
https://co-no.tistory.com/entry/Linux-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4-%EB%AA%A8%EB%8B%88%ED%84%B0%EB%A7%81%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%9C%A0%EC%9A%A9%ED%95%9C-ps-%EB%AA%85%EB%A0%B9-%EC%98%88%EC%A0%9C

https://blog.naver.com/tmk0429/222318530824

## jobs 명령어
jobs 명령어는 백그라운드로 실행 중인 프로세스나 중지된 프로세스의 목록을 출력해주는 명령어이다.
```
top jobs [옵션][jobs ID]
```
도커에서 실행한 우분투(진짜 도커 컨테이너에 우분투만 올리고 아무것도 안했다.)에서는 <br>백그라운드 프로세스가 없는것인지 아무것도 뜨지 않는다.
![스크린샷 2024-06-01 140026](https://github.com/Cheems9/README_TEST/assets/170844889/559dac87-1c5a-40f4-95ae-2b72def6105d)

### jobs 명령어 옵션
|옵션||
|--|--|
| -ㅣ | 프로세스 그룹 ID를 state 필드 앞에 출력|
|-n|프로세스 그룹 중 대표 프로세스 ID를 출력|
|-p|각 프로세스 ID에 한 행씩 출력|
### 참조 블로그
https://shaeod.tistory.com/968

## kill 명령어 
kill 명령어는 프로세스를 종료할때 주요 사용되는 명령어이다.
```
kill [옵션][PID]
```

### kill 명령어 옵션
|옵션||
|--|--|
|-9|강제 종료 옵션|
|-ㅣ|신호(Signal)로 사용할 수 있는 신호들을 출력|

### 예시

```
kill -l
```
![스크린샷 2024-06-01 141630](https://github.com/Cheems9/README_TEST/assets/170844889/8a318566-9b65-4f91-bb96-e1cbe7be195d)

