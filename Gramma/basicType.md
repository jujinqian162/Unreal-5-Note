# Basic Type

## 基本变量类型
```cpp
    	//基础变量类型
	bool bBool;
	int32 varInt32;
	int64 varInt64;
	BYTE varByte;
	FString varString; //可修改,但性能低
    FString s = TEXT("hello world"); //创建FString
	FName Name; //利用哈希值存储，查找性能高，不可修改
	FText varText; //给玩家显示用，本地化的 。 
     //注：FText 无法转换为FString
	FVector vector;
	FRotator Rotator;
	FTransform varTransform; //缩放旋转位置的集合类型；
```

## Unreal泛型容器
### TArray
```cpp
    TArray<int64> array;
    array.Add(10);
    array.Add(20);
    array.AddUnique(10); //array: [10,20]
    array.AddUnique(40); //array: [10,20,40]
    array.Remove(10); // 移除所有等值元素
    array.RemoveAt(0); // 移除对应索引的元素
    array.RemoveSingle(20); // 移除首次遇到的20的元素
    array.Empty(); // 清空元素
    array.Reset(); // 重置所有元素为0 
    array.Insert(60,0);// 在索引为0处插入元素60；
    array.Find(120); //找到为真
    // 迭代器
    auto iter = array.CreateConstIterator();
    ++iter; // 迭代器移动

```

## 基础数据类型的输出
```cpp
    bool mBool = false;
    int32 mInt = 2;
    FString mString = "hello";
    FVector mVector = FVector(0, 5, 1);
	UE_LOG(LogTemp, Warning, TEXT("mVector: %s"),*mVector.ToString());
	FVector mV = { 1,2,3 };
	UE_LOG(LogTemp, Warning, TEXT("mV: %s"),*mV.ToString());


```