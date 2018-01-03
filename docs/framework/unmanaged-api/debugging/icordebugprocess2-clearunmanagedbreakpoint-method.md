---
title: Metodo ICorDebugProcess2::ClearUnmanagedBreakpoint
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 14258ef1ae473fc867d86c89ec877ddbf8c80213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>Metodo ICorDebugProcess2::ClearUnmanagedBreakpoint
Rimuove un impostata in precedenza punto di interruzione in corrispondenza dell'indirizzo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `address`  
 [in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo in cui è stato impostato il punto di interruzione.  
  
## <a name="remarks"></a>Note  
 Il punto di interruzione specificato sarebbe stato impostato precedentemente da una precedente chiamata a [ICorDebugProcess2::](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Il `ClearUnmanagedBreakpoint` metodo può essere chiamato mentre è in esecuzione il processo sottoposto a debug.  
  
 Il `ClearUnmanagedBreakpoint` metodo restituisce un codice di errore se il debugger è collegato in modalità solo gestito o se è presente alcun punto di interruzione in corrispondenza dell'indirizzo specificato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
