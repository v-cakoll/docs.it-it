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
ms.openlocfilehash: d31b0190ef9a697fb27c849db080bec6c57618ae
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616385"
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
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`eAll`|Specifica che tutte le classi gestite e i membri che sono coperti da altri `EApiCategories` campi vengono bloccati dall'esecuzione in codice parzialmente attendibile.|  
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
  
## <a name="remarks"></a>Osservazioni  
 Il metodo [ICLRHostProtectionManager:: SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md) accetta un parametro di tipo `EApiCategories` .  
  
 L' `EApiCategories` enumerazione e il `SetProtectedCategories` metodo sono direttamente correlati alla classe gestita <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> . La classe gestita viene utilizzata con l' <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumerazione, i cui valori corrispondono direttamente ai `EApiCategories` valori, per contrassegnare i tipi e i membri gestiti che espongono le funzionalità corrispondenti alle categorie descritte da `EApiCategories` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)
- [Enumerazioni di hosting](hosting-enumerations.md)
