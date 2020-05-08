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
ms.openlocfilehash: e6dd951b0f432d455d95bb60f4c42df64d5bee24
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975992"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a>Interfaccia ICorDebugExceptionObjectCallStackEnum
Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione. Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ICorDebugExceptionObjectCallStackEnum:: Next](icordebugexceptionobjectcallstackenum-next-method.md)|Ottiene un numero specificato di oggetti [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) che contengono informazioni sullo stack di chiamate di un oggetto eccezione.|  
  
## <a name="remarks"></a>Osservazioni  
 L' `ICorDebugExceptionObjectCallStackEnum` interfaccia implementa l'interfaccia ICorDebugEnum.  
  
 Un' `ICorDebugExceptionObjectCallStackEnum` istanza viene popolata con gli oggetti [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) chiamando il metodo [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) . È possibile enumerare gli elementi dello stack di chiamate nella raccolta chiamando il metodo [ICorDebugExceptionObjectCallStackEnum:: Next](icordebugexceptionobjectcallstackenum-next-method.md)  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
