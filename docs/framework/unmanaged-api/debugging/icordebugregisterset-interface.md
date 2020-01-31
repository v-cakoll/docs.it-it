---
title: Interfaccia ICorDebugRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: f435db28d5c85d576f69e7612841fc46ae142332
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792075"
---
# <a name="icordebugregisterset-interface"></a>Interfaccia ICorDebugRegisterSet
Rappresenta il set di registri disponibili nel computer in cui è attualmente in esecuzione il codice.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetRegisters](icordebugregisterset-getregisters-method.md)|Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione il codice) specificato dalla maschera di bit.|  
|[Metodo GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md)|Ottiene una maschera di bit che indica i registri in questo `ICorDebugRegisterSet` sono attualmente disponibili.|  
|[Metodo GetThreadContext](icordebugregisterset-getthreadcontext-method.md)|Ottiene il contesto del thread corrente.|  
|[Metodo SetRegisters](icordebugregisterset-setregisters-method.md)|Non implementato per la versione di .NET Framework 2,0.|  
|[Metodo SetThreadContext](icordebugregisterset-setthreadcontext-method.md)|Non implementato per la .NET Framework 2,0.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugRegisterSet` supporta solo registri a 32 bit. Usare l'interfaccia [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) sulle piattaforme, ad esempio IA-64, che richiedono registri aggiuntivi.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Interfaccia ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
