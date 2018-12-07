# igroot-help README

使用 igroot 业务组件时的代码提示

## Features

```js
// 输入 login，会从 sso-login 中引入 withLogin 高阶组件
// 代码将替换为以下：
import { withLogin } from 'sso-login'

// 输入 token， 从 sso-login 中引入 handleTokenInvalid
// 代码将替换为以下：
import { handleTokenInvalid } from 'sso-login'

// 输入 logout， 从 sso-login 中引入 logout 和 handleTokenInvalid
// 代码将替换为以下：
import { logout,handleTokenInvalid } from 'sso-login'

// 输入 il, 引入 igroot-frame-layout 组件
// 代码将替换为以下：
import BaseLayout from 'igroot-frame-layout'

// 输入 layout, 使用 BaseLayout 组件
// 代码将替换为以下：
<BaseLayout
  apiDomain=''
  appName=''>

</BaseLayout>

// 输入 fetch, 引入fetch，并定义
// 代码将替换为以下：
import igrootFetch from 'igroot-fetch'
const graphQLApi = igrootFetch(domain+'/graphql',{
  handleErrors: ({ code, msg }) => {
    if (code == '44') {
      handleTokenInvalid(domain)
      return
    }
    if (code != 0) {
      message.error(msg)
    }
  },
  handleHttpErrors: (response) => {
    notification.error({
      message: 'Http Error',
      description: response.statusText
    })
  }
})
```

## Release Notes

### 1.0.0

第一个可用版本


**Enjoy!**
