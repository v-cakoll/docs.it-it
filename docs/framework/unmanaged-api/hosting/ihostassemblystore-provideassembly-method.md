---
title: Metodo IHostAssemblyStore::ProvideAssembly
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
ms.openlocfilehash: f97490e89e835716911072dbad5f70d8e55e76e6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805023"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>Metodo IHostAssemblyStore::ProvideAssembly
Ottiene un riferimento a un assembly a cui non viene fatto riferimento da [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituito da [IHostAssemblyManager:: GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md). Il Common Language Runtime (CLR) chiama `ProvideAssembly` per ogni assembly che non viene visualizzato nell'elenco.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pBindInfo`  
 in Puntatore a un'istanza di [AssemblyBindInfo](assemblybindinfo-structure.md) utilizzata dall'host per determinare determinate caratteristiche di associazione, inclusa la presenza o l'assenza di criteri di controllo delle versioni e l'assembly a cui eseguire l'associazione.  
  
 `pAssemblyId`  
 out Puntatore a un identificatore univoco per l'assembly richiesto per l'oggetto `IStream` .  
  
 `pHostContext`  
 out Puntatore a dati specifici dell'host utilizzati per determinare l'evidenza dell'assembly richiesto senza la necessità di una chiamata platform invoke. `pHostContext`corrisponde alla <xref:System.Reflection.Assembly.HostContext%2A> proprietà della <xref:System.Reflection.Assembly> classe gestita.  
  
 `ppStmAssemblyImage`  
 out Puntatore all'indirizzo di un oggetto `IStream` che contiene l'immagine del file eseguibile di tipo PE da caricare o null se l'assembly non è stato trovato.  
  
 `ppStmPDB`  
 out Puntatore all'indirizzo di un oggetto `IStream` che contiene le informazioni di debug del programma (PDB) o null se il file con estensione PDB non è stato trovato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Impossibile trovare l'assembly richiesto.|  
|E_NOT_SUFFICIENT_BUFFER|Le dimensioni del buffer specificate da `pAssemblyId` non sono sufficienti per contenere l'identificatore che l'host vuole restituire.|  
  
## <a name="remarks"></a>Osservazioni  
 Il valore Identity restituito per `pAssemblyId` viene specificato dall'host. Gli identificatori devono essere univoci entro la durata di un processo. CLR utilizza questo valore come identificatore univoco per il flusso. Verifica ogni valore rispetto ai valori `pAssemblyId` restituiti da altre chiamate a `ProvideAssembly` . Se l'host restituisce lo stesso `pAssemblyId` valore per un altro `IStream` , CLR verifica se è già stato eseguito il mapping del contenuto del flusso. In tal caso, il runtime carica la copia esistente dell'immagine anziché mapparne una nuova.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](ihostassemblymanager-interface.md)
- [Interfaccia IHostAssemblyStore](ihostassemblystore-interface.md)
