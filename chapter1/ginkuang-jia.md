# Swagger接口

```
# go get github.com/swaggo/swag/cmd/swag
```

```
// @title  Dongjing Server api
// @version 2.0
// @description Dongjing server
// @termsOfService https://github.com/GACHAIN

func main() {}
```

```
// @Description 用户登录
// @Summary 登录
// @Accept  json
// @Produce  json
// @Param name query string true "用户名"
// @Param password query string true "密码"
// @Success 200 {string} json "{"code":200,"data":{},"message":"ok"}"
// @Router /login [post]
func Login(c *gin.Context) {}
```



