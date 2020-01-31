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
ms.openlocfilehash: 2d3f8360a1fb1164fd4e26f85246251409bee376
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788953"
---
# <a name="icordebugterminate-method"></a>Metodo ICorDebug::Terminate
Termina l'oggetto `ICorDebug`.  
  
> [!NOTE]
> `Terminate` non devono essere chiamati fino a quando non viene ricevuto un callback [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) per tutti i processi di cui è in corso il debug.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a>Note  
 `Terminate` necessario chiamare quando l'oggetto `ICorDebug` non è più necessario.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](icordebug-interface.md)
