## React props basic

Passing props to a component from the parents, for instance, The topics props passed from App to Nav

```javascript
import './App.css'

export function Nav({topics}) {
  console.log(topics)
  const list = []
  for (let i = 0; i < topics.length; i++) {
    let t = topics[i]
    list.push(<li key={t.id}>{t.title}</li>)
  }

  return (
    <>
      <nav>
        {list}
      </nav>
    </>
  )
}

function App() {
  const topics = [
    {id: 1, title: 'html', body: 'html ...'},
    {id: 2, title: 'css', body: 'css ...'},
    {id: 3, title: 'javascript', body: 'js ...'},
  ]

  return (
    <Nav topics={topics} />

  )
}
 

export default App
```

You can omit `props` and replace it by directly destructuring the `topics` property from the parameter.
```
export function Nav(props) { // Destructuring props to Nav({ topics })
  const list = []
  for (let i = 0; i < props.topics.length; i++) { // you can ommit props
    let t = props.topics[i]
    list.push(<li key={t.id}>{t.title}</li>)
  }

```
