## 프로젝트 생성
**사전준비물**
- Java 11 설치
- IDE: InteliJ

### 스프링 부트 스타터 사이트로 이동해서 스프링 프로젝트 생성
https://start.spring.io/

- 프로젝트 선택
  - Project: Gradle Project
  - Spring Boot: 2.7.2 (강의에서는 2.3.3 버전, M 버전과 snapshot 버전은 정식 릴리즈 버전이 아니다.)
  - Language: Java
  - Packaging: Jar
  - Java: 11
- Project Metadata
  - groupId: hello
  - artifactId: core
- Dependencies: 선택하지 않는다.
- 그 후 generate

### 오류 발생
```
Unable to find method 'org.gradle.api.artifacts.result.ComponentSelectionReason.getDescription()Ljava/lang/String;'.
Possible causes for this unexpected error include:
Gradle's dependency cache may be corrupt (this sometimes occurs after a network connection timeout.)
Re-download dependencies and sync project (requires network)

The state of a Gradle build process (daemon) may be corrupt. Stopping all Gradle daemons may solve this problem.
Stop Gradle build processes (requires restart)

Your project may be using a third-party plugin which is not compatible with the other plugins in the project or the version of Gradle requested by the project.

In the case of corrupt Gradle processes, you can also try closing the IDE and then killing all Java processes.
```
1. 첫번째 해결
- https://www.google.com/search?q=intellij+android+sdk+download&oq=intellij+andr&aqs=chrome.4.0i512j0i20i263i512j69i57j0i512l7.17127j1j4&sourceid=chrome&ie=UTF-8

2. 두 번째 해결 과정
- 구글에 Unable to find method 'org.gradle.api.artifacts.result.ComponentSelectionReason.getDescription()Ljava/lang/String;'. 검색
- https://twinparadox.tistory.com/624
- 그래들 버전 문제일 가능성이 있어서 위 게시물을 보고 6.8.3 버전으로 변경해주었다.
- 아래와 같이 오류가 변경되었다.
```
Deprecated Gradle features were used in this build, making it incompatible with Gradle 7.0.
Use '--warning-mode all' to show the individual deprecation warnings.
See https://docs.gradle.org/6.8.3/userguide/command_line_interface.html#sec:command_line_warnings

CONFIGURE SUCCESSFUL in 13s
```

### 스프링 프로젝트 실행방법
**..\src\main\java\hello\core\CoreApplication.java** 에서 run!