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
ms.openlocfilehash: cd1d9e768698115bee22e35699b044e0c3526d2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136314"
---
# <a name="getrequestedruntimeinfo-function"></a>Funzione GetRequestedRuntimeInfo
Ottiene le informazioni sulla versione e sulla directory relative alla Common Language Runtime (CLR) richiesta da un'applicazione.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
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
 in Nome dell'applicazione.  
  
 `pwszVersion`  
 in Stringa che specifica il numero di versione del runtime.  
  
 `pConfigurationFile`  
 in Nome del file di configurazione associato a `pExe`.  
  
 `startupFlags`  
 in Uno o più valori di enumerazione [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) .  
  
 `runtimeInfoFlags`  
 in Uno o più valori di enumerazione [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) .  
  
 `pDirectory`  
 out Buffer che contiene il percorso di directory del runtime dopo il completamento.  
  
 `dwDirectory`  
 in Lunghezza del buffer di directory.  
  
 `dwDirectoryLength`  
 out Puntatore alla lunghezza della stringa del percorso di directory.  
  
 `pVersion`  
 out Buffer che contiene il numero di versione del runtime dopo il completamento.  
  
 `cchBuffer`  
 in Lunghezza del buffer della stringa di versione.  
  
 `dwlength`  
 out Puntatore alla lunghezza della stringa di versione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|ERROR_INSUFFICIENT_BUFFER|Il buffer di directory non è abbastanza grande per archiviare il percorso della directory.<br /><br /> -oppure-<br /><br /> Il buffer della versione non è abbastanza grande per archiviare la stringa di versione.|  
  
## <a name="remarks"></a>Note  
 Il metodo `GetRequestedRuntimeInfo` restituisce informazioni in fase di esecuzione sulla versione caricata nel processo, che non è necessariamente la versione più recente installata nel computer.  
  
 Nel .NET Framework versione 2,0, è possibile ottenere informazioni sull'ultima versione installata usando il metodo `GetRequestedRuntimeInfo` come indicato di seguito:  
  
- Specificare i parametri `pExe`, `pwszVersion`e `pConfigurationFile` come null.  
  
- Specificare il flag RUNTIME_INFO_UPGRADE_VERSION nelle enumerazioni `RUNTIME_INFO_FLAGS` per il parametro `runtimeInfoFlags`.  
  
 Il metodo `GetRequestedRuntimeInfo` non restituisce la versione più recente di CLR nelle circostanze seguenti:  
  
- Un file di configurazione dell'applicazione che specifica il caricamento di una determinata versione di CLR esiste. Si noti che il .NET Framework utilizzerà il file di configurazione anche se si specifica null per il parametro `pConfigurationFile`.  
  
- Il metodo [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) è stato chiamato specificando una versione precedente di CLR.  
  
- Un'applicazione compilata per una versione CLR precedente è attualmente in esecuzione.  
  
 Per il parametro `runtimeInfoFlags`, è possibile specificare solo una delle costanti di architettura dell'enumerazione `RUNTIME_INFO_FLAGS` alla volta:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [Funzione GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
