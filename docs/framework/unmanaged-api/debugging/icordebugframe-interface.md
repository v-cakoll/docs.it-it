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
ms.openlocfilehash: 9c2771d1338943406921447d96dd9a8748153a36
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209617"
---
# <a name="icordebugframe-interface"></a>Interfaccia ICorDebugFrame

Rappresenta un frame sullo stack corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateStepper](icordebugframe-createstepper-method.md)|Ottiene un ICorDebugStepper per eseguire operazioni di esecuzione dell'istruzione rispetto a questo `ICorDebugFrame` .|  
|[Metodo GetCallee](icordebugframe-getcallee-method.md)|Ottiene un puntatore all'oggetto `ICorDebugFrame` nella catena corrente chiamato da questo frame oppure restituisce null se si tratta del frame più interno nella catena.|  
|[Metodo GetCaller](icordebugframe-getcaller-method.md)|Ottiene un puntatore all'oggetto `ICorDebugFrame` nella catena corrente che ha chiamato questo frame oppure restituisce null se si tratta del frame più esterno nella catena.|  
|[Metodo GetChain](icordebugframe-getchain-method.md)|Ottiene un puntatore a ICorDebugChain di cui `ICorDebugFrame` fa parte.|  
|[Metodo GetCode](icordebugframe-getcode-method.md)|Ottiene un puntatore all'oggetto ICorDebugCode associato a questo stack frame.|  
|[Metodo GetFunction](icordebugframe-getfunction-method.md)|Ottiene un puntatore a ICorDebugFunction che contiene il codice associato a questo stack frame.|  
|[Metodo GetFunctionToken](icordebugframe-getfunctiontoken-method.md)|Ottiene il token di metadati per la funzione che contiene il codice associato a questo stack frame.|  
|[Metodo GetStackRange](icordebugframe-getstackrange-method.md)|Ottiene l'intervallo di indirizzi assoluto della stack frame rappresentata dall'oggetto `ICorDebugFrame` .|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
