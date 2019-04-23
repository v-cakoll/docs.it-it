---
title: Metodo ICorProfilerCallback::JITInlining
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60183291fda551e328ee1def03c02240314a71e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178269"
---
# <a name="icorprofilercallbackjitinlining-method"></a>Metodo ICorProfilerCallback::JITInlining
Notifica al profiler che il compilatore just-in-time (JIT) sta per inserire una funzione in linea con un'altra funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a>Parametri  
 `callerId`  
 [in] L'ID della funzione in cui il `calleeId` funzione verrà inserita.  
  
 `calleeId`  
 [in] L'ID della funzione deve essere inserito.  
  
 `pfShouldInline`  
 [out] `true` per consentire l'inserimento; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Il profiler può impostare `pfShouldInline` al `false` per impedire la `calleeId` funzione venga inserito nel `callerId` (funzione). Inoltre, il profiler a livello globale può disabilitare inserimento inline utilizzando il valore di COR_PRF_DISABLE_INLINING il [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione.  
  
 Inserire le funzioni inline non generano eventi per entra o esce dalla. Pertanto, il profiler deve impostare `pfShouldInline` a `false` per produrre un grafico chiamate accurato. L'impostazione `pfShouldInline` a `false` influirà sulle prestazioni, perché l'inserimento di inline è in genere aumenta la velocità e riduce il numero di eventi di compilazione JIT separati per il metodo inserito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
