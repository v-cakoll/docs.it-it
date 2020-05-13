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
ms.openlocfilehash: f095bc0272e0e6f16467b9758d5e392d371139dd
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212685"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>Metodo ICorDebugManagedCallback::LogSwitch
Notifica al debugger che un thread gestito di Common Language Runtime (CLR) ha chiamato un metodo nella <xref:System.Diagnostics.Switch> classe per creare, modificare o eliminare un'opzione di debug/traccia.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread gestito che ha creato, modificato o eliminato un'opzione di debug/traccia.  
  
 `pThread`  
 in Puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.  
  
 `lLevel`  
 in Valore che indica il livello di gravità del messaggio descrittivo che è stato scritto nel log eventi.  
  
 `ulReason`  
 in Valore dell'enumerazione [LogSwitchCallReason](logswitchcallreason-enumeration.md) che indica l'operazione eseguita sull'opzione di debug/traccia.  
  
 `pLogSwitchName`  
 in Puntatore al nome dell'opzione di debug/traccia.  
  
 `pParentName`  
 in Puntatore al nome dell'elemento padre dell'opzione di debug/traccia.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
