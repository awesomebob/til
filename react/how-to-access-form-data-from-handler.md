# How to access form data from handler

We can use refs to assign form values to properties on the component object.

        <input placeholder="Name:" ref={(input) => this._author = input}/>

This `ref` is a function that passes the HTML element as its argument.
Then it assigns the element to a property of the React Component.
Later, we can access the value of the element with this.props.prop.value.

Functions in JavaScript are first-class citizens, so we can pass them as props to other components.

        class CommentBox extends React.Component {
          render() {
            return(
              <div className="comment-box">
                <CommentForm addComment={this._addComment.bind(this)} />
              </div>
            );
          }
        }

        _addComment(author, body) {

        }

