---
title: Metodo ICorProfilerAssemblyReferenceProvider::AddAssemblyReference
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
ms.openlocfilehash: 2325e3034dbf00441e587017affa65b80821fbb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128760"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a>Metodo ICorProfilerAssemblyReferenceProvider::AddAssemblyReference
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Informa il Common Language Runtime (CLR) di un riferimento a un assembly che il Profiler prevede di aggiungere nel callback [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a>Parametri  
 pAssemblyRefInfo  
 Puntatore a una struttura [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) che fornisce a CLR informazioni su un riferimento a un assembly che deve considerare quando esegue un percorso di chiusura del riferimento all'assembly.  
  
## <a name="remarks"></a>Note  
 Il profiler chiama questo metodo per ogni assembly di destinazione a cui fa riferimento l'assembly specificato nell'argomento `wszAssemblyPath` del callback [ICorProfilerCallback6:: GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) . L'oggetto interfaccia [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) viene passato al callback [ICorProfilerCallback6:: GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) del profiler, insieme al percorso e al nome dell'assembly nell'argomento `wszAssemblyPath`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
- [Metodo GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [Metodo ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
