---
title: Metodo ICorDebugVariableHome::GetSlotIndex
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61014e067b2afb8b7e4be0488ed6a3c7f1bd6fc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420700"
---
# <a name="icordebugvariablehomegetslotindex-method"></a>Metodo ICorDebugVariableHome::GetSlotIndex
Ottiene l'indice dello slot gestito di una variabile locale.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pSlotIndex`  
 [out] Un puntatore per l'indice dello slot di una variabile locale.  
  
## <a name="return-value"></a>Valore restituito  
 Il metodo restituisce i valori seguenti.  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`S_OK`|La chiamata al metodo ha restituito un valore di indice dello slot in `pSlotIndex`.|  
|`E_FAIL`|Corrente [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza rappresenta un argomento di funzione.|  
  
## <a name="remarks"></a>Note  
 L'indice dello slot può essere utilizzato per recuperare i metadati per questa variabile locale.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
