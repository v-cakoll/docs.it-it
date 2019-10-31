---
title: Metodo ICorDebugManagedCallback::ControlCTrap
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
ms.openlocfilehash: da35db8a943fda5fb3fbf4126684bb9cb7243001
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137422"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a>Metodo ICorDebugManagedCallback::ControlCTrap
Notifica al debugger che la combinazione di tasti CTRL + C è intrappolata nel processo di cui è in corso il debug.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pProcess`  
 in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo in cui viene intercettata la combinazione di tasti CTRL + C.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il debugger gestirà la trap CTRL + C.|  
|S_FALSE|Il debugger non gestirà la trap CTRL + C.|  
  
## <a name="remarks"></a>Note  
 Tutti i domini applicazione all'interno del processo vengono arrestati per questo callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
