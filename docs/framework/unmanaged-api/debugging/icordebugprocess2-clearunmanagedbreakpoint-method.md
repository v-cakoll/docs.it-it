---
title: Metodo ICorDebugProcess2::ClearUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fb566ff2e5e2b0bcb096cead243ed65a904a914
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736983"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>Metodo ICorDebugProcess2::ClearUnmanagedBreakpoint
Rimuove un impostato in precedenza punto di interruzione in corrispondenza dell'indirizzo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 [in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo in corrispondenza del quale è stato impostato il punto di interruzione.  
  
## <a name="remarks"></a>Note  
 Il punto di interruzione specificato sarebbe stato impostato precedentemente da una precedente chiamata a [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Il `ClearUnmanagedBreakpoint` metodo può essere chiamato mentre è in esecuzione il processo sottoposto a debug.  
  
 Il `ClearUnmanagedBreakpoint` metodo restituisce un codice di errore se il debugger è collegato in modalità "solo gestito" o se è presente alcun punto di interruzione in corrispondenza dell'indirizzo specificato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
