---
title: Metodo ICorProfilerInfo4::InitializeCurrentThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
ms.openlocfilehash: 39882a554f9d47040bef00ff320d15b56abea533
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445718"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>Metodo ICorProfilerInfo4::InitializeCurrentThread
Inizializza il thread corrente prima delle chiamate API del profiler successive sullo stesso thread, in modo che il deadlock possa essere evitato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Note  
 Si consiglia di chiamare `InitializeCurrentThread` su qualsiasi thread che chiamerà un'API del profiler mentre sono presenti thread sospesi. Questo metodo viene in genere usato dai profiler di campionamento che creano il proprio thread per chiamare il metodo [ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) per eseguire i percorsi dello stack mentre il thread di destinazione è sospeso. Chiamando `InitializeCurrentThread` una volta quando il profiler crea prima il thread di campionamento, i profiler possono garantire che l'inizializzazione differita per thread che CLR verrebbe eseguita durante la prima chiamata a `DoStackSnapshot` ora possa essere eseguita in modo sicuro quando nessun altro thread viene sospeso.  
  
> [!NOTE]
> `InitializeCurrentThread` esegue l'inizializzazione in anticipo per completare le attività che accettano blocchi ed è possibile che si verifichi un deadlock. Chiamare `InitializeCurrentThread` solo quando non sono presenti thread sospesi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
