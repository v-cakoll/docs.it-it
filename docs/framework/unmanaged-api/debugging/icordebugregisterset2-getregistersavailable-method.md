---
title: Metodo ICorDebugRegisterSet2::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4ab49aaccd77fac497bd86413915e82c99ed3e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744902"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>Metodo ICorDebugRegisterSet2::GetRegistersAvailable
Ottiene una matrice di byte che fornisce una bitmap di registri disponibili.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `numChunks`  
 [in] Dimensione della matrice `availableRegChunks`.  
  
 `availableRegChunks`  
 [out] Matrice di byte, ogni bit che corrisponde a un registro. Se è disponibile un registro, viene impostato il bit corrispondente.  
  
## <a name="remarks"></a>Note  
 I valori dell'enumerazione CorDebugRegister specificano i registri di microprocessori diversi. I cinque bit superiore di ogni valore sono l'indice nel `availableRegChunks` matrice di byte. I tre bit inferiore di ogni valore di identificare la posizione del bit all'interno del byte indicizzata. Dato un `CorDebugRegister` valore che specifica un determinato registro, la posizione del registro nella maschera è determinato come segue:  
  
1. Estrarre necessaria per accedere al corretto byte in corrispondenza dell'indice di `availableRegChunks` matrice:  
  
     `CorDebugRegister` valore >> 3  
  
2. Estrarre la posizione del bit all'interno del byte indicizzata, in cui il bit zero è il bit meno significativo:  
  
     `CorDebugRegister` valore di & amp;7  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [Interfaccia ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
