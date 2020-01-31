---
title: Interfaccia ICorDebugExceptionObjectCallStackEnum
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: 9d98bccdfb83cec547b185693c28f25017d3225f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782803"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a>Interfaccia ICorDebugExceptionObjectCallStackEnum
Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione. Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md)|Ottiene un numero specificato di oggetti [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) che contengono informazioni sullo stack di chiamate di un oggetto eccezione.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugExceptionObjectCallStackEnum` implementa l'interfaccia ICorDebugEnum.  
  
 Un'istanza di `ICorDebugExceptionObjectCallStackEnum` viene popolata con gli oggetti [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) chiamando il metodo [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) . È possibile enumerare gli elementi dello stack di chiamate nella raccolta chiamando il metodo [ICorDebugExceptionObjectCallStackEnum:: Next](icordebugexceptionobjectcallstackenum-next-method.md)  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
