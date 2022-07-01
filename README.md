## doak-curl

go 版本的 curl 对外请求库


### 项目介绍

*  使用 go 开发的对外请求库


### 使用方法

1. 下载

```go
go get -u github.com/deatil/doak-curl
```

2. 使用

```go
package main

import (
    "fmt"

    "github.com/deatil/doak-curl/curl"
)

func main() {
    client := curl.New(
        curl.WithBaseURI("http://yourdomain.com/api"),
        curl.WithTimeout(35),
        curl.WithResCharset("utf-8"),
    )

    resp, err := client.Get(
        "/get-data",
        curl.WithParams(map[string]any{
            "p": "123",
        }),
    )
    if err != nil {
        fmt.Println(err.Error())
        return
    }

    data, err2 := resp.GetContents()
    if err2 != nil {
        fmt.Println(err2.Error())
        return
    }

    fmt.Println(data)
}
```


### 开源协议

*  `doak-curl` 遵循 `Apache2` 开源协议发布，在保留本软件版权的情况下提供个人及商业免费使用。


### 版权

*  该系统所属版权归 deatil(https://github.com/deatil) 所有。
