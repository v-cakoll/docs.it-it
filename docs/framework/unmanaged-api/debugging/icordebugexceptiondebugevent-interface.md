---
title: Interfaccia ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e2a147d46412eb4feb192070ff8420cab842a6c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156455"
---
# <a name="icordebugexceptiondebugevent-interface"></a>Interfaccia ICorDebugExceptionDebugEvent
Estende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi di eccezione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|Ottiene un flag che indica se è possibile intercettare l'eccezione.|  
|[Metodo GetNativeIP](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|Ottiene il puntatore all'interfaccia nativa per questo evento di debug per le eccezioni.|  
|[Metodo GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|Ottiene il puntatore dello stack per questo evento di debug per le eccezioni.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugExceptionDebugEvent` è implementata dai tipi di evento seguenti:  
  
-   [MANAGED_EXCEPTION_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [MANAGED_EXCEPTION_USER_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [MANAGED_EXCEPTION_UNHANDLED](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
>  L'interfaccia è disponibile solo con .NET Native. Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
