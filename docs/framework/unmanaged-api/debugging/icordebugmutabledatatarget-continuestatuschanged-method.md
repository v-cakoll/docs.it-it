---
title: Metodo ICorDebugMutableDataTarget::ContinueStatusChanged
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2f4f3890f2cfb2e3b017b8c7d0705d8c8e063957
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a>Metodo ICorDebugMutableDataTarget::ContinueStatusChanged
Modifica lo stato di continuazione per l'evento di debug in sospeso sul thread specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwThreadId`  
 Identificatore del thread definito dal sistema operativo.  
  
 `continueStatus`  
 Oggetto[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)valore che rappresenta il nuovo stato di continuazione richiesto.  
  
## <a name="remarks"></a>Note  
 Il debugger chiama il metodo `ContinueStatusChanged` quando chiama un metodo ICorDebug che richiede di gestire l'evento di debug corrente in modo potenzialmente diverso da quello in cui verrebbe gestito di solito. Ad esempio, se si verifica un'eccezione in sospeso e il debugger richiede un'operazione che annullerebbe l'accezione (ad esempio [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o `FuncEval`), questa API viene usata per richiedere che l'eccezione venga annullata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugMutableDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
