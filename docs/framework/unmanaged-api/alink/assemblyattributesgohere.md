---
title: Classe AssemblyAttributesGoHere (CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHere
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHere
helpviewer_keywords:
- AssemblyAttributesGoHere type
- Alink API, AssemblyAttributesGoHere type
ms.assetid: 7b26fcb6-94f4-4f09-933e-b33efe451f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 571c2f6723e827a1b385f77724c33703ae970ae3
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968114"
---
# <a name="assemblyattributesgohere-class"></a>Classe AssemblyAttributesGoHere

Usato da ALink come segnaposto per archiviare le informazioni sugli attributi personalizzati.

## <a name="syntax"></a>Sintassi

```csharp
internal sealed class AssemblyAttributesGoHere
```

## <a name="remarks"></a>Note

I riferimenti a questo tipo potrebbero essere incorporati in netmodule le cui origini contengono attributi personalizzati dell'assembly. Quando compila un manifesto di assembly da uno o più netmodule contenenti riferimenti a questi tipi, ALink usa le informazioni associate a tali riferimenti per generare i veri attributi personalizzati. Per questo tipo non viene pertanto mai creata un'istanza e i riferimenti a esso relativi vengono usati solo come parte del processo di compilazione e non hanno alcun ruolo nell'assembly finale.

I riferimenti a questo tipo indicano gli attributi personalizzati che non sono correlati alla sicurezza e non sono multiuso.

Questi tipi sono contrassegnati come "interni" all'interno di .NET Framework e si trovano nel <xref:System.Runtime.CompilerServices> dello spazio dei nomi.

## <a name="requirements"></a>Requisiti

mscorlib.dll

## <a name="see-also"></a>Vedere anche

- [AssemblyAttributesGoHereM](assemblyattributesgoherem.md)
- [AssemblyAttributesGoHereS](assemblyattributesgoheres.md)
- [AssemblyAttributesGoHereSM](assemblyattributesgoheresm.md)
