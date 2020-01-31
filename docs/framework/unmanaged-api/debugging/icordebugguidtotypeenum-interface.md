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
ms.openlocfilehash: 2663e5604cdd55472cc148b2d2b38599df81f11e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794445"
---
# <a name="icordebugguidtotypeenum-interface"></a>Interfaccia ICorDebugGuidToTypeEnum
Fornisce un enumeratore che definisce il mapping tra un set di GUID e i tipi corrispondenti, rappresentati da istanze di ICorDebugType. Questa interfaccia eredita i metodi dall'interfaccia ICorDebugEnum.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ICorDebugGuidToTypeEnum::Next](icordebugguidtotypeenum-next-method.md)|Ottiene il numero specificato di istanze di [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) che mappano i GUID alle informazioni sul tipo.|  
  
## <a name="remarks"></a>Note  
 Un oggetto `ICorDebugGuidToTypeEnum` interfaccia può essere recuperato chiamando il metodo [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) . Un debugger può chiamare il metodo [successivo](icordebugguidtotypeenum-next-method.md) di questa interfaccia per recuperare gli oggetti [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) che rappresentano i mapping di rappresentazioni gestite dei tipi Windows Runtime caricati nel dominio applicazione usato per la chiamata al metodo [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) .  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** Windows Runtime  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
