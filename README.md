What is Redux ??

        Its a state management library
        It makes creating complex applications easier
        Not required to create a React App
        Not explicitely designed to work with React
  
Redux Lifecycle:

        Action Creator - Action - Dispatch - Reducers - State
        
        Any time we want to change the state or the data of our application we're going to call an action creator, calling an action creator is
        going to produce an action object this action object describes exactly how we want to change data inside of application that action
        object gets fed to the dispatch function which in turn is going to make copies. We can imagine of the action object and feed those
        copies to each of our different reducers in turn. The reducers are going to run , They're going to process those actions are the forms
        that came in modify their data and then eventually return some new data that data that gets returned gets forint into some new state 
        object. So then we wait until we need to somehow updates our state again at some point in the future.  (Refer To Redux Cycle image ).
        
        Combine reducers , Remember the different reducers we put together were simple functions. All these different functions need to be
        somehow wired up together. We wire up all the different reducers together by making use of the combine reducers function. Now
        Considering an Example of Insurance company, our redux lifecycle will be :

        Person Dropping the form - the form - form reciever - departments - compiled department data

Rules of Reducers : 
        
        Always return some value
        control the undefined error, by putting some default values or empty arrays in variable

Installing Libraries of React-Redux Project :
        
        npm install --save react react-redux

We Have to combine reducers.
We have to create provider by importing  { Provider } from 'react-redux', { createStore } from 'redux' and then on your index file, wrap your App component in Provider as :
              
         ReactDOM.render(
         <Provider store={createStore(reducers)}>
                <App />
         </Provider>,
         document.querySelector('#root'));

The Connect Function :

        import { connect } from 'react-redux';        //Imporitng
        export default connect( mapStateToProps )( COMPONENT );               //At the end of component
        
        We always going to import connect at the top
        We always going to call connect and pass in our component as 2nd function call
        We always going to define mapStateToProps
        mapStateToProps is always get 1st argument = state and we always going to return an object that is going to show up some props inside of our component.
        
               const mapStateToProps = (state) => {
                return { songs : state.song }
                };
