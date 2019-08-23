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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6419a525a8a542295751defb97e67a83220730b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965072"
---
# <a name="icordebugregisterset-interface"></a>Interfaccia ICorDebugRegisterSet
Rappresenta il set di registri disponibili nel computer in cui è attualmente in esecuzione il codice.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|DESCRIZIONE|  
|------------|-----------------|  
|[Metodo GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione il codice) specificato dalla maschera di bit.|  
|[Metodo GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|Ottiene una maschera di bit che indica `ICorDebugRegisterSet` i registri attualmente disponibili.|  
|[Metodo GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|Ottiene il contesto del thread corrente.|  
|[Metodo SetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|Non implementato per la versione di .NET Framework 2,0.|  
|[Metodo SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|Non implementato per la .NET Framework 2,0.|  
  
## <a name="remarks"></a>Note  
 L' `ICorDebugRegisterSet` interfaccia supporta solo registri a 32 bit. Usare l'interfaccia [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) sulle piattaforme, ad esempio IA-64, che richiedono registri aggiuntivi.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Interfaccia ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
