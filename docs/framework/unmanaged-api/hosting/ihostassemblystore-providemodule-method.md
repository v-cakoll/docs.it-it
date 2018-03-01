---
title: Metodo IHostAssemblyStore::ProvideModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8b29f19933ae985d15627d1eba2622f350a52e72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystoreprovidemodule-method"></a>Metodo IHostAssemblyStore::ProvideModule
Risolve un file di risorse all'interno di un assembly o collegato (ma non incorporato).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pBindInfo`  
 [in] Un puntatore a un [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) istanza che descrive il modulo di richiesto <xref:System.AppDomain>, assembly e il nome del modulo.  
  
 `pdwModuleId`  
 [out] Un puntatore a un identificatore univoco per il `IStream` contenente il modulo caricato.  
  
 `ppStmModuleImage`  
 [out] Un puntatore all'indirizzo di un `IStream` , che contiene l'immagine eseguibile portabile (PE) da caricare, o null se non è stato possibile trovare il modulo.  
  
 `ppStmPDB`  
 [out] Un puntatore all'indirizzo di un `IStream` dell'oggetto, che contiene le informazioni di debug (PDB) del programma per il modulo richiesto oppure null se non è stato possibile trovare il file con estensione pdb.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ProvideModule`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0X80070002)|L'assembly richiesto o una risorsa collegata non è possibile individuare.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId`non è sufficientemente grande da contenere l'identificatore in cui l'host deve essere restituito.|  
  
## <a name="remarks"></a>Note  
 Il valore di identità restituito per `pdwModuleId` è specificato dall'host. Gli identificatori devono essere univoci all'interno della durata di un processo. Common Language Runtime utilizza questo valore come identificatore univoco per il flusso associato. Ogni valore viene confrontato con i valori per `pAssemblyId` restituiti dalle chiamate a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) e con i valori per `pdwModuleId` restituito da altre chiamate a `ProvideModule`. Se l'host restituisce lo stesso valore di identificatore per un'altra `IStream`, CLR verifica se il contenuto del flusso è già stato mappato. In questo caso, CLR carica la copia esistente dell'immagine anziché eseguire il mapping uno nuovo. Pertanto, l'identificatore non deve sovrapporsi agli identificatori assembly restituiti da `ProvideAssembly`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [Interfaccia IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
