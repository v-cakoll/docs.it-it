---
title: Interfaccia ICorDebugChain
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01dded47fca26df11781153eb45693057a25ad01
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220708"
---
# <a name="icordebugchain-interface"></a>Interfaccia ICorDebugChain

Rappresenta un segmento di uno stack di chiamate fisico o logico.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Ottiene un enumeratore contenente tutti gli stack frame gestiti nella catena, inizia con il frame più recente.|  
|[Metodo GetActiveFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Ottiene attivo (vale a dire più recente) frame della catena.|  
|[Metodo GetCallee](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Ottiene la catena di chiamata da questa catena.|  
|[Metodo GetCaller](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Ottiene la catena che ha chiamato questa catena.|  
|[Metodo GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Non implementato.|  
|[Metodo GetNext](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Ottiene la catena di frame successiva per il thread.|  
|[Metodo GetPrevious](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Ottiene la catena di frame precedente per il thread.|  
|[Metodo GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Ottiene il motivo per la creazione di questa catena di chiamata.|  
|[Metodo GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Ottiene il set per la parte attiva di questa catena di registri.|  
|[Metodo GetStackRange](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Ottiene l'intervallo di indirizzi del segmento di stack per questa catena.|  
|[Metodo GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Ottiene il thread fisico che questa catena di chiamate è parte di.|  
|[Metodo IsManaged](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Ottiene un valore che indica se questa catena esegue codice gestito.|  
  
## <a name="remarks"></a>Note  
 Gli stack frame in una catena di occupano lo spazio dello stack contigue e condividono lo stesso thread e contesto. Una catena può rappresentare uno catene di codice gestito o. Un oggetto vuoto `ICorDebugChain` istanza rappresenta una catena di codice non gestito.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
