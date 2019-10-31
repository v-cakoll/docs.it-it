---
title: Interfaccia ICorDebugStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: 48f1b485b6dfa8fd898f6ea00eee2d7b397deba6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131863"
---
# <a name="icordebugstackwalk-interface"></a>Interfaccia ICorDebugStackWalk
Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|Restituisce il contesto per il frame corrente nell'oggetto `ICorDebugStackWalk`.|  
|[Metodo SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|Imposta il contesto corrente dell'oggetto `ICorDebugStackWalk` su un contesto valido per il thread.|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|Sposta l'oggetto `ICorDebugStackWalk` al frame successivo.|  
|[Metodo GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|Ottiene il frame corrente nell'oggetto `ICorDebugStackWalk`.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
