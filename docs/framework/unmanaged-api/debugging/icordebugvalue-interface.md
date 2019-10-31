---
title: Interfaccia ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: 77d28d8eef97a934c15ac29725f856f4bf39e6ce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140151"
---
# <a name="icordebugvalue-interface"></a>Interfaccia ICorDebugValue
Rappresenta un valore nel processo di cui è in corso il debug. Il valore può essere un valore di lettura o di scrittura.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|Questo metodo non è attualmente implementato.|  
|[Metodo GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Ottiene l'indirizzo di questo `ICorDebugValue` oggetto, che è in fase di debug.|  
|[Metodo GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Ottiene le dimensioni in byte di questo oggetto `ICorDebugValue`.|  
|[Metodo GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Ottiene il tipo primitivo di questo oggetto `ICorDebugValue`.|  
  
## <a name="remarks"></a>Note  
 In generale, la proprietà di un oggetto valore viene passata quando viene restituito. Il destinatario è responsabile della rimozione di un riferimento dall'oggetto al termine dell'oggetto.  
  
 A seconda della posizione in cui è stato recuperato il valore, il valore potrebbe non rimanere valido dopo la ripresa del processo. Pertanto, in generale, il valore non deve essere mantenuto in una chiamata al metodo [ICorDebugController:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) .  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
