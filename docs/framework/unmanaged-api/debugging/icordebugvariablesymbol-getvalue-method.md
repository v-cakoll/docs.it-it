---
title: Metodo ICorDebugVariableSymbol::GetValue
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 186d9eec0aa6ad9e327b1dd4d0f19e251c79ecf9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147277"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a>Metodo ICorDebugVariableSymbol::GetValue
Ottiene il valore di una variabile come matrice di byte.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `offset`  
 [in] Offset iniziale nella variabile da cui leggere il valore. Questo parametro viene usato durante la lettura di campi membro in un oggetto.  
  
 `cbContext`  
 [in] Dimensioni in byte dell'argomento `context`.  
  
 `context`  
 [in] Contesto del thread usato per leggere il valore.  
  
 `cbValue`  
 [in] Dimensioni in byte del buffer `pValue`.  
  
 `pcbValue`  
 [out] Numero di byte affettivamente scritti nel buffer `pValue`.  
  
 `pValue`  
 [out] Matrice di byte contenente il valore della variabile.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
