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
ms.openlocfilehash: 844ac2a8aad4ce2cc6f70de2d5a53c7c0b6f4f6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453144"
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
  
#### <a name="parameters"></a>Parametri  
 `callerId`  
 [in] L'ID della funzione in cui il `calleeId` funzione verrà inserita.  
  
 `calleeId`  
 [in] L'ID della funzione da inserire.  
  
 `pfShouldInline`  
 [out] `true` per consentire l'inserimento; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Il profiler può impostare `pfShouldInline` a `false` per impedire la `calleeId` funzione vengono inseriti il `callerId` (funzione). Inoltre, il profiler può disabilitare globalmente inserimento in linea con il valore COR_PRF_DISABLE_INLINING il [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione.  
  
 Le funzioni inserite inline non genera eventi per entra o esce dalla. Pertanto, il profiler deve impostare `pfShouldInline` a `false` per produrre un grafico chiamate accurato. Impostazione `pfShouldInline` a `false` influirà sulle prestazioni, perché l'inserimento di inline in genere aumenta la velocità e riduce il numero di eventi di compilazione JIT distinti per il metodo inserito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
