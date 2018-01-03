---
title: Enumerazione CorDebugCodeInvokePurpose
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugInvokePurpose
api_location: mscordbi.dll
api_type: COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e87e5d8baf3ff7c87efe8f6bd96f8fd806527363
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a>Enumerazione CorDebugCodeInvokePurpose
Descrive il motivo per cui una funzione esportata chiama il codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|Nessuno o sconosciuto.|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|Il codice gestito esegue qualsiasi punto di ingresso gestito, ad esempio p-invoke inverso. Eventuali altri scopi più dettagliati non sono noti al runtime.|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|Il codice gestito esegue un costruttore statico.|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|Il codice gestito esegue l'implementazione per alcuni metodi dell'interfaccia chiamati.|  
  
## <a name="remarks"></a>Note  
 Questa enumerazione viene utilizzata per la [Icordebugprocess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) metodo per fornire informazioni sull'avanzamento tramite codice gestito.  
  
> [!NOTE]
>  Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
