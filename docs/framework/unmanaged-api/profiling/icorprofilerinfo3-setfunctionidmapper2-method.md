---
title: Metodo ICorProfilerInfo3::SetFunctionIDMapper2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 723cb277a7df592e0494505018f7422e4e40f5f6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496152"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a>Metodo ICorProfilerInfo3::SetFunctionIDMapper2
Specifica la funzione implementata dal profiler che verrà chiamata per trasformare i valori `FunctionID` in valori alternativi, che vengono passati agli hook di ingresso/uscita delle funzioni del profiler. Questo metodo estende il metodo [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) con un parametro di dati aggiuntivo, che i profiler possono usare per evitare ambiguità tra i Runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a>Parametri  
 `pFunc`  
 in Puntatore a un'implementazione di [FunctionIDMapper2](functionidmapper2-function.md) che verrà chiamata per eseguire il mapping dei `FunctionID` valori ai valori alternativi.  
  
 `clientData`  
 in Puntatore passato a ogni chiamata di funzione [FunctionIDMapper2](functionidmapper2-function.md) effettuata dal runtime corrente. Il profiler può usare queste informazioni per distinguere tra Runtime.  
  
## <a name="return-value"></a>Valore restituito  
  
## <a name="remarks"></a>Osservazioni  
 Le alternative per i valori FunctionID verranno passate agli hook di ingresso/uscita della funzione del profiler ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md); oppure [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)) specificati dal metodo [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) o [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) .  
  
 Il `FunctionIDMapper2` metodo può essere impostato una sola volta. è consigliabile impostarlo nel callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [Interfaccia ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
