:::NEW_COMMAND:::
UPLOAD_PUBLIC
```js
import { Storage } from "@aws-amplify/storage"

await Storage.put("test.txt", "Hello");
```
:::NEW_COMMAND:::
UPLOAD_PROTECTED
```js
import { Storage } from "@aws-amplify/storage"

await Storage.put('test.txt', 'Protected Content', {
    level: 'protected',
    contentType: 'text/plain'
});
```
:::NEW_COMMAND:::
UPLOAD_PRIVATE
```js
import { Storage } from "@aws-amplify/storage"

await Storage.put('test.txt', 'Private Content', {
    level: 'private',
    contentType: 'text/plain'
});
```
:::NEW_COMMAND:::
DOWNLOAD_PUBLIC
```js
import { Storage } from "@aws-amplify/storage"

await Storage.get('test.txt', { 
    level: 'public'
});
```
:::NEW_COMMAND:::
DOWNLOAD_PROTECTED
```js
import { Storage } from "@aws-amplify/storage"

await Storage.get('test.txt', { 
    level: 'protected'
    identityId: 'xxxxxxx' // The identityId of that user. Omit to get current user's objects.
});
```
:::NEW_COMMAND:::
DOWNLOAD_PRIVATE
```js
import { Storage } from "@aws-amplify/storage"

await Storage.get('test.txt', { 
    level: 'private'
});
```
:::NEW_COMMAND:::
LIST_PUBLIC
```js
import { Storage } from "@aws-amplify/storage"

Storage.list('photos/') // for listing ALL files without prefix, pass '' instead
        .then(result => console.log(result))
        .catch(err => console.log(err));
```
:::NEW_COMMAND:::
LIST_PROTECTED
```js
import { Storage } from "@aws-amplify/storage"

Storage.list('photos/', { 
        level: 'protected', 
        identityId: 'xxxxxxx' // The identityId of that user. Omit to get current user's objects.
    })
    .then(result => console.log(result))
    .catch(err => console.log(err));
```
:::NEW_COMMAND:::
LIST_PRIVATE
```js
import { Storage } from "@aws-amplify/storage"

Storage.list('photos/', { level: 'private' })
        .then(result => console.log(result))
        .catch(err => console.log(err));
```
:::NEW_COMMAND:::
REMOVE_PUBLIC
```js
import { Storage } from "@aws-amplify/storage"

await Storage.remove('test.txt');
```
:::NEW_COMMAND:::
REMOVE_PROTECTED
```js
import { Storage } from "@aws-amplify/storage"

await Storage.remove('test.txt', { level: 'protected' });
```
:::NEW_COMMAND:::
REMOVE_PRIVATE
```js
import { Storage } from "@aws-amplify/storage"

await Storage.remove('test.txt', { level: 'private' });
```