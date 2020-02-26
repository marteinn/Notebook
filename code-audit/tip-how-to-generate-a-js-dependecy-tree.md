# How to generate a frontend/react dependecy treee

1. Install required packages

```
brew install wget
brew install graphviz
npm i -g dependency-cruiser
```

2. Generate tree
```
depcruise --exclude "^node_modules" --output-type dot src | dot -T svg > dependencygraph.svg
```


- [Ref](https://medium.com/javascript-scene/setting-up-a-new-macbook-for-javascript-development-289df3f8f9)
