---
title: Metodo IHostAssemblyManager::GetNonHostStoreAssemblies
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0da548d5d5cc22eb6754859a802afa4d82fac89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438389"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a>Metodo IHostAssemblyManager::GetNonHostStoreAssemblies
Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) che rappresenta l'elenco di assembly che dovranno essere caricati da common language runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppReferenceList`  
 [out] Un puntatore all'indirizzo di un `ICLRAssemblyReferenceList` che contiene un elenco di riferimenti agli assembly che dovranno essere caricati da Common Language Runtime da caricare.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetNonHostStoreAssemblies` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente è disponibile per creare l'elenco di riferimenti per la richiesta `ICLRAssemblyReferenceList`.|  
  
## <a name="remarks"></a>Note  
 CLR risolve i riferimenti utilizzando le seguenti linee guida:  
  
-   Innanzitutto, consulta l'elenco di riferimenti ad assembly restituito da `GetNonHostStoreAssemblies`.  
  
-   Se l'assembly viene visualizzato nell'elenco, CLR esegue l'associazione normalmente.  
  
-   Se l'assembly non vengono visualizzati nell'elenco e l'host ha fornito un'implementazione di [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR chiama [IHostAssemblyStore::](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) per consentire all'host di fornire il assembly da associare.  
  
-   In caso contrario, CLR non riesce ad associare all'assembly.  
  
 Se l'host imposta `ppReferenceList` su null, CLR esamina innanzitutto la global assembly cache, chiama `ProvideAssembly`e quindi analizza la base dell'applicazione per risolvere un riferimento all'assembly.  
  
> [!NOTE]
>  Al momento dell'inizializzazione, CLR chiama `GetNonHostStoreAssemblies` una sola volta. Il metodo non viene chiamato nuovamente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [Interfaccia IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
