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
ms.openlocfilehash: 13ce44c9c7a04b870278bc8926dd9fe5daf10bc3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500013"
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
 in ID della funzione in cui `calleeId` verrà inserita la funzione.  
  
 `calleeId`  
 in ID della funzione da inserire.  
  
 `pfShouldInline`  
 [out] `true` per consentire l'inserimento; in caso contrario, `false` .  
  
## <a name="remarks"></a>Osservazioni  
 Il profiler può impostare `pfShouldInline` su `false` per impedire che la `calleeId` funzione venga inserita nella `callerId` funzione. Inoltre, il profiler può disabilitare globalmente l'inserimento inline usando il valore COR_PRF_DISABLE_INLINING dell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .  
  
 Le funzioni inserite inline non generano eventi per l'immissione o la uscita. Il profiler deve pertanto impostare `pfShouldInline` su per `false` produrre un grafico chiamate accurato. `pfShouldInline`L'impostazione di su `false` influirà sulle prestazioni, perché l'inserimento inline aumenta in genere la velocità e riduce il numero di eventi di compilazione JIT distinti per il metodo inserito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
