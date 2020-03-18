---
title: -refonly (opzioni del compilatore C#)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: 856b65d3b2217dbe5d53ecda00723b47247d80a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72773857"
---
# <a name="-refonly-c-compiler-options"></a>-refonly (opzioni del compilatore C#)

L'opzione **-refonly** indica che l'output primario deve essere un assembly di riferimento, anziché un assembly di implementazione. Il parametro `-refonly` disabilita automaticamente l'output dei file PDB poiché non è possibile eseguire gli assembly di riferimento. Questa opzione corrisponde alla proprietà del progetto [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) di MSBuild.

## <a name="syntax"></a>Sintassi

```console
-refonly
```

## <a name="remarks"></a>Osservazioni

Gli assembly di riferimento sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie API pubblica della libreria. Includono dichiarazioni per tutti i membri che sono significative quando si fa riferimento a un assembly negli strumenti di compilazione, ma escludono tutte le implementazioni dei membri e le dichiarazioni di membri privati che non hanno alcun impatto osservabile sul contratto API. Per altre informazioni, vedere Assembly di [riferimento](../../../standard/assembly/reference-assemblies.md) nella Guida di .NET.

Le `-refonly` [`-refout`](refout-compiler-option.md) opzioni e si escludono a vicenda.

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
