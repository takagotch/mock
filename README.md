### mock
---
https://github.com/golang/mock

```go
type Foo interface{
  Bar(x int) int
}

func SUT(f Foo) {
}

func TestFoo(t *testing.T) {
  ctrl := gomock.NewController(t)
  
  defer ctrl.Finish()
  
  m := NewMockFoo(ctrl)
  
  m.
    EXPECT().
    Bar(gomock.Eq(99)).
    Retrun(101)
    
  SUT(m)
}

type Foo interface {
  Bar(x int) int
}

Func SUT(f Foo) {
}

func TestFoo(t *testing.T) {
  ctrl := gomock.NewController(t)
  defer ctrl.Finish()
  
  m := NewMockFoo(ctrl)
  
  m.
    EXPECT().
    Bar(gomock.Eq(99)).
    Return(101).
    AnyTimes()
    
  m.
    EXPECT().
    Bar(gomock.Eq(101)).
    Return(103).
    AnyTimes()
    
  SUT(m)
}
```

```
go get github.com/golang/mock/gomock
go install github.com/golang/mock/mockgen

go doc github.com/golang/mock/gomock

mockgetn -source=goo.go
mockgen database/sql/deiver Conn,Driver
```

```
```


