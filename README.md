# typescript-learn
All the painful typescript types


## Working practices

- place all types in `interfaces` folder
- use union for string types, don't create unnecessary types
- group by domain

## React Input
```ts
  const handleChange = (evt: React.FormEvent<HTMLInputElement>) => {
    const field = evt.currentTarget.name;
    const value = evt.currentTarget.value;

    setState((state: Job) => ({
      [field]: value,
      ...state,
    }));
  };
```

## React Input resolving Dataset

```ts
  const handleRedirect = (evt: React.MouseEvent<HTMLSpanElement>) => 
    history.replace(evt.currentTarget.dataset.link);
```


## React FC

```ts
import React from 'react';

interface Props {
  col: number;
}

const View: React.FC<Props> = ({ col = 1, children }) => {
  const styles = {
    width: `${80 * i}px`,
  };
  return <div styles={styles}>{children}</div>;
};

export default View;
```

## Extending React.CSSProperties

Sometimes, we want to inject custom CSS variables to a class, e.g.
```css
/* Using css.modules */
.someClass {
  --row: 1
  grid-row: var(--row);
}
```

```js
type EnhancedProperties = React.CSSProperties & {
  '--row': number;
};

const style={
  '--row': 1
}

return <div style={style} className={styles.someClass}>...</div>
```

## Typescript enum from array

Allows enums to be enumerated:

```ts
const  MONTHS = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'];

type Month = typeof MONTHS[number]
```
