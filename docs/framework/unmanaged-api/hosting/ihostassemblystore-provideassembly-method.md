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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62a8be1e330338043df50bd80576b5aa65447b9c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111904"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>Metodo IHostAssemblyStore::ProvideAssembly
Ottiene un riferimento a un assembly che non fa riferimento il [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituito da [IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). Common language runtime (CLR) chiama `ProvideAssembly` per ogni assembly che non compare nell'elenco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 [in] Un puntatore a un [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) istanza usato dall'host per determinare alcune caratteristiche di associazione, tra cui la presenza o assenza di qualsiasi criterio di controllo delle versioni e l'assembly a cui associarsi.  
  
 `pAssemblyId`  
 [out] Un puntatore a un identificatore univoco per l'assembly richiesto per l'oggetto `IStream`.  
  
 `pHostContext`  
 [out] Un puntatore ai dati specifici per l'host utilizzato per determinare l'evidenza dell'assembly richiesto senza la necessità di una piattaforma chiamata invoke. `pHostContext` corrisponde alla <xref:System.Reflection.Assembly.HostContext%2A> proprietà di gestito <xref:System.Reflection.Assembly> classe.  
  
 `ppStmAssemblyImage`  
 [out] Un puntatore all'indirizzo di un `IStream` che contiene l'immagine eseguibile portabile (PE) da caricare, oppure null se non è stato possibile trovare l'assembly.  
  
 `ppStmPDB`  
 [out] Un puntatore all'indirizzo di un `IStream` che contiene le informazioni di debug (PDB) di programma, o null se non è stato possibile trovare il file con estensione pdb.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Impossibile individuare l'assembly richiesto.|  
|E_NOT_SUFFICIENT_BUFFER|Le dimensioni del buffer specificata da `pAssemblyId` non è sufficientemente grande da contenere l'identificatore che l'host deve essere restituito.|  
  
## <a name="remarks"></a>Note  
 Il valore identity restituiti per `pAssemblyId` è specificato dall'host. Gli identificatori devono essere univoci all'interno della durata di un processo. Common Language Runtime Usa questo valore come un identificatore univoco per il flusso. Ogni valore viene confrontato con i valori per `pAssemblyId` restituito da altre chiamate a `ProvideAssembly`. Se l'host restituisce lo stesso `pAssemblyId` valore per un altro `IStream`, Common Language Runtime controlla se il contenuto del flusso è già stato mappato. In questo caso, il runtime carica la copia esistente di immagine anziché eseguire il mapping di una nuova.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Interfaccia IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
