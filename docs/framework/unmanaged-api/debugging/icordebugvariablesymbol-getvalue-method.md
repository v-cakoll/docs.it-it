---
title: Metodo ICorDebugVariableSymbol::GetValue
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b72b9dbeff6aa06a132dc7ec3ddd9477553c4c2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967986"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a>Metodo ICorDebugVariableSymbol::GetValue
Ottiene il valore di una variabile come matrice di byte.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
