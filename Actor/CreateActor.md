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

## 构造函数
```cpp
AMyActor::AMyActor()
{
 	// Set this actor to call Tick() every frame.  You can turn this off to improve performance if you don't need it.
	PrimaryActorTick.bCanEverTick = true;
	MyScene = CreateDefaultSubobject<USceneComponent>(TEXT("my Scene"));
	MyBox = CreateDefaultSubobject<UBoxComponent>(TEXT("my Box"));
	MyParticle = CreateDefaultSubobject<UParticleSystemComponent>(TEXT("my Particle"));
	MyMesh = CreateDefaultSubobject<UStaticMeshComponent>(TEXT("my Mesh"));

	RootComponent = MyScene;
	MyBox->SetupAttachment(RootComponent);
	MyParticle->SetupAttachment(RootComponent);
	MyMesh->SetupAttachment(RootComponent);

	//加载静态资源
	static ConstructorHelpers::FObjectFinder<UStaticMesh>	TempStaticMesh(TEXT("Your reference adress"));

	MyMesh->SetStaticMesh(TempStaticMesh.Object);


	static ConstructorHelpers::FObjectFinder<UParticleSystem>	TempStaticParticle(TEXT("Your reference adress"));

	MyParticle->SetTemplate(TempStaticParticle.Object);
}
```
右键资源：复制引用
![Alt text](image-1.png)