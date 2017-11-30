---
title: Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 000a338400efa0d70e690f585518304a8b525346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="corprfassemblyreferenceinfo-structure"></a>Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Fornisce Common Language Runtime con informazioni su un riferimento all'assembly che deve considerare quando esegue un percorso di chiusura del riferimento all'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|Un puntatore alla chiave pubblica o token dell'assembly.|  
|`cbPublicKeyOrToken`|Il numero di byte nella chiave pubblica o token.|  
|`szName`|Il nome dell'assembly al quale viene fatto riferimento.|  
|`pMetaData`|Un puntatore ai metadati dell'assembly.|  
|`pbHashValue`|Un puntatore a un oggetto binario hash di grandi dimensioni (BLOB).|  
|`cbHashValue`|Il numero di byte nel BLOB hash.|  
|`dwAssemblyRefFlags`|I flag dell'assembly.|  
  
## <a name="remarks"></a>Note  
 La struttura `COR_PRF_EX_CLAUSE_INFO` è popolata dal profiler quando dichiara altri riferimenti ad assembly che Common Language Runtime deve considerare quando esegue un percorso di chiusura del riferimento all'assembly.  
  
 Se il profiler si registra per il [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) il metodo di callback, il runtime passa il percorso e il nome dell'assembly da caricare, insieme a un puntatore a un [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) oggetto dell'interfaccia a tale metodo. Il profiler può quindi chiamare il [Icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) metodo con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` oggetto per ogni assembly di destinazione al quale intende fare riferimento dall'assembly specificato nella [ Icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 [Metodo GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)  
 [Metodo AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
