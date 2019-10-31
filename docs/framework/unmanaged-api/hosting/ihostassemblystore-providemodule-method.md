---
title: Metodo IHostAssemblyStore::ProvideModule
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
ms.openlocfilehash: eed09a8149a21140ad61133f29391f86cb0fb929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124477"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>Metodo IHostAssemblyStore::ProvideModule
Risolve un modulo all'interno di un assembly o di un file di risorse collegato, ma non incorporato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pBindInfo`  
 in Puntatore a un'istanza di [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) che descrive il <xref:System.AppDomain>del modulo, l'assembly e il nome del modulo richiesti.  
  
 `pdwModuleId`  
 out Puntatore a un identificatore univoco per la `IStream` che contiene il modulo caricato.  
  
 `ppStmModuleImage`  
 out Puntatore all'indirizzo di un oggetto `IStream`, che contiene l'immagine PE (Portable Executable) da caricare, oppure null se il modulo non è stato trovato.  
  
 `ppStmPDB`  
 out Puntatore all'indirizzo di un oggetto `IStream`, che contiene le informazioni di debug del programma (PDB) per il modulo richiesto, oppure null se il file con estensione PDB non è stato trovato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ProvideModule` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Impossibile trovare l'assembly o la risorsa collegata richiesta.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` non è sufficientemente grande da contenere l'identificatore che l'host vuole restituire.|  
  
## <a name="remarks"></a>Note  
 Il valore Identity restituito per `pdwModuleId` viene specificato dall'host. Gli identificatori devono essere univoci entro la durata di un processo. CLR utilizza questo valore come identificatore univoco per il flusso associato. Verifica ogni valore in base ai valori per `pAssemblyId` restituiti dalle chiamate a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) e ai valori per `pdwModuleId` restituiti da altre chiamate a `ProvideModule`. Se l'host restituisce lo stesso valore di identificatore per un altro `IStream`, CLR verifica se il contenuto del flusso è già stato mappato. In tal caso, CLR carica la copia esistente dell'immagine anziché mapparne una nuova. Pertanto, anche l'identificatore non deve sovrapporsi agli identificatori di assembly restituiti da `ProvideAssembly`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Interfaccia IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
