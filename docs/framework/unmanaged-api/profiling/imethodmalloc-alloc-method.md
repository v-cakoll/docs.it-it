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
ms.openlocfilehash: 54c38f9a9abc9a02ba4d84c9a41b2ef6b1f7cb69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528563"
---
# <a name="imethodmallocalloc-method"></a>Metodo IMethodMalloc::Alloc
Tenta di allocare una quantità di memoria specificata per un nuovo corpo di funzione Microsoft intermediate language (MSIL).  
  
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
 La memoria allocata inizierà con un indirizzo maggiore l'indirizzo di base del modulo che è associato questo allocatore. In altre parole, ogni allocatore viene creato per un modulo specifico e tenterà di allocare memoria in corrispondenza di un offset positivi dal relativo indirizzo di base. Se `Alloc` non riesce ad allocare il numero richiesto di byte in corrispondenza di un indirizzo maggiore l'indirizzo di base del modulo, viene restituito E_OUTOFMEMORY, indipendentemente dalla quantità effettiva di spazio di memoria disponibile.  
  
 Il `Alloc` metodo deve essere usato in combinazione con il [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
