---
title: ICorDebugValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue
helpviewer_keywords: ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01c94df1d8e6ddef0110268461a2b28f594201b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue-interface1"></a>ICorDebugValue Interface1
Rappresenta un valore nel processo sottoposto a debug. Il valore può essere un'operazione di lettura o scrittura.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CreateBreakpoint (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|Questo metodo non è attualmente implementato.|  
|[GetAddress (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Ottiene l'indirizzo di questo `ICorDebugValue` oggetto, che è in corso il debug.|  
|[GetSize (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Ottiene le dimensioni, in byte, di questo `ICorDebugValue` oggetto.|  
|[GetType (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Ottiene il tipo primitivo di `ICorDebugValue` oggetto.|  
  
## <a name="remarks"></a>Note  
 In generale, la proprietà di un oggetto di valore viene passata quando viene restituita. Il destinatario è responsabile della rimozione di un riferimento dall'oggetto quando viene terminato con l'oggetto.  
  
 A seconda di dove è stato recuperato il valore da, il valore potrebbe non rimanere valido, dopo il processo viene ripreso. In tal caso, in generale, il valore non deve essere mantenuto in una chiamata di [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) metodo.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
    
    
    
    
 [ICorDebugValue3 (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
