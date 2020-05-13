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
ms.openlocfilehash: 5f71dfcdffaaa683ca4f2abebaa99115ef90e0ff
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378899"
---
# <a name="icordebugstackwalk-interface"></a>Interfaccia ICorDebugStackWalk
Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetContext](icordebugstackwalk-getcontext-method.md)|Restituisce il contesto per il frame corrente nell' `ICorDebugStackWalk` oggetto.|  
|[Metodo SetContext](icordebugstackwalk-setcontext-method.md)|Imposta il `ICorDebugStackWalk` contesto corrente dell'oggetto su un contesto valido per il thread.|  
|[Metodo Next](icordebugstackwalk-next-method.md)|Sposta l' `ICorDebugStackWalk` oggetto sul frame successivo.|  
|[Metodo GetFrame](icordebugstackwalk-getframe-method.md)|Ottiene il frame corrente nell' `ICorDebugStackWalk` oggetto.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
