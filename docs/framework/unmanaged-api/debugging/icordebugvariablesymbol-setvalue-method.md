---
title: Metodo ICorDebugVariableSymbol::SetValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12c13259d20301b0f485a6041fa884b0996cbbdc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolsetvalue-method"></a>Metodo ICorDebugVariableSymbol::SetValue
Assegna il valore di una matrice di byte a una variabile.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `offset`  
 [in] Offset iniziale nella variabile da cui leggere il valore. Questo parametro viene usato durante la scrittura nei campi membro di un oggetto.  
  
 `threadID`  
 [in] Identificatore del thread il cui contesto deve essere aggiornato per riflettere il nuovo valore.  
  
 `cbContext`  
 [in] Dimensioni in byte del contesto del thread.  
  
 `context`  
 [in] Contesto del thread usato per scrivere il valore.  
  
 `cbValue`  
 [in] Dimensioni in byte del buffer `pValue`.  
  
 `pValue`  
 [in] Buffer contenente il valore da configurare.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
