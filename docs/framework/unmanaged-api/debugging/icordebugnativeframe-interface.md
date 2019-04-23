---
title: Interfaccia ICorDebugNativeFrame
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d59450540b680d6004c47fd646769e38c806024
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161265"
---
# <a name="icordebugnativeframe-interface"></a>Interfaccia ICorDebugNativeFrame

Implementazione specializzata di ICorDebugFrame usato per i frame nativi.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CanSetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|Ottiene un valore che indica se è sicuro impostare il puntatore all'istruzione alla posizione di offset specificata nel codice nativo.|  
|[Metodo GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|Ottiene l'offset del frame dello stack nel codice nativo.|  
|[Metodo GetLocalDoubleRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Ottiene un puntatore a un'interfaccia ICorDebugValue che rappresenta il valore di un argomento o una variabile locale archiviata in due registri di memoria di un frame nativo.|  
|[Metodo GetLocalMemoryRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di una variabile locale, in cui i bit meno significativi vengono archiviati nel registro specificato e i bit più significativi sono archiviati in corrispondenza dell'indirizzo di memoria specificato.|  
|[Metodo GetLocalMemoryValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di una variabile locale archiviata nell'indirizzo di memoria specificato.|  
|[Metodo GetLocalRegisterMemoryValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di una variabile locale, in cui i bit più significativi vengono archiviati nel registro specificato e i bit meno significativi vengono archiviati in corrispondenza dell'indirizzo di memoria specificato|  
|[Metodo GetLocalRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di un argomento o una variabile locale archiviata nel registro nativo specificato.|  
|[Metodo GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|Ottiene un puntatore a un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) che rappresenta il set di registri di questo `ICorDebugNativeFrame`.|  
|[Metodo SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|Imposta il puntatore all'istruzione alla posizione di offset specificata nel codice nativo.|  
  
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
