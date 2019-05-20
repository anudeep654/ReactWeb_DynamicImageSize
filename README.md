
## REACT WEB => YOUTUBE API SEARCH

![alt text](https://i.ibb.co/t4DvP8K/Screen-Shot-2019-05-20-at-9-57-20-PM.png)

##### This app is done in React Web in which the each image card uses a reference and we have added a listener,when the image loads then we calculate the height of image and we will re render the image. please find the code below.

``` class ImageCard extends React.Component {
  constructor(props) {
    super(props);
    this.imageRef = React.createRef();
  }

  state = {
    spans: 0
  };

  componentDidMount() {
    this.imageRef.current.addEventListener("load", this.setSpans);

    //console.log(this.imageRef);
  }
  setSpans = () => {
    const height = this.imageRef.current.clientHeight;

    const spans = Math.ceil(height / 10);

    this.setState({
      spans
    });
  };
  render() {
    const { description, urls } = this.props.image;
    return (
      <div style={{ gridRowEnd: `span ${this.state.spans}` }}>
        <img alt={description} src={urls.regular} ref={this.imageRef} />
      </div>
    );
  }
} ```
