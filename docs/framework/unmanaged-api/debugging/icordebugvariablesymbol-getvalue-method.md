---
title: Metodo ICorDebugVariableSymbol::GetValue
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: f217f7226d53a27363f66eb90a340fd3604a0217
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396511"
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
  
## <a name="remarks"></a>Commenti  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
