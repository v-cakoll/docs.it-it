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
ms.openlocfilehash: b52a0e7f993629c1005883723c734996d75300a7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868434"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>Metodo ICorProfilerInfo4::InitializeCurrentThread
Inizializza il thread corrente prima delle chiamate API del profiler successive sullo stesso thread, in modo che il deadlock possa essere evitato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Note  
 Si consiglia di chiamare `InitializeCurrentThread` su qualsiasi thread che chiamerà un'API del profiler mentre sono presenti thread sospesi. Questo metodo viene in genere usato dai profiler di campionamento che creano il proprio thread per chiamare il metodo [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) per eseguire i percorsi dello stack mentre il thread di destinazione è sospeso. Chiamando `InitializeCurrentThread` una volta quando il profiler crea prima il thread di campionamento, i profiler possono garantire che l'inizializzazione differita per thread che CLR verrebbe eseguita durante la prima chiamata a `DoStackSnapshot` ora possa essere eseguita in modo sicuro quando nessun altro thread viene sospeso.  
  
> [!NOTE]
> `InitializeCurrentThread` esegue l'inizializzazione in anticipo per completare le attività che accettano blocchi ed è possibile che si verifichi un deadlock. Chiamare `InitializeCurrentThread` solo quando non sono presenti thread sospesi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo4](icorprofilerinfo4-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
