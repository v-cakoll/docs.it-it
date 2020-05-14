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
ms.openlocfilehash: b8d2e49031e59db0527de3c848d7d390095797bf
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396783"
---
# <a name="icordebugvalue-interface"></a>Interfaccia ICorDebugValue
Rappresenta un valore nel processo di cui è in corso il debug. Il valore può essere un valore di lettura o di scrittura.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](icordebugvalue-createbreakpoint-method.md)|Non è attualmente implementato.|  
|[Metodo GetAddress](icordebugvalue-getaddress-method.md)|Ottiene l'indirizzo di questo `ICorDebugValue` oggetto, che è in fase di debug.|  
|[Metodo GetSize](icordebugvalue-getsize-method.md)|Ottiene le dimensioni in byte di questo `ICorDebugValue` oggetto.|  
|[Metodo GetType](icordebugvalue-gettype-method.md)|Ottiene il tipo primitivo di questo `ICorDebugValue` oggetto.|  
  
## <a name="remarks"></a>Commenti  
 In generale, la proprietà di un oggetto valore viene passata quando viene restituito. Il destinatario è responsabile della rimozione di un riferimento dall'oggetto al termine dell'oggetto.  
  
 A seconda della posizione in cui è stato recuperato il valore, il valore potrebbe non rimanere valido dopo la ripresa del processo. Pertanto, in generale, il valore non deve essere mantenuto in una chiamata al metodo [ICorDebugController:: continue](icordebugcontroller-continue-method.md) .  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugValue3](icordebugvalue3-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
