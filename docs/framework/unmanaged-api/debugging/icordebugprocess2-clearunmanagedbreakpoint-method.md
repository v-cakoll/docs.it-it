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
ms.openlocfilehash: 2b228383c3b393fe43f60d39e59cca37af36233f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212490"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>Metodo ICorDebugProcess2::ClearUnmanagedBreakpoint
Rimuove un punto di interruzione impostato in precedenza in corrispondenza dell'indirizzo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 in `CORDB_ADDRESS`Valore che specifica l'indirizzo in corrispondenza del quale è stato impostato il punto di interruzione.  
  
## <a name="remarks"></a>Osservazioni  
 Il punto di interruzione specificato è stato impostato in precedenza da una chiamata precedente a [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Il `ClearUnmanagedBreakpoint` metodo può essere chiamato mentre è in esecuzione il processo di cui è in corso il debug.  
  
 Il `ClearUnmanagedBreakpoint` metodo restituisce un codice di errore se il debugger è collegato in modalità solo gestito oppure se non esiste alcun punto di interruzione nell'indirizzo specificato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
