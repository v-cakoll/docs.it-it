---
title: Interfaccia ICorProfilerAssemblyReferenceProvider
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
ms.openlocfilehash: 17fb3de830d1aed2214631bbe8254a7f58030025
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500520"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a>Interfaccia ICorProfilerAssemblyReferenceProvider
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Consente al profiler di informare il Common Language Runtime (CLR) dei riferimenti ad assembly che il profiler aggiungerà nel callback [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|Informa il CLR di un riferimento a un assembly che il Profiler prevede di aggiungere nel callback [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .|  
  
## <a name="remarks"></a>Osservazioni  
 CLR passa il profiler `ICorProfilerAssemblyReferenceProvider` a un oggetto di interfaccia nel callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) . Ciò consente al profiler di informare il CLR dei riferimenti ad assembly che il Profiler prevede di aggiungere in un secondo momento nel metodo [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md). . In questo modo viene migliorata la precisione del walker di chiusura dei riferimenti ad assembly di CLR e dei relativi algoritmi per determinare la possibilità di condivisione degli assembly.  
  
 Questa interfaccia può essere usata solo nel callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) che passa questo oggetto interfaccia al profiler.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
