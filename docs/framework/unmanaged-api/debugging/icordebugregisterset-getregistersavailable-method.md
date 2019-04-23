---
title: Metodo ICorDebugRegisterSet::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f341098268f735a576bdbc5f0cea52f1a7e14f90
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59156039"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a>Metodo ICorDebugRegisterSet::GetRegistersAvailable
Ottiene una maschera di bit che indica quali registri in questo [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) sono attualmente disponibili.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAvailable`  
 [out] Maschera di bit che indica quali registri sono attualmente disponibili.  
  
## <a name="remarks"></a>Note  
 Un registro potrebbe non essere disponibile se non è possibile determinare il valore per una determinata situazione.  
  
 La maschera restituita contiene un bit per ogni registrazione (1 << indice register). Il valore di bit è 1 se la registrazione è disponibile, oppure 0 se non è disponibile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [Interfaccia ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
