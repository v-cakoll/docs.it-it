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
ms.openlocfilehash: d38a59b23d47cbaf57dc21e121d56530a514d354
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128853"
---
# <a name="icordebugprocessgethelperthreadid-method"></a>Metodo ICorDebugProcess::GetHelperThreadID
Ottiene l'ID del thread del sistema operativo del thread helper interno del debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pThreadID`  
 out Puntatore all'ID del thread del sistema operativo del thread helper interno del debugger.  
  
## <a name="remarks"></a>Note  
 Durante il debug gestito e non gestito, è responsabilità del debugger garantire che il thread con l'ID specificato rimanga in esecuzione se raggiunge un punto di interruzione inserito dal debugger. Un debugger può anche voler nascondere questo thread dall'utente. Se nel processo non è ancora presente alcun thread helper, il metodo `GetHelperThreadID` restituisce zero in *`pThreadID`.  
  
 Non è possibile memorizzare nella cache l'ID del thread di supporto perché potrebbe cambiare nel tempo. È necessario eseguire di nuovo la query sull'ID del thread a ogni evento di interruzione.  
  
 L'ID thread del thread helper del debugger sarà corretto in ogni evento [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) non gestito, consentendo così a un debugger di determinare l'ID del thread del relativo thread helper e di nasconderlo dall'utente. Un thread identificato come thread Helper durante un evento `ICorDebugManagedCallback::CreateThread` non gestito non eseguirà mai codice utente gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl. CorDebug. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
