# guide-mas.md

보통 개발자들은 Architecture로 문제를 거시적인 관점에서 풀기를 원한다.
예를 들면, Scale out/up 을 하는 방향으로 생각하지만, 결국 근본적인 원인을 바라보지 않는 경향이 있다.
근본적으로 시스템에 원인이 있을 수 있지만, 대부분은 소포트웨어의 문제는 응용하는 부분에서 발생한다.

예시)
Heap 관리를 못하고 있는 프로그래밍, List의 잘못된 사용, Data area(Method Area) 구분을 못하는 경우

MSA가 힘든 부분

- Context Tracing을 구현해야지 프로그램의 맥락을 찾아다니기 수월하다.
- Server간 순환 호출이 발생할 수 있다.
- convention 불일치(lint, code, test, build, deploy, ...)
- Network Latency 발생
- Atomicity 보장이 어렵다.
