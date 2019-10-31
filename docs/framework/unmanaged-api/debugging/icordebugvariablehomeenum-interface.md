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
ms.openlocfilehash: a9b65449747fde42f9cd770e33741ef34d33fbb8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121028"
---
# <a name="icordebugvariablehomeenum-interface"></a>Interfaccia ICorDebugVariableHomeEnum
Fornisce un enumeratore per le variabili e gli argomenti locali in una funzione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|Ottiene il numero specificato di istanze di [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) che contengono informazioni sulle variabili e gli argomenti locali in una funzione.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugVariableHomeEnum` implementa l'interfaccia ICorDebugEnum.  
  
 Un'istanza di `ICorDebugVariableHomeEnum` viene popolata con istanze [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) chiamando il metodo [interfacce icordebugcode4:: EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) . Ogni istanza di [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) nell'insieme rappresenta una variabile o un argomento locale in una funzione. Gli oggetti [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) della raccolta possono essere enumerati chiamando il metodo [ICorDebugVariableHomeEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
