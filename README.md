# mobx-react-observerwithprops

In `mobx-react`, any change to any prop of a react component will force re-rendering. This is undesirable in many circumstances. A solution to this within `mobx-react` is being worked on, but at the moment, the desired behaviour can be achieved with this decorator, which will copy the values from the defined props to observable members on the class. 

## Synopsis
````jsx
@observerWithProps({
  showValue: false,
  value: 10
})
class Test extends React.Component {
  render() {
    console.log("render"); // will not happen if value changes while showValue is false
    if (this.showValue) return <div>{this.value}</div>;
    else return <div>Nothing shown</div>;
  }
};
````
