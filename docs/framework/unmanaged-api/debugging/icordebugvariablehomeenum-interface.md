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
ms.openlocfilehash: d5962de8cc2762f6ecf4864c5255da0fe83918e4
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396523"
---
# <a name="icordebugvariablehomeenum-interface"></a>Interfaccia ICorDebugVariableHomeEnum
Fornisce un enumeratore per le variabili e gli argomenti locali in una funzione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](icordebugvariablehomeenum-next-method.md)|Ottiene il numero specificato di istanze di [ICorDebugVariableHome](icordebugvariablehome-interface.md) che contengono informazioni sulle variabili e gli argomenti locali in una funzione.|  
  
## <a name="remarks"></a>Commenti  
 L' `ICorDebugVariableHomeEnum` interfaccia implementa l'interfaccia ICorDebugEnum.  
  
 Un' `ICorDebugVariableHomeEnum` istanza viene popolata con istanze [ICorDebugVariableHome](icordebugvariablehome-interface.md) chiamando il metodo [interfacce icordebugcode4:: EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) . Ogni istanza di [ICorDebugVariableHome](icordebugvariablehome-interface.md) nell'insieme rappresenta una variabile o un argomento locale in una funzione. Gli oggetti [ICorDebugVariableHome](icordebugvariablehome-interface.md) della raccolta possono essere enumerati chiamando il metodo [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
