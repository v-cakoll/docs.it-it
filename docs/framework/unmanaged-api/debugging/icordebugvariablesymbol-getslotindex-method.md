---
title: 'Metodo metodo icordebugvariablesymbol:: GetSlotIndex'
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: a7a7ecf7d3e3d0d2125b03d3604c44138a2be0cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120977"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a>Metodo metodo icordebugvariablesymbol:: GetSlotIndex
Ottiene l'indice dello slot gestito di una variabile locale.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pSlotIndex`  
 [out] Un puntatore all'indice degli slot della variabile locale.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se l'operazione riesce. `E_FAIL` se la variabile è un argomento di funzione.  
  
## <a name="remarks"></a>Note  
 L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
