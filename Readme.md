# Javascript Basic Projects
## All the Js codes are written here.
- Color Switcher

```javascript
const buttons = document.querySelectorAll(".button");
const body = document.querySelector("body");

buttons.forEach((button) => {
  console.log(button);
  button.addEventListener("click", (e) => {
    console.log(e);
    console.log(e.target);
    if (e.target.id === "grey") {
      body.style.backgroundColor = "grey";
    } else if (e.target.id === "blue") {
      body.style.backgroundColor = "rgb(86, 86, 239)";
    } else if (e.target.id === "white") {
      body.style.backgroundColor = "rgb(238, 107, 107)";
    } else if (e.target.id === "yellow") {
      body.style.backgroundColor = "yellow";
    }
  });
});
```

- BMI calculator

```javascript
const form = document.querySelector("form");

// This usecase gives you an empty value
// const height = parseInt(document.querySelector('#height').value)

document.querySelector("#results").innerHTML = "Result";

form.addEventListener("submit", (e) => {
  e.preventDefault();

  const height = parseInt(document.querySelector("#height").value);
  const weight = parseInt(document.querySelector("#weight").value);
  const results = document.querySelector("#results");

  if (height === "" || height < 0 || isNaN(height)) {
    results.innerHTML = `Please give a valid height ${height}`;
  } else if (weight === "" || weight < 0 || isNaN(weight)) {
    results.innerHTML = `Please give a valid weight ${weight}`;
  } else {
    const val = (weight / ((height * height) / 10000)).toFixed(2);

    if (val < 18.6) {
      results.innerHTML = `You are Under weight and your BMI is ${val}`;
    } else if (val >= 18.6 && val <= 24.9) {
      results.innerHTML = `You are normal range and your BMI is ${val}`;
    } else if (val > 24.9) {
      results.innerHTML = `You are over weight and your BMI is ${val}`;
    }
  }
});
```

- To Do list
```javascript
const inputBox = document.getElementById('input-box')
const listContainer = document.getElementById('list-container')

function addTask() {
    if (inputBox.value === '') {
        alert('You must write something.')
    }
    else {
        let li = document.createElement("li")
        li.innerHTML = inputBox.value;
        listContainer.appendChild(li);

        let span = document.createElement("span")
        span.innerHTML = "\u00d7"
        li.appendChild(span)
    }
    inputBox.value = ' '
}

listContainer.addEventListener("click", (e) => {
    if (e.target.tagName === "LI") {
        e.target.classList.toggle("checked");
    }
    else if (e.target.tagName === "SPAN") {
        e.target.parentElement.remove();
    }
})
```







