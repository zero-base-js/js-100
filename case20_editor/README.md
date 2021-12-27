## 글쓰기 에디터

### Document.execCommand()

https://developer.mozilla.org/ko/docs/Web/API/Document/execCommand

-HTML 문서가 designMode로 전환되면 문서에서 execCommand 메서드를 사용할 수 있게 되는데 이것을 이용해서 문서의 편집 가능한 영역을 변경할 수 있음

```
bool = document.execCommand(aCommandName, aShowDefaultUI, aValueArgument)
```

#### 매개 변수

- aCommandName
  - 실행해야할 명령어 이름 DOMString을 나타냅니다. 사용 가능한 명령어 목록은 Commands를 참고하세요.
- aShowDefaultUI
  - 기본 사용자 UI가 나타나야하는지를 보여주는 Boolean 값입니다. Mozilla에서는 구현되어 있지 않습니다.
- aValueArgument
  - 입력 변수가 필요한 명령어(insertImage와 같이 삽입할 이미지의 URL이 필요한)의 경우 이 DOMString으로 정보를 전달합니다. 변수가 필요하지 않으면 null을 표기합니다.

```
document.execCommand('Italic')           // 기울이기
document.execCommand('Underline')        // 밑줄
document.execCommand('StrikeThrough')    // 중간줄
document.execCommand('Cut')              // 자르기
document.execCommand('Copy')             // 복사하기
document.execCommand('Paste')            // 붙혀넣기
document.execCommand('Undo')             // 실행취소
document.execCommand('Redo')             // 다시실행
document.execCommand('insertorderedList')    // 글번호 매기기
document.execCommand('insertunorderdList')   // 글머리 매기기
document.execCommand('outdent')          // 내어쓰기
document.execCommand('indent')           // 들여쓰기
document.execCommand('justifyleft')      // 왼쪽정렬
document.execCommand('justifycenter')    // 가운데정렬
document.execCommand('justifyright')     // 오른쪽정렬
```
