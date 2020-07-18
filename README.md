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
