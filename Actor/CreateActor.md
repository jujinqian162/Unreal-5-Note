# CreateActor
## 创建actor
![Alt text](image.png)
## include 组件
```cpp
#include "Components/SceneComponent.h"
#include "Components/StaticMeshComponent.h"
#include "Components/BoxComponent.h"
#include "Particles/ParticleSystemComponent.h"
#include "Components/AudioComponent.h"
```

## 添加组件
```cpp

	UPROPERTY(VisibleAnywhere, BlueprintReadOnly, Category = "MyComponent")
	class USceneComponent* MyScene;

	UPROPERTY(VisibleAnywhere, BlueprintReadOnly, Category = "MyComponent")
	class UStaticMeshComponent* MyMesh;

	UPROPERTY(VisibleAnywhere, BlueprintReadOnly, Category = "MyComponent")
	class UBoxComponent* MyBox;

	UPROPERTY(VisibleAnywhere, BlueprintReadOnly, Category = "MyComponent")
	class UParticleSystemComponent* MyParticle;
```