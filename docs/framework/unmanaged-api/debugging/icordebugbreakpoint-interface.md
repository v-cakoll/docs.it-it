---
title: ICorDebugBreakpoint Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpoint
helpviewer_keywords: ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b78b61b99fb8f236e787f3acbf993d0a1c57e797
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugbreakpoint-interface1"></a>ICorDebugBreakpoint Interface1
Rappresenta un punto di interruzione in una funzione o un punto di controllo su un valore.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Activate (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|Imposta lo stato attivo di questo `ICorDebugBreakpoint`.|  
|[IsActive (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|Ottiene un valore che indica se questo `ICorDebugBreakpoint` è attiva.|  
  
## <a name="remarks"></a>Note  
 I punti di interruzione non supportano direttamente le espressioni condizionali. Se si desidera tale funzionalità, un debugger deve implementarla in cima `ICorDebugBreakpoint`.  
  
 Estende l'interfaccia ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` per supportare i punti di interruzione all'interno di funzioni.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
