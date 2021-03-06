# Хранилище \(Store\)

Хранилище \(store\) — это объект, который:

* содержит состояние приложения;
* отображает состояние через `getState()`;
* может обновлять состояние через `dispatch()`;
* позволяет регистрироваться \(или удаляться\) в качестве слушателя изменения состояния через `subscribe()`.

Хранилище в приложении всегда уникально.

Очень легко создать Хранилище \(Store\), если у вас есть редюсер. Теперь мы их импортируем и передадим в `createStore()`.

```jsx
import { createStore } from "redux";
import rootReducer from "../reducers";

export const configureStore = () => {
  return createStore(
    rootReducer
  );
};
```

Вы можете объявить начальное состояние, передав его вторым аргументом в `createStore()`. Это полезно для пробрасывания состояния на клиент из состояния приложения Redux, работающего на сервере, когда вы пишете универсальное приложение.

```jsx
let store = createStore(todoApp, window.STATE_FROM_SERVER)
```

Обновление состояния:

```jsx
store.dispatch(setMessage('Something'))
```

