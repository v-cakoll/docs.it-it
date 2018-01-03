---
title: ICorDebugNativeFrame Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame
helpviewer_keywords: ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edd49d745be9db0c4c5309cf5febc3ff651a860f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe-interface1"></a>ICorDebugNativeFrame Interface1
Implementazione specializzata di ICorDebugFrame utilizzata per frame nativi.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CanSetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|Ottiene un valore che indica se è possibile impostare il puntatore all'istruzione alla posizione di offset specificata in codice nativo.|  
|[Metodo GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|Ottiene l'offset del frame dello stack nel codice nativo.|  
|[Metodo GetLocalDoubleRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Ottiene un puntatore a un oggetto ICorDebugValue che rappresenta il valore di un argomento o una variabile locale archiviata in due registri di memoria di un frame nativo.|  
|[Metodo GetLocalMemoryRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di una variabile locale, in cui bit meno significativi vengono archiviati nel registro specificato e i bit più significativi sono archiviati in corrispondenza dell'indirizzo di memoria specificata.|  
|[Metodo GetLocalMemoryValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di una variabile locale archiviata nell'indirizzo di memoria specificata.|  
|[Metodo GetLocalRegisterMemoryValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di una variabile locale, in cui i bit più significativi sono archiviati nel registro specificato e il bit meno significativi vengono archiviati in corrispondenza dell'indirizzo di memoria specificata|  
|[Metodo GetLocalRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di un argomento o una variabile locale archiviata nel registro nativo specificato.|  
|[Metodo GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|Ottiene un puntatore a un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) che rappresenta il set di registri di questo `ICorDebugNativeFrame`.|  
|[Metodo SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|Imposta il puntatore all'istruzione alla posizione di offset specificata nel codice nativo.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
