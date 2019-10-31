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
ms.openlocfilehash: a93d700c9c398076d87156cd2eb9c6d0d08cccfd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124479"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>Metodo IHostAssemblyStore::ProvideAssembly
Ottiene un riferimento a un assembly a cui non viene fatto riferimento da [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituito da [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). Il Common Language Runtime (CLR) chiama `ProvideAssembly` per ogni assembly che non viene visualizzato nell'elenco.  
  
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
 in Puntatore a un'istanza di [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) utilizzata dall'host per determinare determinate caratteristiche di associazione, inclusa la presenza o l'assenza di criteri di controllo delle versioni e l'assembly a cui eseguire l'associazione.  
  
 `pAssemblyId`  
 out Puntatore a un identificatore univoco per l'assembly richiesto per questo `IStream`.  
  
 `pHostContext`  
 out Puntatore a dati specifici dell'host utilizzati per determinare l'evidenza dell'assembly richiesto senza la necessità di una chiamata platform invoke. `pHostContext` corrisponde alla proprietà <xref:System.Reflection.Assembly.HostContext%2A> della classe <xref:System.Reflection.Assembly> gestita.  
  
 `ppStmAssemblyImage`  
 out Puntatore all'indirizzo di un `IStream` che contiene l'immagine del file eseguibile portabile (PE) da caricare o null se l'assembly non è stato trovato.  
  
 `ppStmPDB`  
 out Puntatore all'indirizzo di un `IStream` contenente le informazioni di debug del programma (PDB) o null se il file con estensione PDB non è stato trovato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Impossibile trovare l'assembly richiesto.|  
|E_NOT_SUFFICIENT_BUFFER|La dimensione del buffer specificata da `pAssemblyId` non è sufficiente per contenere l'identificatore che l'host vuole restituire.|  
  
## <a name="remarks"></a>Note  
 Il valore Identity restituito per `pAssemblyId` viene specificato dall'host. Gli identificatori devono essere univoci entro la durata di un processo. CLR utilizza questo valore come identificatore univoco per il flusso. Controlla ogni valore in base ai valori per `pAssemblyId` restituiti da altre chiamate al `ProvideAssembly`. Se l'host restituisce lo stesso valore di `pAssemblyId` per un'altra `IStream`, CLR verifica se è già stato eseguito il mapping del contenuto del flusso. In tal caso, il runtime carica la copia esistente dell'immagine anziché mapparne una nuova.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Interfaccia IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
