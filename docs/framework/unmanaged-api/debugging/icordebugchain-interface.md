---
title: ICorDebugChain Interface1
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
ms.openlocfilehash: 32889a8e8867fc42b48413463095dda423f26b85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugchain-interface1"></a>ICorDebugChain Interface1
Rappresenta un segmento di uno stack di chiamate fisico o logico.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Ottiene un enumeratore che contiene tutti gli stack frame gestiti nella catena, a partire dal frame più recente.|  
|[Metodo GetActiveFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Ottiene attivo (vale a dire più recente) frame sulla catena.|  
|[Metodo GetCallee](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Ottiene la catena di chiamata da questa catena.|  
|[Metodo GetCaller](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Ottiene la catena che ha chiamato questa catena.|  
|[Metodo GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Non implementato.|  
|[Metodo GetNext](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Ottiene la catena di frame successiva per il thread.|  
|[Metodo GetPrevious](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Ottiene la catena di frame precedente per il thread.|  
|[Metodo GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Ottiene il motivo per la creazione di questa catena di chiamata.|  
|[Metodo GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Ottiene l'insieme di registri per la parte della catena attiva.|  
|[Metodo GetStackRange](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Ottiene l'intervallo di indirizzi del segmento di stack per questa catena.|  
|[Metodo GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Ottiene il thread fisico che questa catena di chiamate è parte di.|  
|[Metodo IsManaged](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Ottiene un valore che indica se la catena è in esecuzione il codice gestito.|  
  
## <a name="remarks"></a>Note  
 Gli stack frame in una catena occupano spazio stack contiguo e condividono lo stesso thread e lo stesso contesto. Una catena può rappresentare uno catene di codice gestito o. Un oggetto vuoto `ICorDebugChain` istanza rappresenta una catena di codice non gestito.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
