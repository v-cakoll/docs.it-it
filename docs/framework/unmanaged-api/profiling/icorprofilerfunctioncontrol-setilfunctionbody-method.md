---
title: Metodo ICorProfilerFunctionControl::SetILFunctionBody
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
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 56d31b93385a087949121a76587ef6009cd9d51e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a>Metodo ICorProfilerFunctionControl::SetILFunctionBody
Sostituisce il corpo Common Intermediate Language (CIL) del metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cbNewILMethodHeader`  
 [in] Dimensioni totali del nuovo codice CIL, incluse l'intestazione e tutte strutture successive al corpo.  
  
 `pbNewILMethodHeader`  
 [in] Puntatore alla nuova intestazione CIL.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli HRESULT specifici seguenti.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Sostituzione completata correttamente.|  
  
## <a name="remarks"></a>Note  
 A differenza di [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) (metodo), il `SetILFunctionBody` metodo gestisce la memoria necessaria per il nuovo corpo CIL. Ciò significa che il corpo CIL fornito dal profiler non deve essere allocato tramite il [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interfaccia né allocato in un intervallo specifico. ma può essere allocato in qualsiasi heap. Il profiler può liberare la memoria usata per proprio corpo CIL dopo `SetILFunctionBody` restituisce.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
