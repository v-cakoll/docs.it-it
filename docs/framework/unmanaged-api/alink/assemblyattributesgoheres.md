---
title: AssemblyAttributesGoHereS
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereS
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereS
helpviewer_keywords:
- AssemblyAttributesGoHereS type
- Alink API, AssemblyAttributesGoHereS type
ms.assetid: 4e817f35-a2bc-4403-9e6f-f731e6b9fe23
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 135938c4ed91423145ca46b743620f4236f7f818
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742252"
---
# <a name="assemblyattributesgoheres"></a>AssemblyAttributesGoHereS

Usato da ALink come segnaposto per archiviare le informazioni sugli attributi personalizzati.

## <a name="syntax"></a>Sintassi

```csharp
internal sealed class AssemblyAttributesGoHereS
```

## <a name="remarks"></a>Note

I riferimenti a questo tipo potrebbero essere incorporati in netmodule le cui origini contengono attributi personalizzati dell'assembly. Quando compila un manifesto di assembly da uno o più netmodule contenenti riferimenti a questi tipi, ALink usa le informazioni associate a tali riferimenti per generare i veri attributi personalizzati. Per questo tipo non viene pertanto mai creata un'istanza e i riferimenti a esso relativi vengono usati solo come parte del processo di compilazione e non hanno alcun ruolo nell'assembly finale.

I riferimenti a questo tipo indicano gli attributi personalizzati che sono correlati alla sicurezza e non sono multiuso.

Questi tipi sono contrassegnati come "interni" all'interno di .NET Framework e si trovano nel <xref:System.Runtime.CompilerServices> dello spazio dei nomi.

## <a name="requirements"></a>Requisiti

mscorlib.dll

## <a name="see-also"></a>Vedere anche

- [AssemblyAttributesGoHere](assemblyattributesgohere.md)
- [AssemblyAttributesGoHereM](assemblyattributesgoherem.md)
- [AssemblyAttributesGoHereSM](assemblyattributesgoheresm.md)
