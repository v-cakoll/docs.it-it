---
title: ICorDebugFrame Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame
helpviewer_keywords: ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2acc825f6592eae80f67e7614ca45f175b6756d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframe-interface1"></a>ICorDebugFrame Interface1
Rappresenta un frame sullo stack corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CreateStepper (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Ottiene un oggetto ICorDebugStepper esegua operazioni di debug passo a passo in base a questa `ICorDebugFrame`.|  
|[GetCallee (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Ottiene un puntatore per il `ICorDebugFrame` nella catena di chiamata di questo frame oppure restituisce null se si tratta del frame più interno nella catena di corrente.|  
|[GetCaller (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Ottiene un puntatore per il `ICorDebugFrame` nella catena corrente che ha chiamato questo frame o restituisce null se questa è la cornice più esterna della catena.|  
|[GetChain (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Ottiene un puntatore a ICorDebugChain questo `ICorDebugFrame` fa parte di.|  
|[GetCode (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Ottiene un puntatore all'oggetto ICorDebugCode associata a questo stack frame.|  
|[GetFunction (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Ottiene un puntatore all'oggetto ICorDebugFunction che contiene il codice associato a questo stack frame.|  
|[GetFunctionToken (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Ottiene il token di metadati per la funzione che contiene il codice associato a questo stack frame.|  
|[GetStackRange (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Ottiene l'intervallo di indirizzi assoluti dello stack frame rappresentato da questo `ICorDebugFrame`.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
