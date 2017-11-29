---
title: Metodo ICorDebugRegisterSet::GetRegisters
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetRegisters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7edae3d3be1bcfb80b7a1e432fd5f25e119f078f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetgetregisters-method"></a>Metodo ICorDebugRegisterSet::GetRegisters
Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione codice) specificato dalla maschera di bit.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `mask`  
 [in] Maschera di bit che specifica quali valori di registro da recuperare. Ogni bit corrisponde a un registro. Se un bit è impostato su uno, viene recuperato il valore del Registro; in caso contrario, non è possibile recuperare il valore del registro.  
  
 `regCount`  
 [in] Il numero di valori del registro da recuperare.  
  
 `regBuffer`  
 [out] Matrice di `CORDB_REGISTER` oggetti, ognuno dei quali riceve un valore di un registro.  
  
## <a name="remarks"></a>Note  
 Le dimensioni della matrice devono essere uguale al numero di bit impostati su 1 nella maschera di bit. Il `regCount` parametro specifica il numero di elementi nel buffer che riceverà i valori di registro. Se il `regCount` valore è troppo piccolo per il numero di registri indicato dalla maschera, i registri con numero maggiore verranno troncati dal set. Se il `regCount` valore è troppo grande, inutilizzata `regBuffer` gli elementi verranno modificati.  
  
 Se la maschera di bit specifica un registro che non è disponibile, `GetRegisters` restituisce un valore indeterminato per tale registro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugRegisterSet (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [ICorDebugRegisterSet2 (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
