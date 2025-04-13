# Experimental UseFile
The intent of this project is to stress test the API with prototype apps. When the API feels good, we'll turn it into contracts so it can work with many backends.

This version only supports IndexedDB as a backend.

## Usage
First we create the composable:
```ts
import { useFile } from 'use-file'

const fileService = useFile()
```

Then, we can use it to both store, and retrieve the file.

Storing the file:
```ts
fileService.store(someFile)
```

We then have access to everything we need
```ts
fileService.storing.value
fileService.id.value // You may need this later!
fileService.url.value
fileService.download()
fileService.name.value
fileService.type.value
```

Of course, we can also retrieve a previously stored file. This is done with the same composable using `id`
```ts
fileService.id.value = 'your-file-id'
```

## Todo
- [ ] callbacks
- [ ] setting id programatically (e.g. `get('some-id')`). This means we can await loading of the file