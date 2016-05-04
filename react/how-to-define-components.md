# How to define React Components

Components are Javascript classes that extend the React.Component class.

        class StoryBox extends React.Component {
          render() {
            return( <div>Story Box</div> );
          }
        }

Each React component must have a render method.
The render function contains JSX, no need for quotes.

To render the component:

        ReactDOM.render(
          <StoryBox />, document.getElementById('story-app')
        );

The ReactDOM.render() function takes a React Component and an HTML element to be its container.

