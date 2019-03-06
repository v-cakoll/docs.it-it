---
title: Metodo ICorDebugExceptionDebugEvent::GetStackPointer
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f5ea632ad8a7dd2e24e71742223936b01298f31
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485154"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a>Metodo ICorDebugExceptionDebugEvent::GetStackPointer
Ottiene il puntatore dello stack per questo evento di debug per le eccezioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pStackPointer`  
 [out] Puntatore all'indirizzo del puntatore dello stack per l'attuale evento di debug per le eccezioni. Per altre informazioni, vedere la sezione Osservazioni.  
  
## <a name="remarks"></a>Note  
 Il significato di questo puntatore dello stack dipende dal tipo di evento, come illustrato nella tabella seguente.  
  
|Tipo evento|Significato del valore `pStackPointer`|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Puntatore dello stack per il frame che ha generato l'eccezione.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Puntatore dello stack per il frame di codice utente più vicino al punto dell'eccezione generata.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Puntatore dello stack per il frame che contiene il gestore catch.|  
|[MANAGED_EXCEPTION_UNHANDLED](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|`pStackPointer` è **null**.|  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
 Il tipo di evento è disponibile il [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugExceptionDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
