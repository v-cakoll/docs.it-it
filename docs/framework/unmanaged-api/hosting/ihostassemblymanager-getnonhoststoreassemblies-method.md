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
ms.openlocfilehash: 9a1440be7011130b16d7112ae15026eb74856190
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501593"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a>Metodo IHostAssemblyManager::GetNonHostStoreAssemblies
Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) che rappresenta l'elenco di assembly che l'host prevede venga caricato dal Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppReferenceList`  
 out Puntatore all'indirizzo di un oggetto `ICLRAssemblyReferenceList` che contiene un elenco di riferimenti agli assembly che l'host prevede venga caricato da CLR.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetNonHostStoreAssemblies`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente per creare l'elenco di riferimenti per la richiesta `ICLRAssemblyReferenceList` .|  
  
## <a name="remarks"></a>Osservazioni  
 CLR risolve i riferimenti usando il set di linee guida seguente:  
  
- In primo luogo, consulta l'elenco di riferimenti ad assembly restituiti da `GetNonHostStoreAssemblies` .  
  
- Se l'assembly viene visualizzato nell'elenco, il CLR viene associato normalmente a tale assembly.  
  
- Se l'assembly non è presente nell'elenco e l'host ha fornito un'implementazione di [IHostAssemblyStore](ihostassemblystore-interface.md), CLR chiama [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) per consentire all'host di fornire l'assembly a cui eseguire l'associazione.  
  
- In caso contrario, CLR non è in grado di eseguire il binding all'assembly.  
  
 Se l'host imposta `ppReferenceList` su null, CLR verifica prima di tutto la Global assembly cache, chiama `ProvideAssembly` e quindi esegue il probe della base dell'applicazione per risolvere un riferimento a un assembly.  
  
> [!NOTE]
> Durante l'inizializzazione, CLR chiama `GetNonHostStoreAssemblies` una sola volta. Il metodo non viene chiamato nuovamente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](ihostassemblymanager-interface.md)
- [Interfaccia IHostAssemblyStore](ihostassemblystore-interface.md)
