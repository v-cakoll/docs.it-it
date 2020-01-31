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
ms.openlocfilehash: f4bacfe94178ea78b1c3afd15a2e100076c38a84
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777992"
---
# <a name="icordebugchain-interface"></a>Interfaccia ICorDebugChain

Rappresenta un segmento di uno stack di chiamate fisico o logico.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateFrames](icordebugchain-enumerateframes-method.md)|Ottiene un enumeratore che contiene tutti gli stack frame gestiti nella catena, a partire dal frame più recente.|  
|[Metodo GetActiveFrame](icordebugchain-getactiveframe-method.md)|Ottiene il frame attivo (ovvero, più recente) nella catena.|  
|[Metodo GetCallee](icordebugchain-getcallee-method.md)|Ottiene la catena chiamata dalla catena.|  
|[Metodo GetCaller](icordebugchain-getcaller-method.md)|Ottiene la catena che ha chiamato questa catena.|  
|[Metodo GetContext](icordebugchain-getcontext-method.md)|Non implementato.|  
|[Metodo GetNext](icordebugchain-getnext-method.md)|Ottiene la catena di frame successiva per il thread.|  
|[Metodo GetPrevious](icordebugchain-getprevious-method.md)|Ottiene la catena di fotogrammi precedente per il thread.|  
|[Metodo GetReason](icordebugchain-getreason-method.md)|Ottiene il motivo per la genesi della catena chiamante.|  
|[Metodo GetRegisterSet](icordebugchain-getregisterset-method.md)|Ottiene il set di registri per la parte attiva della catena.|  
|[Metodo GetStackRange](icordebugchain-getstackrange-method.md)|Ottiene l'intervallo di indirizzi del segmento dello stack per questa catena.|  
|[Metodo GetThread](icordebugchain-getthread-method.md)|Ottiene il thread fisico di cui fa parte questa catena di chiamate.|  
|[Metodo IsManaged](icordebugchain-ismanaged-method.md)|Ottiene un valore che indica se la catena sta eseguendo codice gestito.|  
  
## <a name="remarks"></a>Note  
 Gli stack frame in una catena occupano lo spazio dello stack contiguo e condividono lo stesso thread e lo stesso contesto. Una catena può rappresentare catene di codice gestite o non gestite. Un'istanza di `ICorDebugChain` vuota rappresenta una catena di codice non gestita.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
