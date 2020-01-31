---
title: Interfaccia ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: bef057bdb3ff0919337dd15f2d930159ddaf1bcf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783401"
---
# <a name="icordebugdebugevent-interface"></a>Interfaccia ICorDebugDebugEvent
Definisce l'interfaccia di base da cui derivano tutti gli evento di debug `ICorDebug`.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetEventKind](icordebugdebugevent-geteventkind-method.md)|Indica il tipo di evento rappresentato dall'oggetto `ICorDebugDebugEvent`.|  
|[Metodo GetThread](icordebugdebugevent-getthread-method.md)|Ottiene il thread in cui si è verificato l'evento.|  
  
## <a name="remarks"></a>Note  
 Le interfacce seguenti sono derivate dall'interfaccia `ICorDebugDebugEvent`:  
  
- [ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)  
  
- [ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> L'interfaccia è disponibile solo con .NET Native. Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
