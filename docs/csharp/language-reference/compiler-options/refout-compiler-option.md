---
title: -refout (opzioni del compilatore C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: f48316a1e6f657e3bd0190d269dfe0e875a833d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72771764"
---
# <a name="-refout-c-compiler-options"></a>-refout (opzioni del compilatore C#)

L'opzione **-refout** specifica un percorso file in cui l'assembly di riferimento deve essere restituito come output. Ciò si converte in `metadataPeStream` nell'API Emit. Questa opzione corrisponde alla proprietà del progetto [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) di MSBuild.

## <a name="syntax"></a>Sintassi

```console
-refout:filepath
```

## <a name="arguments"></a>Argomenti

 `filepath` Il percorso del file dell'assembly di riferimento. In genere corrisponde a quello dell'assembly primario. La convenzione consigliata (usata da MSBuild) consiste nell'inserire l'assembly di riferimento in una sottocartella "ref /" relativa all'assembly primario.

## <a name="remarks"></a>Osservazioni

Gli assembly di riferimento sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie API pubblica della libreria. Includono dichiarazioni per tutti i membri che sono significative quando si fa riferimento a un assembly negli strumenti di compilazione, ma escludono tutte le implementazioni dei membri e le dichiarazioni di membri privati che non hanno alcun impatto osservabile sul contratto API. Per altre informazioni, vedere Assembly di [riferimento](../../../standard/assembly/reference-assemblies.md) nella Guida di .NET.

Le `-refout` [`-refonly`](refonly-compiler-option.md) opzioni e si escludono a vicenda.

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
