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
```javascript
export function Nav(props) { // Destructuring props to Nav({ topics })
  const list = []
  for (let i = 0; i < props.topics.length; i++) { // you can ommit props
    let t = props.topics[i]
    list.push(<li key={t.id}>{t.title}</li>)
  }

```

## React props feature 1.
Once you are determinded to pass props between components, the initial type of props is a string. for instance, the below code snippet brought `id` from the `Nav` component, there's `<a>` tag in the `Nav` component sets `id={t.id}` and passing `id` as a string. If it is necessary to get `Number`, convert it using `Number()`

```javascript
 if (mode === 'READ') {
    let title, body = null
    for(let i=0; i < topics.length; i++) {
      console.log(id, topics[i].id)
      console.log(typeof(id), typeof(topics[i].id))
      if (topics[i].id === id) {
        title = topics[i].title
        body = topics[i].body
      }
    }
    content = <Article title={title} body={body} />
```

```javscript
export function Nav({topics, onChangeMode}) {
  const list = []
  for (let i = 0; i < topics.length; i++) {
    let t = topics[i]
    list.push(<li key={t.id}>
      <a id={t.id} href="" onClick={e => {
      e.preventDefault()
      onChangeMode(Number(e.target.id))
    }}>{t.title}</a></li>)
  }

```
