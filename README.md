# adi_redux_test

# Cara Install
```sh
$ npm install adi_redux_test
```sh

# Tambahkan script pada index.js
```sh

import rootReducer from 'adi_redux_test'; //tambah script ini

```

# mapDispatchToProps
mapDispatchToProps yang dapat anda gunakan :
```sh
const mapDispatchToProps = dispatch => {
  return {
    postTodos: (value) => dispatch({ 
      type: "ADD_TODO", 
      payLoad: {
        id        : value.id,
        text      : value.text,
        complete : value.complete
      }
    }),
    updateTodos: (value) => dispatch({
      type: "UPDATE_TODO",
      payLoad: {
        id        : value.id,
        text      : value.text,
        complete : value.complete
      }
    }),
    doneTodo: (value) => dispatch({
      type: "DONE_TODO",
      payLoad: {
        id        : value.id,
        complete : value.complete
      }
    }),
    deleteTodo: (value) => dispatch({
      type: "DELETE_TODO",
      payLoad: {
        id        : value.id,
        complete : value.complete
      }
    }),
    clearData: () => dispatch({
      type: "CLEAR_DATA"
    })
  };
};
```

# mapStateToProps
mapStateToProps yang dapat digunakan :
```sh
const mapStateToProps = (state) => {
  var rowTodo = state.listTodos.filter(function (item) {
    return item.completed === true;
  });

  var rowDone = state.listTodos.filter(function (item) {
    return item.completed === false;
  });

  return {
    rowTodo,
    rowDone,
  }
}
```
