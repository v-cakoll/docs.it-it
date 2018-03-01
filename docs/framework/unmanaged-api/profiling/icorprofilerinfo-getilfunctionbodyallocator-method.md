---
title: Metodo ICorProfilerInfo::GetILFunctionBodyAllocator
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
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1feec20f0ddc4f6029490e06d4729b3fdaa7fa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a>Metodo ICorProfilerInfo::GetILFunctionBodyAllocator
Ottiene un'interfaccia che fornisce un metodo per allocare memoria per essere utilizzato per scambiare il corpo di un metodo in codice Microsoft intermediate language (MSIL).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleId`  
 [in] L'ID del modulo in cui risiede il metodo.  
  
 `ppMalloc`  
 [out] Un puntatore a un [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interfaccia che fornisce un metodo per allocare la memoria.  
  
## <a name="remarks"></a>Note  
 Il corpo di un metodo in codice MSIL deve essere individuato come indirizzi virtuali relativi (RVA), rispetto al modulo caricato, che significa che segue il modulo all'interno di 4 GB. Per renderne più semplice per uno strumento di scambiare il corpo di un metodo, il `GetILFunctionBodyAllocator` metodo assicura che la memoria viene allocata all'interno dell'intervallo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
