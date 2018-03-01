---
title: Enumerazione EApiCategories
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
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 630a3048072ed7b19b3250e75aca3b31e4dd7df7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="eapicategories-enumeration"></a>Enumerazione EApiCategories
Vengono descritte le categorie di funzionalità che l'host può impedire l'esecuzione in codice parzialmente attendibile.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`eAll`|Specifica che tutte le classi gestite e membri inclusi da altri `EApiCategories` campi bloccare l'esecuzione in codice parzialmente attendibile.|  
|`eExternalProcessMgmt`|Specifica che deve essere impedita l'esecuzione in codice parzialmente attendibile di classi gestite e i membri che consentono la creazione, modifica e l'eliminazione di processi esterni.|  
|`eExternalThreading`|Specifica che le classi gestite e i membri che consentono la creazione, la modifica e la distruzione di thread esterni bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eMayLeakOnAbort`|Specifica che deve essere impedita l'esecuzione in codice parzialmente attendibile di tipi gestiti e i membri che potrebbero causare una perdita di memoria in caso di interruzione.|  
|`eNoCategory`|Specifica che deve non essere impedita l'esecuzione in codice parzialmente attendibile categorie nessun codice gestito.|  
|`eSecurityInfrastructure`|Specifica che l'infrastruttura di protezione di common language runtime (CLR) bloccato vengano utilizzati da codice parzialmente attendibile.|  
|`eSelfAffectingProcessMgmt`|Specifica che le classi gestite e i membri le cui funzionalità può influenzare il processo di hosting bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eSelfAffectingThreading`|Specifica che le classi gestite e i membri che possono influire sulla thread nel processo host bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eSharedState`|Specifica che deve essere impedita l'esecuzione in codice parzialmente attendibile di classi gestite e i membri che espongono lo stato condiviso.|  
|`eSynchronization`|Specifica che deve essere impedita l'esecuzione in codice parzialmente attendibile di common language runtime e classi i membri che consentono di mantenere attivi i blocchi di codice utente.|  
|`eUI`|Specifica che le classi gestite e i membri che consentono o richiedono l'interazione umana bloccato dall'esecuzione di codice parzialmente attendibile.|  
  
## <a name="remarks"></a>Note  
 Il [ICLRHostProtectionManager::](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) metodo accetta un parametro di tipo `EApiCategories`.  
  
 Il `EApiCategories` enumerazione e `SetProtectedCategories` metodo sono direttamente correlati all'oggetto gestito <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> classe. La classe gestita viene utilizzata con la <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumerazione, i cui valori corrispondono direttamente al `EApiCategories` valori, per contrassegnare i tipi gestiti e i membri che espongono funzionalità corrispondenti alle categorie descritte da `EApiCategories`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
