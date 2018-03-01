---
title: Metodo IMethodMalloc::Alloc
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26998e8b2e8648b4fb175f188540e7bc33c580c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
