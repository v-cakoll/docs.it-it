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
ms.openlocfilehash: 0717ef5fdb6c0447ceeb801f239be08f8cca5988
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865051"
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
 in Puntatore all'indirizzo di un'interfaccia [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) che specifica i riferimenti ad assembly da aggiungere.  
  
## <a name="return-value"></a>Valore restituito  
 I valori restituiti da questo callback vengono ignorati.  
  
## <a name="remarks"></a>Note  
 Questo callback viene controllato impostando il flag della maschera di evento [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) quando si chiama il metodo [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) . Se il profiler viene registrato per il metodo di callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , il runtime passa il percorso e il nome dell'assembly da caricare, insieme a un puntatore a un oggetto di interfaccia [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) a tale metodo. Il profiler può quindi chiamare il metodo [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) con un oggetto `COR_PRF_ASSEMBLY_REFERENCE_INFO` per ogni assembly di destinazione a cui fa riferimento l'assembly specificato nel callback di `GetAssemblyReferences`.  
  
 Usare il callback `GetAssemblyReferences` solo se il profiler deve modificare i metadati di un assembly per aggiungere riferimenti. Si noti tuttavia che la modifica effettiva dei metadati di un assembly viene eseguita nel metodo di callback [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md). Il profiler deve implementare il metodo di callback `GetAssemblyReferences` per informare l'Common Language Runtime (CLR) che i riferimenti ad assembly verranno aggiunti quando il modulo è stato caricato.  Questo garantisce che le decisioni di condivisione prese da CLR in questa fase iniziale restino valide anche se il profiler prevede di modificare i riferimenti all'assembly di metadati in un secondo momento.  In questo modo è possibile evitare alcune situazioni in cui le modifiche dei metadati del profiler provocano un errore `SECURITY_E_INCOMPATIBLE_SHARE`.  
  
 Il profiler usa l'oggetto [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) fornito da questo metodo per aggiungere riferimenti ad assembly al Walker di chiusura del riferimento all'assembly CLR.  L'oggetto [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) deve essere utilizzato solo dall'interno di questo callback. Le chiamate al metodo [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) da questo callback non comportano la modifica dei metadati, ma solo in un percorso di chiusura del riferimento all'assembly modificato. Il profiler dovrà ancora usare un oggetto [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) per aggiungere in modo esplicito i riferimenti ad assembly dal callback [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) per l'assembly di riferimento, anche se implementa il callback `GetAssemblyReferences`.  
  
 Il profiler deve essere pronto a ricevere chiamate duplicate a questo callback per lo stesso assembly e deve rispondere in modo identico per ogni chiamata duplicata (effettuando lo stesso set di chiamate [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) ).  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback6](icorprofilercallback6-interface.md)
- [Metodo ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)
- [Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md)
- [Interfaccia ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md)
