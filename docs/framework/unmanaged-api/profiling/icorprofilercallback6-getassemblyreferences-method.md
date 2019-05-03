---
title: Metodo ICorProfilerCallback6::GetAssemblyReferences
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5296fbab71c67572718a58fedb9f89b064f816
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041496"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a>Metodo ICorProfilerCallback6::GetAssemblyReferences
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Indica al profiler che un assembly è in una fase iniziale di caricamento, quando Common Language Runtime esegue un percorso di chiusura del riferimento all'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszAssemblyPath`  
 [in] Percorso e nome dell'assembly i cui metadati verranno modificati.  
  
 `pAsmRefProvider`  
 [in] Un puntatore all'indirizzo di un [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) fa riferimento all'interfaccia che specifica l'assembly da aggiungere.  
  
## <a name="return-value"></a>Valore restituito  
 I valori restituiti da questo callback vengono ignorati.  
  
## <a name="remarks"></a>Note  
 Questo callback viene controllato impostando il [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) flag maschera eventi quando si chiama il [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) (metodo). Se il profiler si registra per la [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) metodo di callback, il runtime passa il percorso e il nome dell'assembly da caricare, insieme a un puntatore a un [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) oggetto di interfaccia di quel metodo. Il profiler può quindi chiamare il [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) metodo con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` oggetto per ogni assembly di destinazione a cui fare riferimento dall'assembly specificato nella `GetAssemblyReferences` callback.  
  
 Usare il callback `GetAssemblyReferences` solo se il profiler deve modificare i metadati di un assembly per aggiungere riferimenti. (Si noti che l'effettiva modifica dei metadati di un assembly viene eseguita nel [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)metodo di callback.) Il profiler deve implementare il metodo di callback `GetAssemblyReferences` per comunicare a Common Language Runtime (CLR) che i riferimenti ad assembly verranno aggiunti dopo il caricamento del form.  Questo garantisce che le decisioni di condivisione prese da CLR in questa fase iniziale restino valide anche se il profiler prevede di modificare i riferimenti all'assembly di metadati in un secondo momento.  In questo modo è possibile evitare alcune situazioni in cui le modifiche dei metadati del profiler provocano un errore `SECURITY_E_INCOMPATIBLE_SHARE`.  
  
 Il profiler Usa il [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) relativo oggetto fornito da questo metodo per aggiungere riferimenti ad assembly per il CLR assembly al walker di chiusura.  Il [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) oggetto deve essere usato solo dall'interno di questo callback. Le chiamate al [Icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) da questo callback (metodo) non comportare una modifica di metadati, ma solo in un percorso di chiusura del riferimento assembly modificato. Il profiler dovrà comunque usare un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) oggetto da aggiungere in modo esplicito i riferimenti ad assembly dall'interno di [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback per il tipo di riferimento assembly, anche se implementa il `GetAssemblyReferences` callback.  
  
 Il profiler deve essere preparato a ricevere chiamate duplicate a questo callback per lo stesso assembly e deve rispondere in modo identico per ogni chiamata duplicata (eseguendo lo stesso set di [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) chiamate).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)
- [Metodo ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
- [Interfaccia ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
