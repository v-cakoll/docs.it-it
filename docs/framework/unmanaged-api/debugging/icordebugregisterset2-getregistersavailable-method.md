---
title: Metodo ICorDebugRegisterSet2::GetRegistersAvailable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2.GetRegistersAvailable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e2e3862f91fc68879e2f9e396ab9045c617de82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
     `CorDebugRegister`valore >> 3  
  
2.  Estrarre la posizione del bit all'interno del byte indicizzato, in bit zero è il bit meno significativo:  
  
     `CorDebugRegister`valore & 7  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [Interfaccia ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
