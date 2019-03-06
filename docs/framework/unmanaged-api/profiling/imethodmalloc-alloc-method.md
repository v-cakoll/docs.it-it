---
title: Metodo IMethodMalloc::Alloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a676989bdc6866f85fabe3e15b1e6b7b8b5a9a9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351255"
---
# <a name="imethodmallocalloc-method"></a>Metodo IMethodMalloc::Alloc

Tenta di allocare una quantità di memoria specificata per un nuovo corpo di funzione Microsoft intermediate language (MSIL).

## <a name="syntax"></a>Sintassi

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a>Parametri

`cb`\
[in] Il numero di byte da allocare per il corpo del metodo.

## <a name="remarks"></a>Note

 La memoria allocata inizierà con un indirizzo maggiore l'indirizzo di base del modulo che è associato questo allocatore. In altre parole, ogni allocatore viene creato per un modulo specifico e tenterà di allocare memoria in corrispondenza di un offset positivi dal relativo indirizzo di base. Se `Alloc` non riesce ad allocare il numero richiesto di byte in corrispondenza di un indirizzo maggiore l'indirizzo di base del modulo, viene restituito E_OUTOFMEMORY, indipendentemente dalla quantità effettiva di spazio di memoria disponibile.

 Il `Alloc` metodo deve essere usato in combinazione con il [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) (metodo).

## <a name="requirements"></a>Requisiti
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Intestazione:** CorProf.idl, CorProf.h

 **Libreria:** CorGuids.lib

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia IMethodMalloc](imethodmalloc-interface.md)