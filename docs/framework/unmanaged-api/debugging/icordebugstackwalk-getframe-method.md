---
title: Metodo ICorDebugStackWalk::GetFrame
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.GetFrame Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bef8cfc13727913e9311b5ce847190fe5544dc18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalkgetframe-method"></a>Metodo ICorDebugStackWalk::GetFrame
Ottiene il frame corrente [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pFrame`  
 [in] Un puntatore all'indirizzo dell'oggetto che rappresenta il frame corrente nello stack frame creato.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il runtime restituito correttamente il frame corrente.|  
|E_FAIL|Non è stato restituito il frame corrente.|  
|S_FALSE|Il frame corrente è un frame dello stack nativo.|  
|E_INVALIDARG|`pFrame` è null.|  
|CORDBG_E_PAST_END_OF_STACK|Puntatore ai frame è già alla fine dello stack. Pertanto, non è possibile accedere ulteriori frame.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 `ICorDebugStackWalk`Restituisce solo gli stack frame effettivi. Utilizzare il [ICorDebugThread3:: GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) per restituire i frame interni. I frame interni sono strutture di dati nello stack dal runtime per archiviare dati temporanei.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugStackWalk (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
