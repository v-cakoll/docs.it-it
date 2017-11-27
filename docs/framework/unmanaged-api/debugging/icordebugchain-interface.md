---
title: ICorDebugChain Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain
helpviewer_keywords: ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f964b5390e601b518acad44dd6fd170399ff0af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchain-interface1"></a>ICorDebugChain Interface1
Rappresenta un segmento di uno stack di chiamate fisico o logico.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[EnumerateFrames (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Ottiene un enumeratore che contiene tutti gli stack frame gestiti nella catena, a partire dal frame più recente.|  
|[GetActiveFrame (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Ottiene attivo (vale a dire più recente) frame sulla catena.|  
|[GetCallee (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Ottiene la catena di chiamata da questa catena.|  
|[GetCaller (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Ottiene la catena che ha chiamato questa catena.|  
|[GetContext (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Non implementato.|  
|[GetNext (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Ottiene la catena di frame successiva per il thread.|  
|[GetPrevious (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Ottiene la catena di frame precedente per il thread.|  
|[GetReason (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Ottiene il motivo per la creazione di questa catena di chiamata.|  
|[GetRegisterSet (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Ottiene l'insieme di registri per la parte della catena attiva.|  
|[GetStackRange (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Ottiene l'intervallo di indirizzi del segmento di stack per questa catena.|  
|[GetThread (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Ottiene il thread fisico che questa catena di chiamate è parte di.|  
|[IsManaged (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Ottiene un valore che indica se la catena è in esecuzione il codice gestito.|  
  
## <a name="remarks"></a>Note  
 Gli stack frame in una catena occupano spazio stack contiguo e condividono lo stesso thread e lo stesso contesto. Una catena può rappresentare uno catene di codice gestito o. Un oggetto vuoto `ICorDebugChain` istanza rappresenta una catena di codice non gestito.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
