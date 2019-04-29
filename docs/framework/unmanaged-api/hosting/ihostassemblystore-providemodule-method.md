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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e07e2c3f2c6000f5a081b13316c269f322b1ef8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599347"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>Metodo IHostAssemblyStore::ProvideModule
Risolve un file di risorse modulo all'interno di un assembly o un collegato (ma non incorporato).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pBindInfo`  
 [in] Un puntatore a un [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) istanza che descrive il modulo richiesto <xref:System.AppDomain>, assembly e il nome del modulo.  
  
 `pdwModuleId`  
 [out] Un puntatore a un identificatore univoco per il `IStream` contenente il modulo caricato.  
  
 `ppStmModuleImage`  
 [out] Un puntatore all'indirizzo di un `IStream` dell'oggetto, che contiene l'immagine del file eseguibile portabile (PE) di essere caricati oppure null se non è stato possibile trovare il modulo.  
  
 `ppStmPDB`  
 [out] Un puntatore all'indirizzo di un `IStream` dell'oggetto, che contiene le informazioni di debug (PDB) del programma per il modulo richiesto o null se il file con estensione PDB non è stato trovato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ProvideModule` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|L'assembly richiesto o risorsa collegata non è possibile individuare.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` non è sufficientemente grande da contenere l'identificatore che l'host deve essere restituito.|  
  
## <a name="remarks"></a>Note  
 Il valore identity restituiti per `pdwModuleId` è specificato dall'host. Gli identificatori devono essere univoci all'interno della durata di un processo. Common Language Runtime Usa questo valore come l'identificatore univoco per il flusso associato. Ogni valore viene confrontato con i valori per `pAssemblyId` restituiti dalle chiamate a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) e con i valori di `pdwModuleId` restituito da altre chiamate a `ProvideModule`. Se l'host restituisce lo stesso valore di identificatore per un altro `IStream`, Common Language Runtime controlla se il contenuto del flusso è già stato mappato. In questo caso, CLR caricata la copia esistente di immagine anziché eseguire il mapping di una nuova. Pertanto, l'identificatore non deve sovrapporsi con gli identificatori di assembly restituiti da `ProvideAssembly`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Interfaccia IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
