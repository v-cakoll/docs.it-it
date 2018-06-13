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
ms.openlocfilehash: 6d73fe16720248d541bac64a432bb6f35d6873b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454981"
---
# <a name="imethodmallocalloc-method"></a>Metodo IMethodMalloc::Alloc
Tenta di allocare una quantità specificata di memoria per un nuovo corpo della funzione Microsoft intermediate language (MSIL).  
  
## <a name="syntax"></a>Sintassi  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cb`  
 [in] Il numero di byte da allocare per il corpo del metodo.  
  
## <a name="remarks"></a>Note  
 La memoria allocata inizierà in corrispondenza di un indirizzo maggiore dell'indirizzo di base del modulo che è associato l'allocatore. In altre parole, ogni allocatore viene creato per un particolare modulo e tenterà di allocare memoria a un offset positivo dal relativo indirizzo di base. Se `Alloc` non riesce ad allocare il numero richiesto di byte in un indirizzo maggiore dell'indirizzo di base del modulo, restituisce E_OUTOFMEMORY, indipendentemente dalla quantità effettiva di spazio di memoria disponibile.  
  
 Il `Alloc` metodo deve essere utilizzato in combinazione con il [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
