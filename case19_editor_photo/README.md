## Photo Editor
- 이미지 에디터에 대한 이해
- crop을 사용하여 이미지를 잘라보기
- filter를 사용하여 이미지에 효과 부여하기
- drag and drop을 사용하여 이미지 업로드하기
### FileReader
https://developer.mozilla.org/ko/docs/Web/API/FileReader

- 웹 애플리케이션이 비동기적으로 데이터를 읽기 위하여 읽을 파일을 가리키는 File 또는 Blob 객체를 이용해서 내용을 읽고 저장하는 역할을 합니다.
### crop
1. https://www.iloveimg.com/crop-image
1. https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/drawImage
- 이미지를 원하는 부분만 잘라냅니다.
```js
this.targetCtx.drawImage(
    img,
    x * buffer,
    y * buffer,
    width * buffer,
    height * buffer,
    (w - w * 0.9) / 2,
    (h - h * 0.9) / 2,
    w * 0.9,
    h * 0.9
)
```

### drag and drop
https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API/File_drag_and_drop

- 파일을 Drag and Drop을 통해서 업로드 합니다.