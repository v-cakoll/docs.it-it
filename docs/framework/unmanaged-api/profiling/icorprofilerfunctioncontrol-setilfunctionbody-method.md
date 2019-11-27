---
title: Metodo ICorProfilerFunctionControl::SetILFunctionBody
ms.date: 03/30/2017
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
ms.openlocfilehash: f6e2cfe47bdd212e39549544b06bf5b11033a956
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429880"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a>Metodo ICorProfilerFunctionControl::SetILFunctionBody
Sostituisce il corpo Common Intermediate Language (CIL) del metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Parametri  
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
 A differenza del metodo [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) , il metodo `SetILFunctionBody` gestisce la memoria necessaria per il nuovo corpo CIL. Ciò significa che il corpo del CIL fornito dal profiler non deve essere allocato tramite l'interfaccia [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) o allocato in un intervallo specifico. ma può essere allocato in qualsiasi heap. Il profiler può liberare la memoria usata per il corpo del CIL dopo che `SetILFunctionBody` restituito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
