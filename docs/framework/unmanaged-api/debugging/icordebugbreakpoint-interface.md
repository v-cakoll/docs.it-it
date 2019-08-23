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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 608c2cea79c20a43d65fcbf37ba13242fa465100
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969320"
---
# <a name="icordebugbreakpoint-interface"></a>Interfaccia ICorDebugBreakpoint

Rappresenta un punto di interruzione in una funzione o un punto di controllo su un valore.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Activate](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|Imposta lo stato attivo di questo `ICorDebugBreakpoint`oggetto.|  
|[Metodo IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|Ottiene un valore che indica se l' `ICorDebugBreakpoint` oggetto è attivo.|  
  
## <a name="remarks"></a>Note  
 I punti di interruzione non supportano direttamente le espressioni condizionali. Se si desidera una funzionalità di `ICorDebugBreakpoint`questo tipo, un debugger deve implementarlo oltre a.  
  
 L'interfaccia ICorDebugFunctionBreakpoint si `ICorDebugBreakpoint` estende per supportare i punti di interruzione all'interno di funzioni.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
