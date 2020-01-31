---
title: Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: 4fdc8e1074bf45de3a8ab85500a85b124ce34fa1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867334"
---
# <a name="cor_prf_assembly_reference_info-structure"></a>Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO
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
  
|Member|Descrizione|  
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
  
 Se il profiler viene registrato per il metodo di callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , il runtime passa il percorso e il nome dell'assembly da caricare, insieme a un puntatore a un oggetto di interfaccia [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) a tale metodo. Il profiler può quindi chiamare il metodo [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) con un oggetto `COR_PRF_ASSEMBLY_REFERENCE_INFO` per ogni assembly di destinazione a cui fa riferimento l'assembly specificato nel callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di profilatura](profiling-structures.md)
- [Metodo GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md)
- [Metodo AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
