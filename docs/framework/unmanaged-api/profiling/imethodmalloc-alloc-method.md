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
ms.openlocfilehash: a82a2150f32b1b335da083ca235ed9d2966a0b6e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494202"
---
# <a name="imethodmallocalloc-method"></a>Metodo IMethodMalloc::Alloc

Tenta di allocare una quantità specificata di memoria per un nuovo corpo della funzione MSIL (Microsoft Intermediate Language).

## <a name="syntax"></a>Sintassi

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a>Parametri

`cb`\
in Numero di byte da allocare per il corpo del metodo.

## <a name="remarks"></a>Osservazioni

 La memoria allocata inizierà in corrispondenza di un indirizzo maggiore dell'indirizzo di base del modulo associato a questo allocatore. In altre parole, ogni allocatore viene creato per un particolare modulo e tenterà di allocare memoria a un offset positivo dal relativo indirizzo di base. Se `Alloc` non riesce ad allocare il numero richiesto di byte in un indirizzo maggiore dell'indirizzo di base del modulo, restituisce E_OUTOFMEMORY, indipendentemente dalla quantità effettiva di spazio di memoria disponibile.

 Il `Alloc` metodo deve essere usato in combinazione con il metodo [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) .

## <a name="requirements"></a>Requisiti
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

 **Intestazione:** CorProf.idl, CorProf.h

 **Libreria:** CorGuids.lib

 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia IMethodMalloc](imethodmalloc-interface.md)
