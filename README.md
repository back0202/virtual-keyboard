# Virtual Keyboard
npm install 한후 package.json에 입력된 scripts를 참고하여 dev server를 실행하거나 build 
# 로직
1. 다크모드
2. 폰트 변경
4. 키보드이벤트는 키보드 색을 변경하기 위해, 한글이면 error클래스를 넣기 위해
5. input이벤트는 value에 영어만 넣기
6. 키보드를 누르고 있을때 마우스 누르기 안됨, 마우스를 누르고 잇을때 키보드 누르기 안됨
7. 키보드나 마우스를 눌렀을때 색변경, 때면 돌아오기
# 고민한점
1. 어디까지 css고 어디까지 js일까
- switch를 클릭하게 되면 checkbox가 체크 되는데 그때 어떤 건 css로 하고 어떤건 js로 한다. 내생각에는 css로 할수있는 transform, transition, animation이면 css로 하고 아니면 js로 하는게 아닐까.

# 알게된점
1. 비용을 최소화 하기 위해 document.getElementById가 아닌 #containerEl.querySelector을 이용
```
  #assignElement() {
    this.#containerEl = document.getElementById("container");
    this.#swichEl = this.#containerEl.querySelector("#switch");
    this.#fontSelectEl = this.#containerEl.querySelector("#font");
    this.#keyboardEl = this.#containerEl.querySelector("#keyboard");
    this.#inputGroupEl = this.#containerEl.querySelector("#input-group");
    this.#inputEl = this.#inputGroupEl.querySelector("#input");
  }
```
2. document로 키보드 이벤트를 걸어준이유는 input에 포커스돼있을때랑 안돼있을때 둘다 키보드 이벤트를 줄려고
```
  #addEvent() {
    document.addEventListener("keydown", this.#onKeyDown.bind(this));
    document.addEventListener("keyup", this.#onKeyUp.bind(this));
```
3. 특수 키는 브라우저 마다 다를수 있다.
4. 키보드이벤트를 주면 event안에 code라는게 있다 이걸로 무슨 키가 눌렸는지 확인하고 키보드 박스에서 이 키로 찾는다.
5. event.key는 어떤 값인지 알려줌. 그래서 한글인지 아닌지 알 수 있음
6. 속성에 data-val=1 은 dataset.val로 불러 올수 잇다.
7. filter: invert(100%) hue-rotate(180deg); css 속성
