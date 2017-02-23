---
order: 0
title: 示例
---

````jsx
import { SearchBar, Button, WhiteSpace, WingBlank } from 'antd-mobile';

class SearchBarExample extends React.Component {
  state = {
    value: '美食',
    focused: false,
  };
  onChange= (value) => {
    this.setState({ value });
  };
  clear = () => {
    this.setState({ value: '' });
  };
  render() {
    return (<div className="need-left-right-margin">
      <div className="sub-title">普通</div>
      <SearchBar placeholder="搜索" />
      <WhiteSpace />
      <div className="sub-title">自动获取光标</div>
      <SearchBar placeholder="自动获取光标" autoFocus />
      <WhiteSpace />
      <div className="sub-title">手动获取获取光标</div>
      <SearchBar
        placeholder="手动获取获取光标"
        focused={this.state.focused}
        onFocus={() => {
          this.setState({
            focused: false,
          });
        }}
      />
      <WhiteSpace />
      <WingBlank>
        <Button
          onClick={() => {
            this.setState({
              focused: true,
            });
          }}
          type="primary"
        >点击获取光标</Button>
      </WingBlank>
      <WhiteSpace />
      <div className="sub-title">显示取消按钮</div>
      <SearchBar
        value={this.state.value}
        placeholder="搜索"
        onSubmit={value => console.log(value, 'onSubmit')}
        onClear={value => console.log(value, 'onClear')}
        onFocus={() => console.log('onFocus')}
        onBlur={() => console.log('onBlur')}
        showCancelButton
        onChange={this.onChange}
      />
    </div>);
  }
}

ReactDOM.render(<SearchBarExample />, mountNode);
````

```css
.am-search {
  border-bottom: 1px solid #ccc;
}
```
