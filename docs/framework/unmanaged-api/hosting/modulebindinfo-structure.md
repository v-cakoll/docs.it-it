---
title: Struttura ModuleBindInfo
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133744"
---
# <a name="modulebindinfo-structure"></a>Struttura ModuleBindInfo
Fornisce informazioni dettagliate sul modulo a cui si fa riferimento e sull'assembly che la contiene.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`dwAppDomainId`|Identificatore univoco per il `IStream` restituito da una chiamata al metodo [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) da cui deve essere caricato il modulo a cui si fa riferimento.|  
|`lpAssemblyIdentity`|Identificatore univoco per l'assembly che contiene il modulo a cui si fa riferimento.|  
|`lpModuleName`|Nome del modulo a cui si fa riferimento.|  
  
## <a name="remarks"></a>Note  
 `ModuleBindInfo` viene passato come parametro a `IHostAssemblyStore::ProvideModule`. L'host fornisce l'identificatore univoco `dwAppDomainId` al Common Language Runtime (CLR). Dopo che una chiamata al metodo [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) restituisce, il runtime usa l'identificatore per determinare se è stato eseguito il mapping del contenuto della `IStream`. In tal caso, il runtime carica la copia esistente anziché rimappare il flusso. Il runtime usa anche questo identificatore come chiave di ricerca per i flussi restituiti dalle chiamate al metodo `IHostAssemblyStore::ProvideAssembly`. Pertanto, l'identificatore deve essere univoco per le richieste di modulo e per le richieste di assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. idl  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Struttura AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [Interfaccia ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
