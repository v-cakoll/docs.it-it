---
title: Metodo ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb134b7d188c2fb966b53e4520a7fb825f11e428
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612047"
---
# <a name="icordebugprocess6processstatechanged-method"></a>Metodo ICorDebugProcess6::ProcessStateChanged
Invia una notifica [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che viene eseguito il processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a>Parametri  
 `change`  
 [in] Un membro del [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumerazione  
  
## <a name="remarks"></a>Note  
 Il debugger chiama questo metodo per notificare [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che viene eseguito il processo.  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
