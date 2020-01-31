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
ms.openlocfilehash: e1044386bd6251132703c4e98a0cf2ed267d34e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791142"
---
# <a name="icordebugvalue-interface"></a>Interfaccia ICorDebugValue
Rappresenta un valore nel processo di cui è in corso il debug. Il valore può essere un valore di lettura o di scrittura.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](icordebugvalue-createbreakpoint-method.md)|Non è attualmente implementato.|  
|[Metodo GetAddress](icordebugvalue-getaddress-method.md)|Ottiene l'indirizzo di questo `ICorDebugValue` oggetto, che è in fase di debug.|  
|[Metodo GetSize](icordebugvalue-getsize-method.md)|Ottiene le dimensioni in byte di questo oggetto `ICorDebugValue`.|  
|[Metodo GetType](icordebugvalue-gettype-method.md)|Ottiene il tipo primitivo di questo oggetto `ICorDebugValue`.|  
  
## <a name="remarks"></a>Note  
 In generale, la proprietà di un oggetto valore viene passata quando viene restituito. Il destinatario è responsabile della rimozione di un riferimento dall'oggetto al termine dell'oggetto.  
  
 A seconda della posizione in cui è stato recuperato il valore, il valore potrebbe non rimanere valido dopo la ripresa del processo. Pertanto, in generale, il valore non deve essere mantenuto in una chiamata al metodo [ICorDebugController:: continue](icordebugcontroller-continue-method.md) .  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugValue3](icordebugvalue3-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
