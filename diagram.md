# Diagram

## Redux

### Store

```mermaid
graph TD;
    hobby-->rootReducer;
    user-->rootReducer;
    rootReducer-->store;
```

```
const rootReducer = combineReducers({
  hobby: hobbyReducer,
  user: userReducer,
});
```

```
const store = createStore(rootReducer);
```

### Action

```mermaid
graph TD;
    action-->ADD_HOBBY;
    action-->SET_ACTIVE_HOBBY;
```

```
export const addNewHobby = (hobby) => {
  return {
    type: 'ADD_HOBBY',
    payload: hobby,
  }
}

export const setActiveHobby = (hobby) => {
  return {
    type: 'SET_ACTIVE_HOBBY',
    payload: hobby,
  }
}
```

---

## React

### State management

```mermaid
graph TD;
    Provider-.store.->App;
```
### Component

```mermaid
graph TD;
    App-->HomePage;
    HomePage-->HobbyList;
```

### UI receive state and dispatch action

```mermaid
graph TD;
    store-.->state;
    state-. useSelector .->HomePage;
    HomePage-. useDispatch .->action;
    action-.->store;
```