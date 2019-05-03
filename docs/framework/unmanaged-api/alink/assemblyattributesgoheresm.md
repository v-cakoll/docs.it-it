---
title: Classe AssemblyAttributesGoHereSM (CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereSM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01b156ed9c318e71a408ea10f2744911a85faedc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790338"
---
# <a name="assemblyattributesgoheresm-class"></a>Classe AssemblyAttributesGoHereSM

Usato da ALink come segnaposto per archiviare le informazioni sugli attributi personalizzati.

## <a name="syntax"></a>Sintassi

```csharp
internal sealed class AssemblyAttributesGoHereSM
```

## <a name="remarks"></a>Note

I riferimenti a questo tipo potrebbero essere incorporati in netmodule le cui origini contengono attributi personalizzati dell'assembly. Quando compila un manifesto di assembly da uno o più netmodule contenenti riferimenti a questi tipi, ALink usa le informazioni associate a tali riferimenti per generare i veri attributi personalizzati. Per questo tipo non viene pertanto mai creata un'istanza e i riferimenti a esso relativi vengono usati solo come parte del processo di compilazione e non hanno alcun ruolo nell'assembly finale.

I riferimenti a questo tipo indicano gli attributi personalizzati che sono correlati alla sicurezza e sono multiuso.

Questi tipi sono contrassegnati come "interni" all'interno di .NET Framework e si trovano nel <xref:System.Runtime.CompilerServices> dello spazio dei nomi.

## <a name="requirements"></a>Requisiti

mscorlib.dll

## <a name="see-also"></a>Vedere anche

- [AssemblyAttributesGoHere](assemblyattributesgohere.md)
- [AssemblyAttributesGoHereM](assemblyattributesgoherem.md)
- [AssemblyAttributesGoHereS](assemblyattributesgoheres.md)
