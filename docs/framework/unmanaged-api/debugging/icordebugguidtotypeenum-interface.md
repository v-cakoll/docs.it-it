---
title: Interfaccia ICorDebugGuidToTypeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: da921644c4d967efb0d88060ada0332c5eb63965
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138525"
---
# <a name="icordebugguidtotypeenum-interface"></a>Interfaccia ICorDebugGuidToTypeEnum
Fornisce un enumeratore che definisce il mapping tra un set di GUID e i tipi corrispondenti, rappresentati da istanze di ICorDebugType. Questa interfaccia eredita i metodi dall'interfaccia ICorDebugEnum.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ICorDebugGuidToTypeEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|Ottiene il numero specificato di istanze di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) che mappano i GUID alle informazioni sul tipo.|  
  
## <a name="remarks"></a>Note  
 Un oggetto `ICorDebugGuidToTypeEnum` interfaccia può essere recuperato chiamando il metodo [ICorDebugAppDomain3:: GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) . Un debugger può chiamare il metodo [successivo](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) di questa interfaccia per recuperare gli oggetti [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) che rappresentano i mapping di rappresentazioni gestite dei tipi Windows Runtime caricati nel dominio applicazione usato per la chiamata al [Metodo Metodo ICorDebugAppDomain3:: GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Windows Runtime  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
