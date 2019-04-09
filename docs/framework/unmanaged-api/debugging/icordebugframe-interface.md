---
title: Interfaccia ICorDebugFrame
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a15d7f16676b8b9d66f8d1ba7484f3fec5735a44
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222568"
---
# <a name="icordebugframe-interface"></a>Interfaccia ICorDebugFrame

Rappresenta un frame sullo stack corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Ottiene un oggetto ICorDebugStepper per eseguire operazioni di debug passo a passo in base a questa `ICorDebugFrame`.|  
|[Metodo GetCallee](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Ottiene un puntatore per il `ICorDebugFrame` nella catena di corrente che questo frame chiamato, o restituisce null se questo è il frame più interno nella catena.|  
|[Metodo GetCaller](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Ottiene un puntatore per il `ICorDebugFrame` nella catena di corrente che ha chiamato questo frame, o restituisce null se questo è il frame più esterno della catena.|  
|[Metodo GetChain](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Ottiene un puntatore a ICorDebugChain si `ICorDebugFrame` fa parte di.|  
|[Metodo GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Ottiene un puntatore all'oggetto ICorDebugCode associato a questo frame dello stack.|  
|[Metodo GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Ottiene un puntatore alla funzione ICorDebugFunction che contiene il codice associato a questo frame dello stack.|  
|[Metodo GetFunctionToken](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Ottiene il token di metadati per la funzione che contiene il codice associato a questo frame dello stack.|  
|[Metodo GetStackRange](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Ottiene l'intervallo di indirizzi assoluti dello stack frame rappresentato da questo `ICorDebugFrame`.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
