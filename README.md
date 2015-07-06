# gin-glog
[Gin](https://github.com/gin-gonic/gin) middleware for Logging with
[glog](https://github.com/golang/glog). It is meant as drop in
replacement for the default logger used in gin.

[![Build Status](https://travis-ci.org/zalando-techmonkeys/gin-glog.svg?branch=master)](https://travis-ci.org/zalando-techmonkeys/gin-glog)

## Usage
### Example

Start your webapp to log to STDERR and /tmp:

    % ./webapp -log_dir="/tmp" -logtostderr -v=2

```go
package main

import (
    "flag
    "time"

    "github.com/golang/glog"
    "github.com/zalando-techmonkeys/gin-glog"
    "github.com/gin-gonic/gin"
)

func main() {
    flag.Parse()
    router := gin.New()
    router.Use(ginglog.Logger(3 * time.Second))
    //..
    router.Use(gin.Recovery())
    glog.Info("bootstrapped application")
    router.Run(":8080")
}
```
## Development
* Issues: Just create issues on github
* Enhancements/Bugfixes: Pull requests are welcome
* get in contact: mailto:team-techmonkeys@zalando.de
* see [MAINTAINERS](https://github.com/zalando-techmonkeys/gin-glog/blob/master/MAINTAINERS)
file.

## License
see [LICENSE](https://github.com/zalando-techmonkeys/gin-glog/blob/master/LICENSE) file.
