---
title: Interfaccia ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: dfa65aa1b63c996068e75ff1165111d5fcfe77eb
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976005"
---
# <a name="icordebugexceptiondebugevent-interface"></a>Interfaccia ICorDebugExceptionDebugEvent
Estende l'interfaccia [ICorDebugDebugEvent](icordebugdebugevent-interface.md) per supportare gli eventi di eccezione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetFlags](icordebugexceptiondebugevent-getflags-method.md)|Ottiene un flag che indica se è possibile intercettare l'eccezione.|  
|[Metodo GetNativeIP](icordebugexceptiondebugevent-getnativeip-method.md)|Ottiene il puntatore all'interfaccia nativa per questo evento di debug per le eccezioni.|  
|[Metodo GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md)|Ottiene il puntatore dello stack per questo evento di debug per le eccezioni.|  
  
## <a name="remarks"></a>Osservazioni  
 L'interfaccia `ICorDebugExceptionDebugEvent` è implementata dai tipi di evento seguenti:  
  
- [MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)  
  
- [MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)  
  
- [MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)  
  
- [MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> L'interfaccia è disponibile solo con .NET Native. Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
