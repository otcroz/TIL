#### import 구문에서 중괄호 사용하는 이유

```
import React from 'react';
import { withRouter } from 'react-router-dom';
imoprt MakeComponent from './MakeComponent';
```
```
export default React;
'''
export withRouter;
```

- export default로 선언된 변수/메서드는 중괄호({})없이 호출 + 변수명이 달라도 되고,
- export로 선언된 변수/메서드는 중괄호 필수로 호출 + 변수명이 같아야 된다.


#### 참고문헌
https://mesonia.tistory.com/135
