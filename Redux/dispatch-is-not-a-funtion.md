# 'dispatch' is not a function when argument to mapToDispatchToProps() in Redux

['dispatch' is not a function](https://stackoverflow.com/questions/35443167/dispatch-is-not-a-function-when-argument-to-maptodispatchtoprops-in-redux)

今天在项目中第一次使用 Redux,过程中有很多坑，但是最后解决也很好。这里记录一个有意思的 bug 原本以为 connect 的参数没有先后，但是出现了这个 bug —— `'dispatch' is not a function` 之后 Google 了解到 **If you want to use mapDispatchToProps without a mapStateToProps just use null for the first argument.**


```js
// mapStateToProps：将state映射到组件的props中
const mapStateToProps = (state) => {
  return {
    userAccountInfo: state.userAccountInfo
  }
}

// mapDispatchToProps：将dispatch映射到组件的props中
const mapDispatchToProps = (dispatch, ownProps) => {
  return {
    changeUserAccountAsync (data) {
        dispatch(changeUserAccountAsync(data))
    }
  }
}
export default connect(mapStateToProps, mapDispatchToProps)(App);
```
```js
// mapDispatchToProps：将dispatch映射到组件的props中
const mapDispatchToProps = (dispatch) => {
  return {
    changeUserAccountAsync (data) {
        dispatch(changeUserAccountAsync(data))
    }
  }
}

// If you want to use mapDispatchToProps without a mapStateToProps just use null for the first argument.
export default connect(null, mapDispatchToProps)(UserInfo);
```