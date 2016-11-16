# JSON - Snippets

### Prettyprint json string

`echo '{"foo": "lorem", "bar": "ipsum"}' | python -m json.tool`

[Source](http://stackoverflow.com/a/1920585)

### Prettyprint json file

`python -m json.tool my_json.json`

[Source](http://stackoverflow.com/a/1920585)

### Prettyprint external file

`curl http://my_url/ | python -m json.tool`

[Source](http://stackoverflow.com/a/1920585)
