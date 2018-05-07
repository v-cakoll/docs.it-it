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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 385ccc7a63fb5eb27ae7bdda5bdcf13c750eb667
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="assemblybindinfo-structure"></a>Struttura AssemblyBindInfo
Fornisce informazioni dettagliate sull'assembly a cui viene fatto riferimento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`dwAppDomainId`|Un identificatore univoco per il `IStream` restituito da una chiamata a [IHostAssemblyStore::](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), da cui deve essere caricato l'assembly di riferimento.|  
|`lpReferencedIdentity`|Un identificatore univoco per l'assembly di riferimento.|  
|`lpPostPolicyIdentity`|L'identificatore per l'assembly di riferimento dopo l'applicazione di tutti i valori dei criteri di associazione.|  
|`ePolicyLevel`|Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori che indicano quali criteri di controllo delle versioni, se presente, devono essere applicati all'assembly di riferimento.|  
  
## <a name="remarks"></a>Note  
 L'identificatore univoco viene fornito dall'host `dwAppDomainId` a common language runtime (CLR). Dopo una chiamata a `IHostAssemblyStore::ProvideAssembly` restituisce, il runtime usa l'identificatore per determinare se il contenuto del `IStream` è stato eseguito il mapping. In questo caso, il runtime carica la copia esistente anziché la modifica del flusso. Il runtime usa anche questo identificatore come chiave di ricerca per i flussi restituiti dalle chiamate a [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md). Pertanto, l'identificatore deve essere univoco per le richieste di modulo e per le richieste di assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [Interfaccia ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [Interfaccia IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [Struttura ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
