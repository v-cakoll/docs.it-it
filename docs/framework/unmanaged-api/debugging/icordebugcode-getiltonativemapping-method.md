---
title: Metodo ICorDebugCode::GetILToNativeMapping
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 949cf322be4b7981a8c569f24abd1d9e29fa5ae6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973145"
---
# <a name="icordebugcodegetiltonativemapping-method"></a>Metodo ICorDebugCode::GetILToNativeMapping
Ottiene una matrice di istanze di "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da Microsoft intermediate language (MSIL) agli offset nativi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cMap`  
 [in] Dimensione della matrice `map`.  
  
 `pcMap`  
 [out] Un puntatore al numero effettivo di elementi restituiti nella `map` matrice.  
  
 `map`  
 [out] Matrice di `COR_DEBUG_IL_TO_NATIVE_MAP` strutture, ognuno dei quali rappresenta un mapping da un offset MSIL da un offset nativo.  
  
 Vi è alcun ordine nella matrice di elementi restituiti.  
  
## <a name="remarks"></a>Note  
 Il `GetILToNativeMapping` metodo restituisce risultati significativi solo se questa istanza di "ICorDebugCode" rappresenta il codice nativo che è stata just-in-time (JIT) compilato dal codice MSIL.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [ICorDebugCode (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
