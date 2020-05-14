---
title: Metodo ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 251a978e96ff396d0d9d9282ded7f8a25ae0ba0b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397090"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a>Metodo ICorDebugVariableSymbol::GetSlotIndex
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
  
## <a name="remarks"></a>Commenti  
 L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.  
  
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
