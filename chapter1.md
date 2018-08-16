### Goland问题集锦

* could not launch process: EOF

```
go get -v  -u github.com/derekparker/delve/cmd/dlv
cd $GOPATH/src/github.com/derekparker/delve
make install
cp $GOPATH/bin/dlv /Applications/GoLand.app/Contents/plugins/intellij-go-plugin/lib/dlv/mac/
```



