---
title: Metodo IHostAssemblyStore::ProvideAssembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore.ProvideAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cda88c2e93b4f90844ad3dec2ed0fa4366dba6d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblystoreprovideassembly-method"></a>Metodo IHostAssemblyStore::ProvideAssembly
Ottiene un riferimento a un assembly che non fa riferimento il [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituito da [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). Common language runtime (CLR) chiama `ProvideAssembly` per ogni assembly che non compare nell'elenco.  
  
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
  
#### <a name="parameters"></a>Parametri  
 `pBindInfo`  
 [in] Un puntatore a un [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) istanza utilizzati dall'host per determinare alcune caratteristiche di associazione, ad esempio la presenza o assenza di criteri e l'assembly da associare.  
  
 `pAssemblyId`  
 [out] Un puntatore a un identificatore univoco per l'assembly richiesto per `IStream`.  
  
 `pHostContext`  
 [out] Un puntatore a dati specifici dell'host utilizzato per determinare l'evidenza dell'assembly richiesto, senza la necessità di una piattaforma di chiamata di PInvoke. `pHostContext`corrisponde alla <xref:System.Reflection.Assembly.HostContext%2A> proprietà di gestito <xref:System.Reflection.Assembly> classe.  
  
 `ppStmAssemblyImage`  
 [out] Un puntatore all'indirizzo di un `IStream` che contiene l'immagine eseguibile portabile (PE) da caricare oppure null se non è stato possibile trovare l'assembly.  
  
 `ppStmPDB`  
 [out] Un puntatore all'indirizzo di un `IStream` che contiene le informazioni di debug (PDB) di programma, o null se non è stato possibile trovare il file con estensione pdb.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0X80070002)|Impossibile individuare l'assembly richiesto.|  
|E_NOT_SUFFICIENT_BUFFER|Le dimensioni del buffer specificata da `pAssemblyId` non è sufficientemente grande da contenere l'identificatore in cui l'host deve essere restituito.|  
  
## <a name="remarks"></a>Note  
 Il valore di identità restituito per `pAssemblyId` è specificato dall'host. Gli identificatori devono essere univoci all'interno della durata di un processo. Common Language Runtime utilizza questo valore come identificatore univoco per il flusso. Ogni valore viene confrontato con i valori per `pAssemblyId` restituito da altre chiamate a `ProvideAssembly`. Se l'host restituisce lo stesso `pAssemblyId` valore per un'altra `IStream`, CLR verifica se il contenuto del flusso è già stato mappato. In questo caso, il runtime carica la copia esistente dell'immagine anziché eseguire il mapping uno nuovo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRAssemblyReferenceList (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
