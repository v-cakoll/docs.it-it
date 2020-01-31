---
title: Metodo ICorDebugExceptionDebugEvent::GetNativeIP
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 31af92dae47027b7285b422a05014b081d7e39a2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788678"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a>Metodo ICorDebugExceptionDebugEvent::GetNativeIP
Ottiene il puntatore alle istruzioni native per questo evento di debug per le eccezioni.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pIP`  
 [out] Puntatore al puntatore alle istruzioni per l'attuale evento di debug per le eccezioni. Per altre informazioni, vedere la sezione Osservazioni.  
  
## <a name="remarks"></a>Note  
 Il significato di questo puntatore alle istruzioni dipende dal tipo di evento, come illustrato nella tabella seguente.  
  
|Tipo evento|Significato del valore `pStackPointer`|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|L'indirizzo dell'istruzione in errore.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Indirizzo del codice nel frame indicato dal metodo [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) in cui l'esecuzione riprende se non è stata generata alcuna eccezione. L'eccezione potrebbe determinare o non determinare codice diverso, ad esempio il blocco catch di una `try/catch/finally` che deve essere eseguito nel frame.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)|Indirizzo del codice in cui viene avviata l'esecuzione `catch` gestore nel frame indicato dal metodo [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) .|  
|[MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)|`pIP` è 0.|  
  
 Il tipo di evento è disponibile dal metodo [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
