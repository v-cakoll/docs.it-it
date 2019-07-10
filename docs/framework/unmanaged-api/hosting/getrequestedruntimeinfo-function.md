---
title: Funzione GetRequestedRuntimeInfo
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62a6f6d6e73ce42c8c86d4e458322e5bd361f412
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778132"
---
# <a name="getrequestedruntimeinfo-function"></a>Funzione GetRequestedRuntimeInfo
Ottiene informazioni di versione e la directory di common language runtime (CLR) richiesto da un'applicazione.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pExe`  
 [in] Il nome dell'applicazione.  
  
 `pwszVersion`  
 [in] Stringa che specifica il numero di versione del runtime.  
  
 `pConfigurationFile`  
 [in] Il nome del file di configurazione associato `pExe`.  
  
 `startupFlags`  
 [in] Uno o più i [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) valori di enumerazione.  
  
 `runtimeInfoFlags`  
 [in] Uno o più i [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) valori di enumerazione.  
  
 `pDirectory`  
 [out] Un buffer che contiene il percorso della directory per il runtime di una volta completata correttamente.  
  
 `dwDirectory`  
 [in] La lunghezza del buffer della directory.  
  
 `dwDirectoryLength`  
 [out] Puntatore alla lunghezza della stringa di percorso di directory.  
  
 `pVersion`  
 [out] Un buffer che contiene il numero di versione del runtime di una volta completata correttamente.  
  
 `cchBuffer`  
 [in] La lunghezza del buffer di stringa di versione.  
  
 `dwlength`  
 [out] Puntatore alla lunghezza della stringa di versione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore standard modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|ERROR_INSUFFICIENT_BUFFER|Il buffer di directory non è sufficiente per archiviare il percorso della directory.<br /><br /> -oppure-<br /><br /> Il buffer di versione non è sufficiente per archiviare la stringa di versione.|  
  
## <a name="remarks"></a>Note  
 Il `GetRequestedRuntimeInfo` metodo restituisce le informazioni di runtime relative alla versione caricata nel processo, che non è necessariamente la versione più recente installata nel computer.  
  
 In .NET Framework versione 2.0, è possibile ottenere informazioni sull'ultima versione installata tramite il `GetRequestedRuntimeInfo` metodo come indicato di seguito:  
  
- Specificare il `pExe`, `pwszVersion`, e `pConfigurationFile` parametri come valori null.  
  
- Specificare il flag RUNTIME_INFO_UPGRADE_VERSION nel `RUNTIME_INFO_FLAGS` enumerazioni per il `runtimeInfoFlags` parametro.  
  
 Il `GetRequestedRuntimeInfo` metodo non restituisce la versione più recente di Common Language Runtime nelle circostanze seguenti:  
  
- Esiste un file di configurazione che specifica il caricamento di una particolare versione CLR. Si noti che .NET Framework utilizzerà il file di configurazione anche se si specifica null per il `pConfigurationFile` parametro.  
  
- Il [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) metodo è stato chiamato specificando una versione precedente di Common Language Runtime.  
  
- Un'applicazione che è stata compilata per una versione precedente di Common Language Runtime è in esecuzione.  
  
 Per il `runtimeInfoFlags` parametro, è possibile specificare solo una delle costanti dell'architettura di `RUNTIME_INFO_FLAGS` enumerazione per volta:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [Funzione GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
