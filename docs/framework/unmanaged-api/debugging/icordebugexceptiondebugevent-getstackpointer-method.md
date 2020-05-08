---
title: Metodo ICorDebugExceptionDebugEvent::GetStackPointer
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 4f84183dfc23ebc0d0fee9feeb21329c217b9cca
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976018"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a>Metodo ICorDebugExceptionDebugEvent::GetStackPointer
Ottiene il puntatore dello stack per questo evento di debug per le eccezioni.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pStackPointer`  
 [out] Puntatore all'indirizzo del puntatore dello stack per l'attuale evento di debug per le eccezioni. Per ulteriori informazioni, vedere le sezione Note.  
  
## <a name="remarks"></a>Osservazioni  
 Il significato di questo puntatore dello stack dipende dal tipo di evento, come illustrato nella tabella seguente.  
  
|Tipo di evento|Significato del valore `pStackPointer`|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Puntatore dello stack per il frame che ha generato l'eccezione.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Puntatore dello stack per il frame di codice utente più vicino al punto dell'eccezione generata.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)|Puntatore dello stack per il frame che contiene il gestore catch.|  
|[MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)|`pStackPointer` è **Null**.|  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
 Il tipo di evento è disponibile dal metodo [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
