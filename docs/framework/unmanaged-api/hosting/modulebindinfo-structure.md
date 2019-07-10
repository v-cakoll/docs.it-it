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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e0e877402daf27c375aedddf8922e919a546ae5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781170"
---
# <a name="modulebindinfo-structure"></a>Struttura ModuleBindInfo
Fornisce informazioni dettagliate sul modulo cui viene fatto riferimento e l'assembly che lo contiene.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`dwAppDomainId`|Un identificatore univoco per il `IStream` restituito da una chiamata ai [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) metodo da cui è possibile caricare il modulo di cui viene fatto riferimento.|  
|`lpAssemblyIdentity`|Identificatore univoco per l'assembly che contiene il modulo di cui viene fatto riferimento.|  
|`lpModuleName`|Il nome del modulo cui viene fatto riferimento.|  
  
## <a name="remarks"></a>Note  
 `ModuleBindInfo` viene passato come parametro al `IHostAssemblyStore::ProvideModule`. L'identificatore univoco viene fornito dall'host `dwAppDomainId` a common language runtime (CLR). Dopo una chiamata al [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) metodo viene restituito, il runtime usa l'identificatore per determinare se il contenuto del `IStream` sono stati mappati. In questo caso, il runtime carica la copia esistente anziché la modifica del flusso. Il runtime usa anche questo identificatore come chiave di ricerca per i flussi che vengono restituiti dalle chiamate al `IHostAssemblyStore::ProvideAssembly` (metodo). Pertanto, l'identificatore deve essere univoco per le richieste di modulo anche per quanto riguarda le richieste di assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.idl  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Struttura AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [Interfaccia ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
