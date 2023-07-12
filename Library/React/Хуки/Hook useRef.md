**useRef** - это React Hook, который позволяет ссылаться на значение, которое позволяет сохранить значание между рендерингами.

**Для чего используют**:

- Его можно использовать для **хранения изменяемого значения**, который **не вызывает рендеринга при обновлении**.
- Его можно использовать для прямого доступа к элементу **DOM**.

**Входной параметр** - это то что **мы помещяем**(initialValue) в хук useRef:

```ts
const firstUseRef = useRef(null);
```

**Возвращает**:

- **current** - изначально установленное initialValue, которое вы передали.
- **current (DOM)** - Если вы установите атрибут ref в React jsx элемент, то в current будет хранится текущий DOM элемент.

```ts
function TextInputWithFocusButton() {
  const inputEl = useRef(null);
  const onButtonClick = () => {
    // `current` указывает на смонтированный элемент `input`
    inputEl.current.focus();
  };
  return (
    <>
      // Вот собственно сам атрибут ref в который мы передаем нащ объект useRef
      <input ref={inputEl} type="text" />
      <button onClick={onButtonClick}>Установить фокус на поле ввода</button>
    </>
  );
}
```

---

[_Новая React документация_](https://react.dev/reference/react/useRef), [_Старая React документация_](https://ru.legacy.reactjs.org/docs/hooks-reference.html#useref), [_Можно тут_](https://www.w3schools.com/react/react_useref.asp).
