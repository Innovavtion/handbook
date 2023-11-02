**useContext** - это React Hook, который позволяет вам читать и подписываться на **контекст** вашего компонента.

---

**Контекст** - Обычно вы будете передавать информацию от родительского компонента к дочернему через реквизиты. Но передача свойств может стать многословной и неудобной, если вам нужно передать их через множество компонентов в середине или если многим компонентам в вашем приложении нужна одна и та же информация.

Контекст позволяет родительскому компоненту сделать некоторую информацию доступной для любого компонента в дереве под ним — независимо от того, насколько глубоко — без передачи ее явно через реквизиты.

---

Использование **useContext**:

```ts
import { createContext, useContext, useState } from "react";

// Создание контекста
const ThemeContext = createContext(null);

export default function MyApp() {
  // Создаем state где храним тему нашего сайта
  const [theme, setTheme] = useState("light");
  // Класс который будет использоваться для определенной темы
  const className = "div-" + theme;

  return (
    // Использование созданного контекста и передача значения value
    <ThemeContext.Provider value={theme}>
      <div className={className}>
        Theme {theme}
        <Button>Изменить тему</Button>
      </div>
    </ThemeContext.Provider>
  );
}

function Button({ children }) {
  // Используем контекст для нашей кнопки
  const theme = useContext(ThemeContext);
  // Класс который будет использоваться для определенной темы
  const className = "button-" + theme;

  return <button className={className}>{children}</button>;
}
```
