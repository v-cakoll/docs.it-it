---
title: Metodo ICLRDebugging::OpenVirtualProcess
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51b5a9ecd85f0d40ac2fe2826cbbe7a56a6228d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>Metodo ICLRDebugging::OpenVirtualProcess
Ottiene l'interfaccia ICorDebugProcess che corrisponde a un modulo common language runtime (CLR) caricato nel processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleBaseAddress`  
 [in] L'indirizzo di base di un modulo nel processo di destinazione. COR_E_NOT_CLR verrà restituito se il modulo specificato non è un modulo CLR.  
  
 `pDataTarget`  
 [in] Un'astrazione di destinazione dei dati che consente al debugger gestito controllare lo stato del processo. Il debugger deve implementare il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia. È necessario implementare la [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaccia per supportare scenari in cui il runtime che viene eseguito il debug non è installato localmente nel computer.  
  
 `pLibraryProvider`  
 [in] Un'interfaccia di callback provider libreria che consente di individuare e caricare su richiesta librerie di debug specifiche della versione. Questo parametro è obbligatorio solo se `ppProcess` o `pFlags` non `null`.  
  
 `pMaxDebuggerSupportedVersion`  
 [in] La versione più recente di questo debugger può eseguire il debug CLR. Si deve specificare la versione principale e secondario, compilare versioni dell'ultima versione di CLR che supporta e impostare il numero di revisione e 65535 per supportare Common Language Runtime sul posto di future Service Release.  
  
 `riidProcess`  
 [in] ID dell'interfaccia ICorDebugProcess da recuperare. Attualmente, i valori accettati sono solo IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 e IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 [out] Un puntatore a interfaccia COM che è identificato da `riidProcess`.  
  
 `pVersion`  
 [in, out] La versione di CLR. Per l'input, questo valore può essere `null`. Può inoltre puntare a un [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) struttura, nel qual caso la struttura `wStructVersion` campo deve essere inizializzato su 0 (zero).  
  
 Nell'output, l'oggetto restituito `CLR_DEBUGGING_VERSION` struttura verrà compilata con le informazioni sulla versione di CLR.  
  
 `pdwFlags`  
 [out] Contrassegni informativi sul runtime specificato. Vedere il [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) argomento per una descrizione dei flag.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pDataTarget` è `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|Il [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback restituisce un errore o non fornisce un handle valido.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget` non implementa le interfacce di destinazione i dati necessari per questa versione del runtime.|  
|CORDBG_E_NOT_CLR|Il modulo indicato non è un modulo CLR. Questo valore di HRESULT viene restituito anche quando un modulo CLR non può essere rilevato perché la memoria è stata danneggiata, il modulo non è disponibile o la versione CLR è successiva alla versione di shim.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Questa versione di runtime non supporta il modello di debug. Attualmente, il modello di debug non è supportato dalle versioni precedenti CLR il [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Il `pwszVersion` parametro di output è ancora impostato sul valore corretto dopo questo errore.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|La versione di CLR è maggiore della versione che per il supporto di attestazioni questo debugger. Il `pwszVersion` parametro di output è ancora impostato sul valore corretto dopo questo errore.|  
|E_NO_INTERFACE|Il `riidProcess` interfaccia non è disponibile.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|Il `CLR_DEBUGGING_VERSION` struttura non dispone di un valore riconosciuto per `wStructVersion`. L'unico valore ammesso in questa fase è 0.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
