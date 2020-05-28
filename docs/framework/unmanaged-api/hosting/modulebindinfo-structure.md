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
ms.openlocfilehash: 31be0525c637e50c1161129277d651b56dadfaa3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006753"
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
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`dwAppDomainId`|Identificatore univoco dell'oggetto `IStream` restituito da una chiamata al metodo [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md) da cui deve essere caricato il modulo a cui si fa riferimento.|  
|`lpAssemblyIdentity`|Identificatore univoco per l'assembly che contiene il modulo a cui si fa riferimento.|  
|`lpModuleName`|Nome del modulo a cui si fa riferimento.|  
  
## <a name="remarks"></a>Commenti  
 `ModuleBindInfo`viene passato come parametro a `IHostAssemblyStore::ProvideModule` . L'host fornisce l'identificatore univoco `dwAppDomainId` al Common Language Runtime (CLR). Dopo che una chiamata al metodo [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) restituisce, il runtime usa l'identificatore per determinare se `IStream` è stato eseguito il mapping del contenuto di. In tal caso, il runtime carica la copia esistente anziché rimappare il flusso. Il runtime usa anche questo identificatore come chiave di ricerca per i flussi restituiti dalle chiamate al `IHostAssemblyStore::ProvideAssembly` metodo. Pertanto, l'identificatore deve essere univoco per le richieste di modulo e per le richieste di assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. idl  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](hosting-structures.md)
- [Struttura AssemblyBindInfo](assemblybindinfo-structure.md)
- [Interfaccia ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](ihostassemblymanager-interface.md)
