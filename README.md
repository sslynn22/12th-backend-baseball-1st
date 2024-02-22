<br>

## ✍🏻 추가 느낀점 
예외 테스트가 왜 통과하지 못하는지 잘 모르겠습니다. 
Application을 디버깅해서 "1234" 경우를 넣으면 에러에 걸려서 프로그램 종료가 되는데 테스트는 왜 통과가 안되는지 너무 궁금합니다😭

테스트 먼저 해결하고 클래스를 나누어 코드를 다시 작성하려고 했으나 테스트를 완성하지 못해 클래스 분리는 하지 못하였습니다ㅠㅠ
다음 미션때는 꼭 클래스 분리를 하여 가독성과 유지 보수성을 높이도록 노력하겠습니다!

피드백에서 커밋 단위를 분리하는 연습을 하라고 말씀해주셨는데, 수정할 때마다 또는 기능을 추가할 때마다 커밋을 하는 것을 의미하는 것일까요?
Refactor, Docs같은 태그를 추가하여 의미있는 커밋을 사용하라는 말씀이실까요? 잘 이해가 가지 않아 적어놓습니다!

--
## 지난 느낀점
깃에서 리포지토리를 복사해서 가져오는 것은 처음이라 많이 해맸지만, 서치와 질문을 통해 해결해갔습니다. 깃이 참 멀게 느껴졌는데 이제는 쉽게 사용할 수 있을 것 같아 신기하였습니다. 

어떻게 과제를 해결하면 좋을까 싶어 기능 목록도 자세하게 적어보고, 코드를 간결하게 작성하는 방법에 대해 유튜브 강의도 들어보니 시간이 오래 걸렸지만 앞으로 어떻게 공부하면 되는지 방향성을 잡을 수 있어 보람찬 시간이었습니다. 그동안 코딩하면서 제가 어떤 부분이 부족하였는 지를 깨닫게 되었고 다음 과제에서도 어떤 점을 제가 깨달을까 기대되었습니다. 

다른 사람들의 코드를 볼 때 여러 조건문이 중첩되어 있으면 알아보기 힘든 점이 생각나, 최대한 간결하게 작성해보고자 노력하였습니다. 그래서 프로그래밍 요구사항중 인덴트 깊이를 지키는 것에 많이 고민했습니다. 

--
# 미션 - 숫자 야구 게임
기본적으로 1부터 9까지 서로 다른 수로 이루어진 3자리의 수를 맞추는 게임이다.

## 🚀 기능 목록
- 1~9 사이의 겹치지 않는 랜덤 숫자 3개를 생성한다.
- 사용자로부터 3자리 숫자를 받는다.
- 오류를 감지한다.
  - 중복되는 숫자가 있는 경우
  - 3자리 숫자가 아닌 경우
  - 1~9 범위가 아닌 경우
- 입력받은 수로부터 랜덤 숫자와의 비교를 통해 볼, 스트라이크를 알아낸다.
- 볼, 스트라이크, 낫싱의 경우를 결정한다.
  - 볼만 출력 : 스트라이크=0, 볼!=0
  - 스트라이크만 출력 : 스트라이크!=0, 볼=0
  - 3스트라이크 출력 : 스트라이크=3
  - 낫싱 출력 : 스트라이크=0, 볼=0
  - 볼, 스트라이크 출력 : 스트라이크!=0, 볼!=0
- 3스트라이크일 경우 게임이 종료된다.
  - 정답 문구 출력
  - 게임 다시하기 기능
      - 1 : 게임을 처음부터 다시한다.
      - 2 : 프로그램을 종료한다.

<br>
--
### ⌨️ 입력

- 3자리의 수
- 게임이 끝난 경우 재시작/종료를 구분하는 1과 2 중 하나의 수

### 🖥 출력

- 입력한 수에 대한 결과를 볼, 스트라이크 개수로 표시

```
1볼 1스트라이크
```

- 하나도 없는 경우

```
낫싱
```

- 3개의 숫자를 모두 맞힐 경우

```
3스트라이크
3개의 숫자를 모두 맞히셨습니다! 게임 종료
```
# 미션 - 숫자 야구 게임
기본적으로 1부터 9까지 서로 다른 수로 이루어진 3자리의 수를 맞추는 게임이다.

- 같은 수가 같은 자리에 있으면 스트라이크, 다른 자리에 있으면 볼, 같은 수가 전혀 없으면 포볼 또는 낫싱이란 힌트를 얻고, 그 힌트를 이용해서 먼저 상대방(컴퓨터)의 수를 맞추면 승리한다.
  - 예) 상대방(컴퓨터)의 수가 425일 때
    - 123을 제시한 경우 : 1스트라이크
    - 456을 제시한 경우 : 1볼 1스트라이크
    - 789를 제시한 경우 : 낫싱
      
### 💻 프로그래밍 실행 결과 예시

```
숫자를 입력해주세요 : 123
1볼 1스트라이크
숫자를 입력해주세요 : 145
1볼 
숫자를 입력해주세요 : 671
2볼 
숫자를 입력해주세요 : 216
1스트라이크 
숫자를 입력해주세요 : 713
3스트라이크 
3개의 숫자를 모두 맞히셨습니다! 게임 종료
게임을 새로 시작하려면 1, 종료하려면 2를 입력하세요.
1
숫자를 입력해주세요 : 123
1볼
… 
```

<br>


---

## 📝 License

This project is [MIT](https://github.com/woowacourse/java-baseball-precourse/blob/master/LICENSE) licensed.
