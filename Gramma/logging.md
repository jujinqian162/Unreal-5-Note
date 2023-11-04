# Unreal 5 Logging gramma

## Log
```cpp
    // on 日志
    /** 
    *@para1 Log组别
    *@para2 Log级别(Warning,Error,Display)
    *@para3 FString 类型 
    */
	UE_LOG(LogTemp, Warning, TEXT("Hello World, this is the Begining"));

	UE_LOG(LogTemp, Error, TEXT("BeginPlay"));

    // on screen
    /**
    *@para1 Key -1表示默认
    *@para2 显示时长（秒）
    *@para3 颜色
    *@para4 在屏幕显示的内容
    */
    const uint64 mkey = -1;

	GEngine->AddOnScreenDebugMessage(mkey, 5.0f, FColor::Blue, TEXT("MY Name is Ju"));

	GEngine->AddOnScreenDebugMessage(mkey, 5.0f, FColor::Red, TEXT("Begin Play"));
```


