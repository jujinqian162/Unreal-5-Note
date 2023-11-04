# Main Methods
## Create Actor

### CreateDefaultSubobject<>
```cpp
    /**
    * param FString 组件名称
    * return 指向ComponentType的指针
    */
    CreateDefaultSubobject<ComponentType>(FString componentName);
```

### SetupAttachment
```cpp
    /**
    * param 要绑定的父组件
    */
    YourComponentPtr->SetupAttachment(RootComponent);
```
