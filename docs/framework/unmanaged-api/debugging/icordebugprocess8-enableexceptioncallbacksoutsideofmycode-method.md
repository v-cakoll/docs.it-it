---
title: Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e7de3622498e8417a961e0d4708c53527a833ef2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
[Supportato in [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] e versioni successive]  
  
 Abilita o disabilita alcuni tipi di [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) callback di eccezione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>Note  
 Se il valore di `enableExceptionsOutsideOfJMC` è `false`:  
  
-   Un'eccezione DEBUG_EXCEPTION_FIRST_CHANCE non comporterà un callback al debugger.  
  
-   Un'eccezione DEBUG_EXCEPTION_CATCH_HANDLER_FOUND non comporterà un callback al debugger se l'eccezione non raggiunge mai il codice utente (ovvero, il percorso dall'origine di un gestore di eccezioni non ha metodi contrassegnati JustMyCode o JMC).  
  
 Il valore predefinito di `enableExceptionsOutsideOfJMC` è `true`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugProcess8](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
