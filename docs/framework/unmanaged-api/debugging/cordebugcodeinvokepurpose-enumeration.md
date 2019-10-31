---
title: Enumerazione CorDebugCodeInvokePurpose
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
ms.openlocfilehash: f037a28f0417f5607cd5b5637da4ca62e34e0edb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132271"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a>Enumerazione CorDebugCodeInvokePurpose
Descrive il motivo per cui una funzione esportata chiama il codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|Nessuno o sconosciuto.|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|Il codice gestito esegue qualsiasi punto di ingresso gestito, ad esempio p-invoke inverso. Eventuali altri scopi più dettagliati non sono noti al runtime.|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|Il codice gestito esegue un costruttore statico.|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|Il codice gestito esegue l'implementazione per alcuni metodi dell'interfaccia chiamati.|  
  
## <a name="remarks"></a>Note  
 Questa enumerazione viene utilizzata dal metodo [Metodo icordebugprocess6:: GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) per fornire informazioni sull'esecuzione del codice gestito.  
  
> [!NOTE]
> Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
