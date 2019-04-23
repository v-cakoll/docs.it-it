---
title: Metodo ICorDebugManagedCallback::LogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a011485453999b9d764716356eebb2a5462f7bb9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078837"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>Metodo ICorDebugManagedCallback::LogSwitch
Notifica al debugger che un thread di common language runtime (CLR) gestito ha chiamato un metodo di <xref:System.Diagnostics.Switch> classe da creare, modificare o eliminare un'opzione di debug/traccia.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a>Parametri  
 `PAppDomain`  
 [in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread gestito creato, modificato o eliminato un'opzione di debug/traccia.  
  
 `pThread`  
 [in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.  
  
 `lLevel`  
 [in] Un valore che indica il livello di gravità del messaggio descrittivo che è stato scritto nel registro eventi.  
  
 `ulReason`  
 [in] Valore di [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumerazione che indica l'operazione eseguita sull'opzione di debug/traccia.  
  
 `pLogSwitchName`  
 [in] Un puntatore al nome del commutatore debug/traccia.  
  
 `pParentName`  
 [in] Un puntatore al nome dell'elemento padre dell'opzione di debug/traccia.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
