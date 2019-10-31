---
title: Interfaccia ICorDebugRuntimeUnwindableFrame
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 2902744b6af3c7b2bd4def73b04807ce3333a8a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131884"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>Interfaccia ICorDebugRuntimeUnwindableFrame
Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.  
  
## <a name="remarks"></a>Note  
 `ICorDebugRuntimeUnwindableFrame` è una versione specializzata dell'interfaccia ICorDebugFrame. Viene usato da metodi non gestiti che richiedono al runtime di rimuovere un frame nello stack corrente. Le convenzioni di rimozione esistenti non funzionano perché non utilizzano codice compilato tramite JIT. Quando il debugger rileva un frame non ricaricabile, deve usare il metodo [ICorDebugStackWalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) per rimuoverlo, ma deve eseguire un controllo. Quando il debugger riceve una `ICorDebugRuntimeUnwindableFrame`, può chiamare il metodo [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) per recuperare il contesto del frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
