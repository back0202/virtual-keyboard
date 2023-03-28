# Virtual Keyboard
npm install 한후 package.json에 입력된 scripts를 참고하여 dev server를 실행하거나 build 

# 고민한점
1. 어디까지 css고 어디까지 js일까
- switch를 클릭하게 되면 checkbox가 체크 되는데 그때 어떤 건 css로 하고 어떤건 js로 한다. 내생각에는 css로 할수있는 transform, transition, animation이면 css로 하고 아니면 js로 하는게 아닐까.

# 알게된점
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
