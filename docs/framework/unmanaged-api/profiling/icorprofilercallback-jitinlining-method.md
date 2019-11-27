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
ms.openlocfilehash: 62035d623d56f7521e0a599a13bc20778e3f18d1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449909"
---
# <a name="icorprofilercallbackjitinlining-method"></a>Metodo ICorProfilerCallback::JITInlining
Notifica al profiler che il compilatore just-in-time (JIT) sta per inserire una funzione in linea con un'altra funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a>Parametri  
 `callerId`  
 in ID della funzione in cui verrà inserita la funzione `calleeId`.  
  
 `calleeId`  
 in ID della funzione da inserire.  
  
 `pfShouldInline`  
 [out] `true` per consentire l'inserimento. in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Il profiler può impostare `pfShouldInline` su `false` per impedire l'inserimento della funzione `calleeId` nella funzione `callerId`. Inoltre, il profiler può disabilitare globalmente l'inserimento inline usando il valore COR_PRF_DISABLE_INLINING dell'enumerazione [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .  
  
 Le funzioni inserite inline non generano eventi per l'immissione o la uscita. Il profiler deve pertanto impostare `pfShouldInline` su `false` per produrre un grafico chiamate accurato. L'impostazione di `pfShouldInline` su `false` influirà sulle prestazioni, perché l'inserimento inline aumenta in genere la velocità e riduce il numero di eventi di compilazione JIT distinti per il metodo inserito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
