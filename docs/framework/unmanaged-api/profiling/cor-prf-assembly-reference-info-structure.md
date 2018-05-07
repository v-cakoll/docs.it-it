---
title: Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be32718ca392ce1712b8ce9f2e33a8f602ccb242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 [Metodo GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)  
 [Metodo AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
