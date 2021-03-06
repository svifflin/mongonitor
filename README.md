<p align="center"><img src="https://github.com/cemkiy/mongonitor/blob/main/gopher.png" width="250"></p>
<p align="center">
  <a href="https://img.shields.io/badge/version-1.0.0-green.svg"><img src="https://img.shields.io/badge/version-1.0.0-green.svg"></a>
  <a href="https://github.com/cemkiy/mongonitor/actions"><img src="https://github.com/cemkiy/mongonitor/workflows/Go/badge.svg?branch=main"></a>
  <a href=""><img src="https://badgen.net/dependabot/cemkiy/mongonitor?icon=dependabot" alt="depandabot"></a>
</p>

# mongonitor
Mongo db basic monitor tool for golang package.

outputs;

- query
- db
- cluster info
- request id
- milliseconds
- filter
- limit
- sort by
- pipeline for aggregate

### install

```go
go get github.com/cemkiy/mongonitor
```

### mongo package

[![mongodb/mongo-go-driver - GitHub](https://gh-card.dev/repos/mongodb/mongo-go-driver.svg)](https://github.com/mongodb/mongo-go-driver)

### additional info for mongo go driver
Check the godoc link.
[event#CommandMonitor in mongo-go-driver](https://pkg.go.dev/go.mongodb.org/mongo-driver@v1.4.4/event#CommandMonitor)

## usage
```go
// Set client options
clientOptions := options.Client().ApplyURI("mongodb://localhost:27017").
  SetMonitor(mongonitor.NewMongonitor())

// use with newrelic
// nrMon := nrmongo.NewCommandMonitor(mongonitor.NewMongonitor())
// clientOptions := options.Client().ApplyURI("mongodb://localhost:27017").SetMonitor(nrMon)

// Connect to MongoDB
client, err := mongo.Connect(context.TODO(), clientOptions)

if err != nil {
    log.Fatal(err)
}

// Check the connection
err = client.Ping(context.TODO(), nil)

if err != nil {
    log.Fatal(err)
}

fmt.Println("Connected to MongoDB!")
```

### output
<a href="url"><img src="https://raw.githubusercontent.com/cemkiy/mongonitor/main/mongonitor.png"></a>
