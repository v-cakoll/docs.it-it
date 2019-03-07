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
ms.openlocfilehash: cd5e30d08e667dcd5a8be1f9502462f28290068e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494220"
---
# <a name="icordebugprocessgethelperthreadid-method"></a>Metodo ICorDebugProcess::GetHelperThreadID
Ottiene l'ID di thread del sistema operativo (OS) del thread di supporto interno del debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pThreadID`  
 [out] ID del thread di supporto interno del debugger di thread di un puntatore al sistema operativo.  
  
## <a name="remarks"></a>Note  
 Durante il debug gestito e non gestito, è responsabilità del debugger per garantire che il thread con l'ID specificato rimanga in esecuzione se raggiunge un punto di interruzione inserito dal debugger. Un debugger può anche scegliere di nascondere questo thread da parte dell'utente. Se l'helper esiste ancora alcun thread nel processo, il `GetHelperThreadID` metodo viene restituito zero in *`pThreadID`.  
  
 È possibile memorizzare nella cache dell'ID del thread di helper, perché può cambiare nel corso del tempo. È necessario ripetere la query l'ID del thread in corrispondenza di ogni evento di arresto.  
  
 L'ID del thread del thread di supporto del debugger saranno corretto in ogni non gestito [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) eventi, consentendo in tal modo un debugger determinare l'ID del thread del suo thread helper e lo nasconde da parte dell'utente. Un thread in cui viene identificato come un thread di supporto durante una funzione non gestita `ICorDebugManagedCallback::CreateThread` evento non verrà mai eseguito il codice utente gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl. Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
