---
title: Enumerazione EApiCategories
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3debd3f13d78841188dd8c900f51c0110e1d4c67
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086455"
---
# <a name="eapicategories-enumeration"></a>Enumerazione EApiCategories
Vengono descritte le categorie di funzionalità che l'host può impedire l'esecuzione di codice parzialmente attendibile.  
  
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
  
|Member|Descrizione|  
|------------|-----------------|  
|`eAll`|Specifica che tutte le classi gestite e membri che vengono analizzati da altri `EApiCategories` campi essere impedita l'esecuzione di codice parzialmente attendibile.|  
|`eExternalProcessMgmt`|Specifica che le classi gestite e i membri che consentono la creazione, modifica e l'eliminazione di processi esterni bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eExternalThreading`|Specifica che le classi gestite e i membri che consentono la creazione, modifica e la distruzione di thread esterni bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eMayLeakOnAbort`|Specifica che i tipi gestiti e i membri che potrebbero causare una perdita di memoria in caso di interruzione bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eNoCategory`|Specifica che nessuna categoria di codice gestito bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eSecurityInfrastructure`|Specifica che l'infrastruttura di sicurezza di common language runtime (CLR) essere bloccate vengano utilizzati da codice parzialmente attendibile.|  
|`eSelfAffectingProcessMgmt`|Specifica che le classi gestite e i membri cui capacità può influenzare il processo ospitato bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eSelfAffectingThreading`|Specifica che le classi gestite e i membri cui capacità possono influire sui thread nel processo host bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eSharedState`|Specifica che le classi gestite e i membri che espongono lo stato condiviso bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eSynchronization`|Specifica che common language runtime e classi i membri che consentono il codice utente per mantenere attivi i blocchi bloccato dall'esecuzione di codice parzialmente attendibile.|  
|`eUI`|Specifica che le classi gestite e i membri che consentono o richiedono l'interazione umana bloccato dall'esecuzione di codice parzialmente attendibile.|  
  
## <a name="remarks"></a>Note  
 Il [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) metodo accetta un parametro di tipo `EApiCategories`.  
  
 Il `EApiCategories` enumerazione e la `SetProtectedCategories` metodo sono direttamente correlati all'oggetto gestito <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> classe. La classe gestita viene utilizzata con il <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumerazione, i cui valori corrispondono direttamente al `EApiCategories` valori, per contrassegnare tipi e membri che espongono funzionalità corrispondenti per le categorie descritte dal gestiti `EApiCategories`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
