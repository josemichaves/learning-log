# React Forms

To add a form we add it as any other component

```jsx
import React, { useState} from 'react';

const Form = () => {

    const [data, setData] = useState({
        name: '',
        surname: ''
    })

    const handleInputChange = (event) => {
        // console.log(event.target.name)
        // console.log(event.target.value)
        setData({
            ...data,
            [event.target.name] : event.target.value
        })
    }

    const sendData = (event) => {
        event.preventDefault()
        console.log(`sending data... ${data.name} ${data.surname}`)
    }

    return (
        <>
            <h1>Form</h1>
            <form className="row" onSubmit={sendData}>
                <div className="col-md-3">
                    <input type="text" placeholder="Name" className="form-control" onChange={handleInputChange} name="name"></input>
                </div>
                <div className="col-md-3">
                    <input type="text" placeholder="Surname" className="form-control" onChange={handleInputChange} name="surname"></input>
                </div>
                <button type="submit" className="btn btn-primary">Enviar</button>
            </form>
            <ul>
                <li>{data.name}</li>
                <li>{data.surname}</li>
            </ul>
        </>
    );
}
 
export default Form;
```

### State

```jsx
const [data, setData] = useState({
    name: '',
    surname: ''
})
```

The state is where we'll be saving our data from the form

### Form

We need to call the component Form to create a form

```jsx
<form className="row" onSubmit={sendData}>
                <div className="col-md-3">
                    <input type="text" placeholder="Name" className="form-control" onChange={handleInputChange} name="name"></input>
                </div>
                <div className="col-md-3">
                    <input type="text" placeholder="Surname" className="form-control" onChange={handleInputChange} name="surname"></input>
                </div>
                <button type="submit" className="btn btn-primary">Enviar</button>
            </form>
```

### On change

We need to listen the form, so we put an `onChange` and we can monitor when te data chanes and update the statewith the new data.

```jsx
const handleInputChange = (event) => {
        // console.log(event.target.name)
        // console.log(event.target.value)
        setData({
            ...data,
            [event.target.name] : event.target.value
        })
    }
```

### OnSubmit

And finally with the `onSubmit` we send the data, in our case we're just doing a console log with the actual state that is the data introduced before

```jsx
 const sendData = (event) => {
        event.preventDefault()
        console.log(`sending data... ${data.name} ${data.surname}`)
    }
```

