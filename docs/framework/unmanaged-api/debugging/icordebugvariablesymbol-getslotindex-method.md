---
title: Metodo ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1657ed4d8326b573fe081b98c1fc414e231ac465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a>Metodo ICorDebugVariableSymbol::GetSlotIndex
Ottiene l'indice dello slot gestito di una variabile locale.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pSlotIndex`  
 [out] Un puntatore all'indice degli slot della variabile locale.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se l'operazione riesce. `E_FAIL` se la variabile è un argomento di funzione.  
  
## <a name="remarks"></a>Note  
 L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
