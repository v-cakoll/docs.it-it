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
ms.openlocfilehash: 2357e5348192db5d41adfe1176300359440aeee3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866728"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a>Metodo ICorProfilerAssemblyReferenceProvider::AddAssemblyReference
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Informa il Common Language Runtime (CLR) di un riferimento a un assembly che il Profiler prevede di aggiungere nel callback [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a>Parametri

- `pAssemblyRefInfo`

  Puntatore a una struttura [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) che fornisce a CLR informazioni su un riferimento a un assembly che deve considerare quando esegue un percorso di chiusura del riferimento all'assembly.
  
## <a name="remarks"></a>Note  
 Il profiler chiama questo metodo per ogni assembly di destinazione a cui fa riferimento l'assembly specificato nell'argomento `wszAssemblyPath` del callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) . L'oggetto interfaccia [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) viene passato al callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) del profiler, insieme al percorso e al nome dell'assembly nell'argomento `wszAssemblyPath`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md)
- [Metodo GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md)
- [Metodo ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)
