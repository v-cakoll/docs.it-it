---
title: Metodo ICorDebugController::Detach
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
ms.openlocfilehash: 480fec4897dac73594515ba8bc0f0e96ceb79ace
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892906"
---
# <a name="icordebugcontrollerdetach-method"></a>Metodo ICorDebugController::Detach
Scollega il debugger dal dominio del processo o dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a>Osservazioni  
 Il processo o il dominio applicazione continua l'esecuzione normalmente, ma l'oggetto "ICorDebugProcess" o "ICorDebugAppDomain" non è più valido e non si verificheranno ulteriori callback.  
  
 Nel .NET Framework versione 2,0, se è abilitato il debug non gestito, questo metodo avrà esito negativo a causa delle limitazioni del sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
