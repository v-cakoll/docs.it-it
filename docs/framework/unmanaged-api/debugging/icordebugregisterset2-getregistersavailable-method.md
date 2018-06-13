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
ms.openlocfilehash: d3a9cdb49c1a44dbc68cd4b7ccf4d4781ce5c539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421892"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>Metodo ICorDebugRegisterSet2::GetRegistersAvailable
Ottiene una matrice di byte che fornisce una bitmap dei registri disponibili.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `numChunks`  
 [in] Dimensione della matrice `availableRegChunks`.  
  
 `availableRegChunks`  
 [out] Matrice di byte, ogni bit che corrisponde a un registro. Se un registro è disponibile, viene impostato il bit corrispondente.  
  
## <a name="remarks"></a>Note  
 I valori dell'enumerazione CorDebugRegister specificano i registri di microprocessori diversi. I cinque bit superiori di ogni valore sono l'indice di `availableRegChunks` matrice di byte. I tre bit inferiore di ogni valore di identificare la posizione del bit all'interno del byte indicizzato. Dato un `CorDebugRegister` valore che specifica un particolare registro, la posizione del registro nella maschera è determinato come segue:  
  
1.  Estrarre necessaria per accedere al byte corretto in corrispondenza dell'indice di `availableRegChunks` matrice:  
  
     `CorDebugRegister` valore >> 3  
  
2.  Estrarre la posizione del bit all'interno del byte indicizzato, in bit zero è il bit meno significativo:  
  
     `CorDebugRegister` valore & 7  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [Interfaccia ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
