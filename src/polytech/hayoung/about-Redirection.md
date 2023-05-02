---
layout: home
---
# Redirection

# 과제 Redirection

## Redirection이란?

<img src ="https://file.notion.so/f/s/52c83eba-a25f-42f8-a51a-eee022254483/img1.daumcdn.png?id=a0b3eab3-6656-4061-b58f-6922526b35eb&table=block&spaceId=f7f5a27f-fb49-4dd8-8a47-1d1cb5901c61&expirationTimestamp=1683078352479&signature=jZxv7auDG0yIZH_P9NZfCPMHLjNpY2zBWJipWnqddXo&downloadName=img1.daumcdn.png">

- stdin 표준 입력
- stdout 표준 출력
- stderr 표준 에러

→ 표준 입력 스트림(stdin)에서 읽어오고 stdout 표준 출력 스트림에 씀

→ 오류가 발생한 경우 stderr, 표준 에러 스트림에 씀

→ 명령의 결과를 모니터로 출력하지 않고 파일로 저장할 수 있는 방법이 없을까?

→ redirection을 사용하여 출력과 입력의 방향을 지정해줌

리다이렉션(Redirection)이란 말 그대로, 방향을 변경하는 것을 의미합니다. 리눅스에선 꼭 키보드로 표준 입력을 받거나 화면으로 표준 출력을 하는 것이아니라, 파일로 표준 입력을 받고, 파일로 표준 출력을 받는 등의 기능을 의미합니다. 리다이렉션을 이용하면 리눅스를 좀 더 자유롭고 편하게 사용할 수 있습니다.

→ 출력과 에러가 너무 길어 파일로 저장하는게 편할 때 사용
### 입출력 리다이렉션


<img src ="https://file.notion.so/f/s/ea1b24ac-21b8-46e5-8373-7cda04a46aa9/%EB%A6%AC%EB%8B%A4%EC%9D%B4%EB%A0%89%EC%85%98.jpg?id=895d5516-0abc-4724-945e-d9233d70aa33&table=block&spaceId=f7f5a27f-fb49-4dd8-8a47-1d1cb5901c61&expirationTimestamp=1683078369293&signature=YF406i8BLPHo8-vwRjZC3U88OyAYQanXc0TcnQgWw7o&downloadName=%EB%A6%AC%EB%8B%A4%EC%9D%B4%EB%A0%89%EC%85%98.jpg">

| 리다이렉션 기호 | 방향 | 의미 |
| --- | --- | --- |
| > | 표준 출력 | 명령 > 파일 : 명령의 결과를 파일로 저장 |
| >> | 표준 출력(추가) | 명령 >> 파일 : 명령의 결과를 기존 파일 데이터에 추가 |
| < | 표준 입력 | 명령 < 파일 : 파일의 데이터를 명령에 입력 |

### 표준 출력

- 표준 출력 변경 : cat 명령어 > , >> 사용
- cat 명령어: 원래 표준 입력인 키보드로부터 입력받은 내용을 표준 출력인 터미널로 보내는 명령어
- 하지만 다음과 같이 cat > 파일명 실행하고 파일의 내용을 작성한 후, ctrl + C를 눌러 종료하면 키보드로부터 입력받은 내용을 파일로 떨어뜨림

<img src ="https://file.notion.so/f/s/889876f3-e576-4b6a-ac2d-ea2b8e69efda/Untitled.png?id=ed720c41-bc17-4cd1-a048-63dc5cc8e8e9&table=block&spaceId=f7f5a27f-fb49-4dd8-8a47-1d1cb5901c61&expirationTimestamp=1683078381734&signature=XBYCjlkyGezAtFAsY4_ENDYfw2cWWdSqYP4dfQLL2fQ&downloadName=Untitled.png">

<img src ="https://file.notion.so/f/s/49ac2693-301f-498d-a779-dab46216caa3/Untitled.png?id=0cbb1708-8a71-4107-aca8-0a628062b593&table=block&spaceId=f7f5a27f-fb49-4dd8-8a47-1d1cb5901c61&expirationTimestamp=1683078424031&signature=sAwh3Lg-6ZnsaEtgCTbzMztAVFtJ2Fb3UdgoZqAdYzE&downloadName=Untitled.png">

<img src ="https://file.notion.so/f/s/3783baea-44ea-499c-8c40-43314060821b/Untitled.png?id=75549ea9-c52a-4f82-a13c-addd297e66a9&table=block&spaceId=f7f5a27f-fb49-4dd8-8a47-1d1cb5901c61&expirationTimestamp=1683078403884&signature=IwTlLkUDZRCuowuINf0EfrndoKjr7g8p_W0R5bgYuo4&downloadName=Untitled.png">

### 기타 예시

→ > 과 >>의 차이점
→ >과 마찬가지로 표준 출력에 전달된 내용을 지정된 파일로 넘겨줌
→ >는 기존의 내용을 삭제하고 덮어쓰지만 >>는 기존의 내용에 추가한다는 점

Ex1) cat test1.txt의 결과를 test.txt로 저장한다. (표준 출력 리다이렉션)

$cat test1.txt > test.txt

Ex2) cat test1.txt를 실행했을 때 에러가 발생하면 err.txt로 저장한다. (표준 에러 리다이렉션)

$cat test1.txt 2 > err.txt

*표준 출력/에러 모두 리다이렉션을 하고 싶다면 파일명 앞에 &추가

Ex) cat test1.txt >& test_err.txt

Ex3) test1.txt의 내용을 sort명령어의 입력으로 받는다. (표준 입력 리다이렉션)

$sort < test1.txt

Ex4) cat test1.txt를 실행한 결과를 test1.log로 저장하고 에러가 발생하는 경우에도 test1.log로 저장한다.

$cat test1.txt > test1.log 2 >&1

 