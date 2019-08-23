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
ms.openlocfilehash: 93ada40bd88e53cd06f5e8d8136b2d527d7741e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969298"
---
# <a name="icordebugchain-interface"></a>Interfaccia ICorDebugChain

Rappresenta un segmento di uno stack di chiamate fisico o logico.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Ottiene un enumeratore che contiene tutti gli stack frame gestiti nella catena, a partire dal frame più recente.|  
|[Metodo GetActiveFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Ottiene il frame attivo (ovvero, più recente) nella catena.|  
|[Metodo GetCallee](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Ottiene la catena chiamata dalla catena.|  
|[Metodo GetCaller](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Ottiene la catena che ha chiamato questa catena.|  
|[Metodo GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Non implementato.|  
|[Metodo GetNext](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Ottiene la catena di frame successiva per il thread.|  
|[Metodo GetPrevious](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Ottiene la catena di fotogrammi precedente per il thread.|  
|[Metodo GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Ottiene il motivo per la genesi della catena chiamante.|  
|[Metodo GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Ottiene il set di registri per la parte attiva della catena.|  
|[Metodo GetStackRange](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Ottiene l'intervallo di indirizzi del segmento dello stack per questa catena.|  
|[Metodo GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Ottiene il thread fisico di cui fa parte questa catena di chiamate.|  
|[Metodo IsManaged](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Ottiene un valore che indica se la catena sta eseguendo codice gestito.|  
  
## <a name="remarks"></a>Note  
 Gli stack frame in una catena occupano lo spazio dello stack contiguo e condividono lo stesso thread e lo stesso contesto. Una catena può rappresentare catene di codice gestite o non gestite. Un'istanza `ICorDebugChain` vuota rappresenta una catena di codice non gestita.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
