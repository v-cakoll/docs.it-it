---
title: Metodo ICorDebug::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: 44bb98f54debb129f951cc388fea81ca0f17b20c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895316"
---
# <a name="icordebugterminate-method"></a>Metodo ICorDebug::Terminate
Termina l' `ICorDebug` oggetto.  
  
> [!NOTE]
> `Terminate`non deve essere chiamato fino a quando non viene ricevuto un callback [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) per tutti i processi di cui è in corso il debug.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a>Osservazioni  
 `Terminate`deve essere chiamato quando l' `ICorDebug` oggetto non è più necessario.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](icordebug-interface.md)
