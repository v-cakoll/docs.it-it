---
title: Metodo ICorDebugProcess::GetHelperThreadID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c3f879e04a710d65f812a5165c3edbfa31f8542
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocessgethelperthreadid-method"></a>Metodo ICorDebugProcess::GetHelperThreadID
Ottiene l'ID di thread del sistema operativo () del thread di supporto interno del debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pThreadID`  
 [out] ID del thread di supporto interno del debugger di thread di un puntatore al sistema operativo.  
  
## <a name="remarks"></a>Note  
 Durante il debug gestito e non gestito, è responsabilità del debugger per assicurarsi che il thread con l'ID specificato rimane in esecuzione se rilevato un punto di interruzione inserito dal debugger. Un debugger può anche scegliere di nascondere questo thread da parte dell'utente. Se nessun thread di supporto nel processo non esiste ancora, la `GetHelperThreadID` metodo restituirà zero in *`pThreadID`.  
  
 È possibile memorizzare nella cache l'ID del thread di supporto, perché può cambiare nel tempo. È necessario eseguire una query nuovamente l'ID di thread a ogni evento di arresto.  
  
 L'ID di thread del thread di supporto del debugger sarà corretto in ogni non gestito [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) evento, consentendo in tal modo un debugger determinare l'ID del thread di supporto e di nasconderlo da parte dell'utente. Un thread che durante una funzione non gestita viene identificato come un thread di supporto `ICorDebugManagedCallback::CreateThread` evento non verrà mai eseguito codice utente gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl. Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
