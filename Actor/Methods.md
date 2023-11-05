# Main Methods
## Create Actor

### 创建组件
```cpp
    /**
    * param FString 组件名称
    * return 指向ComponentType的指针
    */
    CreateDefaultSubobject<ComponentType>(FString componentName);
```

### 绑定到父组件
```cpp
    /**
    * param 要绑定的父组件
    */
    YourComponentPtr->SetupAttachment(RootComponent);
```
### 设置静态资源方法
```cpp
    //加载temp静态资源
    static ConstructorHelpers::FObjectFinder<objectType>
    temp(TEXT("referenceAddress"));

    //将资源设置到组件上
    Mesh->SetStaticMesh(mesh.object);
    Particle->SetTemplate(particle.object);
    Audio->SetSound(audio.object)

```

### 设置静态类方法
```cpp
    //已知有一个	
    //UPROPERTY(VisibleAnywhere, BlueprintReadOnly, Category = "MyActor")
	//TSubclassOf<AActor> mActor;

    static ConstructorHelpers::FClassFinder<AActor>     TempStaticAActor(TEXT("YourReferenceAddress_C'"));
mActor = TempStaticAActor.Class;
    // 注意！：在复制的引用地址最后加上"_C"
    // 否则无法通过编译
```
### 对继承至AActor的类设置位置旋转缩放
```cpp
	SetActorLocation(FVector mLocation);
	SetActorRotation(FRotator mRotation);
	SetActorScale3D(FVector mScale);
```