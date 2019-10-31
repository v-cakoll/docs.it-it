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
ms.openlocfilehash: 0fd9409a5157e1013365c94f01631f130a76f54b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131209"
---
# <a name="eapicategories-enumeration"></a>Enumerazione EApiCategories
Vengono descritte le categorie di funzionalità che l'host può bloccare dall'esecuzione in codice parzialmente attendibile.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`eAll`|Specifica che tutte le classi gestite e i membri coperti da altri campi `EApiCategories` essere bloccati dall'esecuzione in codice parzialmente attendibile.|  
|`eExternalProcessMgmt`|Specifica che le classi gestite e i membri che consentono la creazione, la manipolazione e la distruzione di processi esterni vengono bloccati dall'esecuzione in codice parzialmente attendibile.|  
|`eExternalThreading`|Specifica che le classi gestite e i membri che consentono la creazione, la manipolazione e la distruzione di thread esterni vengono bloccati dall'esecuzione in codice parzialmente attendibile.|  
|`eMayLeakOnAbort`|Specifica che i tipi e i membri gestiti che potrebbero causare perdite di memoria in Abort non possono essere eseguiti in codice parzialmente attendibile.|  
|`eNoCategory`|Specifica che non è possibile bloccare l'esecuzione di nessuna categoria di codice gestito in codice parzialmente attendibile.|  
|`eSecurityInfrastructure`|Specifica che l'infrastruttura di sicurezza di Common Language Runtime (CLR) non viene utilizzata da codice parzialmente attendibile.|  
|`eSelfAffectingProcessMgmt`|Specifica che le classi gestite e i membri le cui funzionalità possono influenzare il processo ospitato vengono bloccati dall'esecuzione in codice parzialmente attendibile.|  
|`eSelfAffectingThreading`|Specifica che le classi gestite e i membri le cui funzionalità possono influenzare i thread nel processo ospitato vengono bloccati dall'esecuzione in codice parzialmente attendibile.|  
|`eSharedState`|Specifica che le classi gestite e i membri che espongono lo stato condiviso vengono bloccati dall'esecuzione in codice parzialmente attendibile.|  
|`eSynchronization`|Specifica che Common Language Runtime classi e membri che consentono al codice utente di mantenere i blocchi possono essere bloccati dall'esecuzione in codice parzialmente attendibile.|  
|`eUI`|Specifica che le classi gestite e i membri che consentono o richiedono un'interazione umana possono essere bloccati dall'esecuzione in codice parzialmente attendibile.|  
  
## <a name="remarks"></a>Note  
 Il metodo [ICLRHostProtectionManager:: SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) accetta un parametro di tipo `EApiCategories`.  
  
 L'enumerazione `EApiCategories` e il metodo `SetProtectedCategories` sono direttamente correlati alla classe <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> gestita. La classe gestita viene utilizzata con l'enumerazione <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType>, i cui valori corrispondono direttamente ai valori `EApiCategories`, per contrassegnare i tipi e i membri gestiti che espongono le funzionalità corrispondenti alle categorie descritte da `EApiCategories`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
