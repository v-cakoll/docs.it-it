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
ms.openlocfilehash: 0efda458d51677fcd16140cd0f0a835b76c20173
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617178"
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
 in Nome del file di configurazione associato a `pExe` .  
  
 `startupFlags`  
 in Uno o più valori dell'enumerazione [STARTUP_FLAGS](startup-flags-enumeration.md) .  
  
 `runtimeInfoFlags`  
 in Uno o più valori dell'enumerazione [RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md) .  
  
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
  
|Codice restituito|Description|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|ERROR_INSUFFICIENT_BUFFER|Il buffer di directory non è abbastanza grande per archiviare il percorso della directory.<br /><br /> - oppure -<br /><br /> Il buffer della versione non è abbastanza grande per archiviare la stringa di versione.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `GetRequestedRuntimeInfo` metodo restituisce informazioni in fase di esecuzione sulla versione caricata nel processo, che non è necessariamente la versione più recente installata nel computer.  
  
 Nel .NET Framework versione 2,0, è possibile ottenere informazioni sull'ultima versione installata usando il `GetRequestedRuntimeInfo` metodo come indicato di seguito:  
  
- Specificare i `pExe` `pwszVersion` parametri, e `pConfigurationFile` come null.  
  
- Specificare il flag di RUNTIME_INFO_UPGRADE_VERSION nelle `RUNTIME_INFO_FLAGS` enumerazioni per il `runtimeInfoFlags` parametro.  
  
 Il `GetRequestedRuntimeInfo` metodo non restituisce la versione più recente di CLR nelle circostanze seguenti:  
  
- Un file di configurazione dell'applicazione che specifica il caricamento di una determinata versione di CLR esiste. Si noti che il .NET Framework utilizzerà il file di configurazione anche se si specifica null per il `pConfigurationFile` parametro.  
  
- Il metodo [CorBindToRuntimeEx](corbindtoruntimeex-function.md) è stato chiamato specificando una versione precedente di CLR.  
  
- Un'applicazione compilata per una versione CLR precedente è attualmente in esecuzione.  
  
 Per il `runtimeInfoFlags` parametro, è possibile specificare solo una delle costanti di architettura dell' `RUNTIME_INFO_FLAGS` enumerazione alla volta:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md)
- [Funzione GetVersionFromProcess](getversionfromprocess-function.md)
- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
