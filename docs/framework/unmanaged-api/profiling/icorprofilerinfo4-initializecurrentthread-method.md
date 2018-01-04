---
title: Metodo ICorProfilerInfo4::InitializeCurrentThread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4::InitializeCurrentThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f3c261068b38861dca2633a490e46d9f44371d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>Metodo ICorProfilerInfo4::InitializeCurrentThread
Inizializza il thread corrente prima di installare il profiler successive chiamate API sullo stesso thread, pertanto è possibile evitare il deadlock.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Note  
 Si consiglia di chiamare `InitializeCurrentThread` in qualsiasi thread che chiama un profiler API mentre vi sono sospese thread. Questo metodo viene in genere utilizzato per i profiler di campionamento che crea i propri thread di chiamare il [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) metodo eseguire dello stack viene illustrato quando viene sospeso il thread di destinazione. Chiamando `InitializeCurrentThread` dopo quando il profiler crea innanzitutto il thread di campionamento, i profiler possono garantire che l'inizializzazione differita per singoli thread eseguite durante la prima chiamata a CLR `DoStackSnapshot` può ora avvenire in modo sicuro quando nessun altro thread è sospeso.  
  
> [!NOTE]
>  `InitializeCurrentThread`esegue l'inizializzazione in anticipo per completare le attività accettano i blocchi e possono causare un deadlock. Chiamare `InitializeCurrentThread` solo quando non sono presenti thread sospesi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
