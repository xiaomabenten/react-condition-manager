# react-condition-manager
> React condition manager.


## properties:
```javascript

  static propTypes = {
    className:PropTypes.string,
    conditionList:PropTypes.array,
  };

  static defaultProps = {
    conditionList:[]
  };
  
```

## usage:
```jsx
class App extends React.Component{
  state = {
    index:0,
    status:'N'
  };

  _click(status) {
    console.log(status);
    if(status==='F0'){
      this.setState({
        index:0,
        status:'F0'
      })
    }else if(status==='F1'){
      this.setState({
        index:1,
        status:'F1'
      })
    }else{
      this.setState({status});
    }
  }

  render(){
    const {index,status} = this.state;
    return (
      <div className="hello-react-condition-manager">
        <ReactConditionManager conditionList={[true,false,true]}>
          <div>when condition 1</div>
          <div>when condition 2</div>
          <div>when condition 3</div>
        </ReactConditionManager>


        <button onClick={this._click.bind(this,'N')}>Set Status - N</button>
        <button onClick={this._click.bind(this,'A')}>Set Status - A</button>
        <button onClick={this._click.bind(this,'F0')}>Set Status - F-0</button>
        <button onClick={this._click.bind(this,'F1')}>Set Status - F-1</button>

         <ReactConditionManager conditionList={[
           index === 0 && status === 'N',
           index === 0 && status === 'A',
           index === 0 && status === 'F0',
           index === 1 && status === 'F1',
         ]}>
          <div>when condition 1  ---. N</div>
          <div>when condition 2  ---. A</div>
          <div>when condition 3  ---. F (index = 0)</div>
          <div>when condition 4  ---. F (index = 1)</div>
        </ReactConditionManager>
    </div>
    );
  }
}

```



## resource:
+ http://www.cnblogs.com/Kummy/p/4966937.html
+ https://github.com/steven5538/vue-button
+ https://yarnpkg.com/en/docs/install

