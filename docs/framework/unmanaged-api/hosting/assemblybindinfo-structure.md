---
title: Struttura AssemblyBindInfo
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
ms.openlocfilehash: 615637813b08629aaea74b23fa2737f52d61bafb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616918"
---
# <a name="assemblybindinfo-structure"></a>Struttura AssemblyBindInfo
Fornisce informazioni dettagliate sull'assembly a cui si fa riferimento.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`dwAppDomainId`|Identificatore univoco per l'oggetto `IStream` restituito da una chiamata a [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md), da cui deve essere caricato l'assembly a cui si fa riferimento.|  
|`lpReferencedIdentity`|Identificatore univoco per l'assembly a cui si fa riferimento.|  
|`lpPostPolicyIdentity`|Identificatore dell'assembly a cui si fa riferimento dopo l'applicazione di tutti i valori dei criteri di associazione.|  
|`ePolicyLevel`|Uno dei valori di [EPolicyAction](epolicyaction-enumeration.md) che indica quali criteri di controllo delle versioni, se presenti, devono essere applicati all'assembly a cui si fa riferimento.|  
  
## <a name="remarks"></a>Osservazioni  
 L'host fornisce l'identificatore univoco `dwAppDomainId` al Common Language Runtime (CLR). Dopo che una chiamata a `IHostAssemblyStore::ProvideAssembly` restituisce, il runtime usa l'identificatore per determinare se `IStream` è stato eseguito il mapping del contenuto di. In tal caso, il runtime carica la copia esistente anziché rimappare il flusso. Il runtime usa anche questo identificatore come chiave di ricerca per i flussi restituiti dalle chiamate a [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md). Pertanto, l'identificatore deve essere univoco per le richieste di modulo e per le richieste di assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. idl  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](hosting-structures.md)
- [Interfaccia ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](ihostassemblymanager-interface.md)
- [Interfaccia IHostAssemblyStore](ihostassemblystore-interface.md)
- [Struttura ModuleBindInfo](modulebindinfo-structure.md)
