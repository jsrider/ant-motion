---
order: 6
title: svg 形变动画
mouseEnter: true
---

点击切换线效果。


```jsx
import TweenOne from 'rc-tween-one';
import {Button} from 'antd';
import SvgMorphPlugin from 'rc-tween-one/lib/plugin/SvgMorphPlugin';
TweenOne.plugins.push(SvgMorphPlugin);

class Demo extends React.Component {

  render() {
    return (
      <div style={{ textAlign: 'center', marginTop: 40 }}>
        <svg width="200" height="130" version="1.2"
          style={{ display: 'block', margin: 'auto' }}
        >
          <TweenOne
            animation={{ 
              d: 'M60,10L60,90L140,90L140,10Z', 
              yoyo: true, 
              repeat: -1, 
              duration: 1000 
            }}
            style={{ fill: '#019BF0'}}
            paused={this.props.paused}
            component="path"
            d="M60,50 a40,40 0 1,0 80,0a40,40 0 1,0 -80,0z"
            attr="attr"
          />
        </svg>
      </div>
    );
  }
}
Demo.propTypes = {
  children: React.PropTypes.any,
  className: React.PropTypes.string,
  paused: React.PropTypes.bool,
};
ReactDOM.render(<Demo/>, mountNode);

```
