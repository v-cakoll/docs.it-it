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
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178145"
---
# <a name="getrequestedruntimeinfo-function"></a>Funzione GetRequestedRuntimeInfo
Ottiene informazioni sulla versione e sulla directory relative a Common Language Runtime (CLR) richiesto da un'applicazione.  
  
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
 [in] Nome dell'applicazione.  
  
 `pwszVersion`  
 [in] Stringa che specifica il numero di versione del runtime.  
  
 `pConfigurationFile`  
 [in] Nome del file di configurazione `pExe`associato a .  
  
 `startupFlags`  
 [in] Uno o più [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) STARTUP_FLAGS valori di enumerazione.  
  
 `runtimeInfoFlags`  
 [in] Uno o più valori di enumerazione [RUNTIME_INFO_FLAGS.](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)  
  
 `pDirectory`  
 [fuori] Buffer che contiene il percorso di directory del runtime al completamento.  
  
 `dwDirectory`  
 [in] Lunghezza del buffer di directory.  
  
 `dwDirectoryLength`  
 [fuori] Puntatore alla lunghezza della stringa del percorso di directory.  
  
 `pVersion`  
 [fuori] Buffer che contiene il numero di versione del runtime al completamento.  
  
 `cchBuffer`  
 [in] Lunghezza del buffer di stringa di versione.  
  
 `dwlength`  
 [fuori] Puntatore alla lunghezza della stringa di versione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM (Component Object Model) standard, come definito in WinError.h, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|ERROR_INSUFFICIENT_BUFFER|Il buffer di directory non è sufficientemente grande per archiviare il percorso della directory.<br /><br /> - oppure -<br /><br /> Il buffer di versione non è sufficientemente grande per archiviare la stringa di versione.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `GetRequestedRuntimeInfo` metodo restituisce informazioni di runtime sulla versione caricata nel processo, che non è necessariamente la versione più recente installata nel computer.  
  
 In .NET Framework versione 2.0 è possibile ottenere informazioni sull'ultima versione installata utilizzando il `GetRequestedRuntimeInfo` metodo nel modo seguente:  
  
- Specificare `pExe` `pwszVersion`i `pConfigurationFile` parametri , e come null.  
  
- Specificare il flag `RUNTIME_INFO_FLAGS` di RUNTIME_INFO_UPGRADE_VERSION `runtimeInfoFlags` nelle enumerazioni per il parametro.  
  
 Il `GetRequestedRuntimeInfo` metodo non restituisce la versione più recente di CLR nelle circostanze seguenti:  
  
- Esiste un file di configurazione dell'applicazione che specifica il caricamento di una particolare versione di CLR. Si noti che .NET Framework utilizzerà il file `pConfigurationFile` di configurazione anche se si specifica null per il parametro.  
  
- Il [metodo CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) è stato chiamato specificando una versione precedente di CLR.  
  
- Un'applicazione compilata per una versione precedente di CLR è attualmente in esecuzione.  
  
 Per `runtimeInfoFlags` il parametro, è possibile specificare solo `RUNTIME_INFO_FLAGS` una delle costanti di architettura dell'enumerazione alla volta:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Mscoree  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [Funzione GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
