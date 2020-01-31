---
title: Interfaccia ICorDebugBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 53d8d219a13f2dade16a338efccf0837f8de0158
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784369"
---
# <a name="icordebugbreakpoint-interface"></a>Interfaccia ICorDebugBreakpoint

Rappresenta un punto di interruzione in una funzione o un punto di controllo su un valore.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Activate](icordebugbreakpoint-activate-method.md)|Imposta lo stato attivo di questo `ICorDebugBreakpoint`.|  
|[Metodo IsActive](icordebugbreakpoint-isactive-method.md)|Ottiene un valore che indica se questo `ICorDebugBreakpoint` è attivo.|  
  
## <a name="remarks"></a>Note  
 I punti di interruzione non supportano direttamente le espressioni condizionali. Se si desidera questa funzionalità, un debugger deve implementarlo sopra `ICorDebugBreakpoint`.  
  
 L'interfaccia ICorDebugFunctionBreakpoint estende `ICorDebugBreakpoint` per supportare i punti di interruzione all'interno di funzioni.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
