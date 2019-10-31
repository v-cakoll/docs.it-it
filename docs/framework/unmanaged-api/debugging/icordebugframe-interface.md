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
ms.openlocfilehash: 5aeea11b7e61869968aafe3425e27d6004f495ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124069"
---
# <a name="icordebugframe-interface"></a>Interfaccia ICorDebugFrame

Rappresenta un frame sullo stack corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Ottiene un ICorDebugStepper per eseguire operazioni di esecuzione dell'istruzione rispetto a questo `ICorDebugFrame`.|  
|[Metodo GetCallee](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Ottiene un puntatore al `ICorDebugFrame` nella catena corrente che questo frame ha chiamato oppure restituisce null se si tratta del frame più interno nella catena.|  
|[Metodo GetCaller](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Ottiene un puntatore al `ICorDebugFrame` nella catena corrente che ha chiamato questo frame oppure restituisce null se si tratta del frame più esterno nella catena.|  
|[Metodo GetChain](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Ottiene un puntatore a ICorDebugChain di cui questo `ICorDebugFrame` fa parte.|  
|[Metodo GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Ottiene un puntatore all'oggetto ICorDebugCode associato a questo stack frame.|  
|[Metodo GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Ottiene un puntatore a ICorDebugFunction che contiene il codice associato a questo stack frame.|  
|[Metodo GetFunctionToken](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Ottiene il token di metadati per la funzione che contiene il codice associato a questo stack frame.|  
|[Metodo GetStackRange](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Ottiene l'intervallo di indirizzi assoluto della stack frame rappresentata da questo `ICorDebugFrame`.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
