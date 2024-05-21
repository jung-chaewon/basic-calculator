# basic-calculator

![Animation](https://github.com/jung-chaewon/basic-calculator/assets/131144717/7fd9aa73-97f8-46fa-95ba-40e248efab4f)


자바스크립트를 이용한 계산기 만들기
### script
``` javascirpt
  const buttonsEl = document.querySelectorAll("button");
const inputFieldEl = document.getElementById("result");

for (let i = 0; 1 < buttonsEl.length; i++) {
    buttonsEl[i].addEventListener("click", () => {
        const buttonValue = buttonsEl[i].textContent;
        if (buttonValue === "C") {
            clearResult();
        } else if (buttonValue === "=") {
            calculateResult();
        } else {
            appendValue(buttonValue);
        }
    });
}
function clearResult() {
    inputFieldEl.value = "";
}
function calculateResult() {
    try {
        inputFieldEl.value = eval(inputFieldEl.value);
    } catch (error) {
        console.error("계산오류:", error)
        inputFieldEl.value = "오류";
    }
}
function appendValue(buttonValue) {
    inputFieldEl.value += buttonValue;
}
```
