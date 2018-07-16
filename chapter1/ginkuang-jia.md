# Swagger接口

```
# go get github.com/swaggo/swag/cmd/swag
```

### 相关位置增加备注

### main入口函数

```
// @title  Dongjing Server api
// @version 2.0
// @description Dongjing server
// @termsOfService https://github.com/GACHAIN

func main() {}
```

### 相关控制器增加说明

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

### 项目目录下执行下面命令

```
# swag init
```

### 添加相关包

```
# govendor fetch github.com/swaggo/gin-swagger
# govendor fetch github.com/swaggo/gin-swagger/swaggerFiles
```

## 



