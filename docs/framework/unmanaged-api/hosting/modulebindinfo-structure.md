---
title: Struttura ModuleBindInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 399ba2471b4dc7c5e372a56a9dcab8117068a693
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="modulebindinfo-structure"></a>Struttura ModuleBindInfo
Fornisce informazioni dettagliate sul modulo a cui fa riferimento e l'assembly che lo contiene.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`dwAppDomainId`|Un identificatore univoco per il `IStream` restituito da una chiamata al [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) metodo da cui è possibile caricare il modulo a cui fa riferimento.|  
|`lpAssemblyIdentity`|Identificatore univoco per l'assembly che contiene il modulo a cui fa riferimento.|  
|`lpModuleName`|Il nome del modulo a cui fa riferimento.|  
  
## <a name="remarks"></a>Note  
 `ModuleBindInfo`viene passato come parametro a `IHostAssemblyStore::ProvideModule`. L'identificatore univoco viene fornito dall'host `dwAppDomainId` a common language runtime (CLR). Dopo una chiamata al [IHostAssemblyStore::](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) metodo viene restituito, il runtime usa l'identificatore per determinare se il contenuto del `IStream` è stato eseguito il mapping. In questo caso, il runtime carica la copia esistente anziché la modifica del flusso. Il runtime usa anche questo identificatore come chiave di ricerca per i flussi restituiti dalle chiamate al `IHostAssemblyStore::ProvideAssembly` metodo. Pertanto, l'identificatore deve essere univoco per richieste del modulo anche per le richieste di assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [Struttura AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 [Interfaccia ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
