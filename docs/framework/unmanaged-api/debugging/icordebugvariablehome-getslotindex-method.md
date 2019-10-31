---
title: 'Metodo ICorDebugVariableHome:: GetSlotIndex'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: dfc2e91599e7f05d90d56af07b71313e9eecaa51
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121058"
---
# <a name="icordebugvariablehomegetslotindex-method"></a>Metodo ICorDebugVariableHome:: GetSlotIndex
Ottiene l'indice di slot gestito di una variabile locale.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pSlotIndex`  
 out Puntatore all'indice di slot di una variabile locale.  
  
## <a name="return-value"></a>Valore restituito  
 Il metodo restituisce i valori seguenti.  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`S_OK`|La chiamata al metodo ha restituito un valore di indice di slot in `pSlotIndex`.|  
|`E_FAIL`|L'istanza corrente di [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) rappresenta un argomento della funzione.|  
  
## <a name="remarks"></a>Note  
 Lo slot-index può essere usato per recuperare i metadati per la variabile locale.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
