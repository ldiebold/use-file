# Experimental UseFile
The intent of this project is to stress test a file API for Vue, with prototype apps. When the API feels good, we'll turn it into contracts so it can work with many backend.

This version only supports IndexedDB as a backend.

## Usage
First we create the composable:
```ts
import { useFile } from 'use-file'

const fileService = useFile()
```

Then, we can use it to both store, and retrieve a file.

### Storing: `store(file)`
```ts
fileService.store(file)
```

We now have access to everything we need
```ts
fileService.storing.value
fileService.id.value // You may need this later!
fileService.url.value
fileService.download()
fileService.name.value
fileService.type.value
```

### Retrieving: `id.value`
Of course, we can also retrieve a previously stored file. This is done with the same composable using the `id` ref
```ts
fileService.id.value = 'your-file-id'
```

## Todo
- [ ] callbacks
- [ ] setting id programatically (e.g. `get('some-id')`). This means we can await loading of the file