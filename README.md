# Dependency Graph Viewer

Minimal web to view a graphs

# Use Cases

- graph of our IT dependencies
- graph of our software libraries
- graph of our network

# Data

Just add relationships in **/graph.json**

```
{
  "nodes": [
    {
      "name": "web",
      "position": 0,
      "class": "web"
    },
    {
      "name": "api",
      "position": 1,
      "class": "api"
    },
    {
      "name": "database",
      "position": 2,
      "class": "database"
    }
  ],
  "links": [
    {
      "source": 0,
      "target": 1,
      "type": "depends"
    },
    {
      "source": 1,
      "target": 2,
      "type": "depends"
    }
  ]
}
```

# Steps

- npm install
- export these values

```
export ENABLE_SECURITY=true
export AUTH_USER=jane
export AUTH_PASSWORD=doe
export PORT=8080
```

- Launch the app

```
npm run start
```

## API ENDPOINTS

### Projects

```javascript
// Get all projects
GET http://HOST:PORT/project

// Get project
GET http://HOST:PORT/project/:id

// Register project
BODY
{
  "project": "web"
}

POST http://HOST:PORT/project/create
```

### Technologies

```javascript
// Get all technologies
GET http://HOST:PORT/technologie

// Get technologies
GET http://HOST:PORT/technologie/:id

// Register technologie
BODY
{
  "technologie":"api"
}

POST http://HOST:PORT/technologie/create

```

### Project Technologies

```javascript
// Get projects details
GET http://HOST:PORT/project/detail/all

// Get project details
GET http://HOST:PORT/project/detail/:id

// Register project detail
BODY
{
  "projectId":1,
  "technologiesId":1
}

POST http://HOST:PORT/project/detail/create

```

### Get data for the graph

```javascript
GET http://HOST:PORT/project/graph/data

```

After registering the data of the projects and their technologies,
you could see something like this:

![image](https://i.ibb.co/rm87f9h/dependencies-sample.png)

# Made with

- https://d3js.org/
- Nodejs & Express

## Contributors

<table>
  <tbody>
    <td>
      <img src="https://avatars0.githubusercontent.com/u/3322836?s=460&v=4" width="100px;"/>
      <br />
      <label><a href="http://jrichardsz.github.io/">JRichardsz</a></label>
      <br />
    </td>  
    <td>
      <img src="https://avatars.githubusercontent.com/u/55628495?v=4" width="100px;"/>
      <br />
      <label><a href="https://aj-derteano.github.io/">AJ Derteano</a></label>
      <br />
    </td>
  </tbody>
</table>

# License

MIT
