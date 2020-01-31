---
title: Interfaccia ICorDebugVariableHomeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
ms.openlocfilehash: 74b3c7bed54f3735efbd5d2c56962d427518f71a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790940"
---
# <a name="icordebugvariablehomeenum-interface"></a>Interfaccia ICorDebugVariableHomeEnum
Fornisce un enumeratore per le variabili e gli argomenti locali in una funzione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](icordebugvariablehomeenum-next-method.md)|Ottiene il numero specificato di istanze di [ICorDebugVariableHome](icordebugvariablehome-interface.md) che contengono informazioni sulle variabili e gli argomenti locali in una funzione.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugVariableHomeEnum` implementa l'interfaccia ICorDebugEnum.  
  
 Un'istanza di `ICorDebugVariableHomeEnum` viene popolata con istanze [ICorDebugVariableHome](icordebugvariablehome-interface.md) chiamando il metodo [interfacce icordebugcode4:: EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) . Ogni istanza di [ICorDebugVariableHome](icordebugvariablehome-interface.md) nell'insieme rappresenta una variabile o un argomento locale in una funzione. Gli oggetti [ICorDebugVariableHome](icordebugvariablehome-interface.md) della raccolta possono essere enumerati chiamando il metodo [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) .  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
