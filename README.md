# Lecture7-8

## Синхронный JavaScript: Как следует из названия, синхронный означает быть последовательным, т.е. каждый оператор кода выполняется один за другим. Итак, по сути, оператор должен дождаться выполнения предыдущего оператора.Давайте разберемся в этом с помощью примера.
## Асинхронный JavaScript: Асинхронный код позволяет программе выполняться немедленно, в то время как синхронный код блокирует дальнейшее выполнение оставшегося кода до тех пор, пока не завершит текущий. Это может показаться не такой уж большой проблемой, но когда вы видите ее в более широком плане, вы понимаете, что это может привести к задержке работы пользовательского интерфейса.

## Итак, что делает код, так это сначала он регистрируется в Hi, затем вместо выполнения функции setTimeout он регистрируется в End, а затем запускает функцию setTimeout.Сначала, как обычно, было введено сообщение Hi. Поскольку мы используем браузеры для запуска JavaScript, существуют веб-API, которые обрабатывают эти вещи для пользователей. Итак, что делает JavaScript, так это передает функцию setTimeout в таком веб-API, а затем мы продолжаем запускать наш код как обычно. Таким образом, он не блокирует выполнение остальной части кода, и после выполнения всего кода он помещается в стек вызовов и затем, наконец, выполняется. Это то, что происходит в асинхронном JavaScript.

## Операторы try и catch.Оператор try определяет блок кода, который во время выполнения будет проверяться на возникновение ошибок.
## Оператор catch определяет блок кода, который будет выполняться, если в блоке оператора try возникнет ошибка.

## Async/await — это специальный синтаксис, который предназначен для более простого и удобного написания асинхронного кода. Появился он в языке, начиная с ES2017 (ES8).Синтаксис «async/await» упрощает работу с промисами (позволяет асинхронный код записывать синхронным способом).

## API – Application Programming Interface, что значит программный интерфейс приложения. В контексте API слово «приложение» относится к любому ПО с определенной функцией. Интерфейс можно рассматривать как сервисный контракт между двумя приложениями. Этот контракт определяет, как они взаимодействуют друг с другом, используя запросы и ответы. Документация API содержит информацию о том, как разработчики должны структурировать эти запросы и ответы
```js
async function getData() {
    try {
        let { data } = await axios.get(API)
        get(data)
    } catch (error) {
        console.log(error);
    }
}

getData()

btn1.onclick = () => {
    let user = {
        id: new Date().getTime(),
        title:inp1.value,
    }
    post(user)
    inp1.value = ''
}

async function post(user) {
    try {
        let { data } = await axios.post(API, user)
        getData()
    } catch (error) {
        console.log(error);
    }
}
```

```js
async function delUser(id) {
  try {
    let { data } = await axios.delete(`https://63d14a1e3f08e4a8ff94b1a5.mockapi.io/department/${id}`)
    getData()
  } catch (error) {
    console.log(error);
  }
}
```

```js
async function getData() {
  try {
    let { data } = await axios.get(
      "https://63d14a1e3f08e4a8ff94b1a5.mockapi.io/department"
    );
    get(data);
    console.log(data);
  } catch (error) {
    console.log(error);
  }
}

getData();
```
```js
async function editUser(id, edit) {
  try {
    const { data } = await axios.put(`https://63d14a1e3f08e4a8ff94b1a5.mockapi.io/department/${id}`, edit);
    getData()
  } catch (error) {
    console.log(error);
  }
}

function editdata(e) {
  modal.showModal()
  formEdit["title"].value = e.title
  formEdit.onsubmit = (event) => {
    event.preventDefault()
    let object = {
      title:formEdit["title"].value
    }
    editUser(e.id, object)
    modal.close()
  }
}
```



