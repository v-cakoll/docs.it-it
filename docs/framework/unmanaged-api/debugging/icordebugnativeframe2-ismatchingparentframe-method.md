---
title: Metodo ICorDebugNativeFrame2::IsMatchingParentFrame
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
ms.openlocfilehash: aeaa706ef35413a728f8b254cd325f0bcc83acd1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792719"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a>Metodo ICorDebugNativeFrame2::IsMatchingParentFrame
Determina se il frame specificato è l'elemento padre del frame corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a>Parametri  
 `pPotentialParentFrame`  
 in Puntatore all'oggetto frame che si desidera valutare per lo stato padre.  
  
 `pIsParent`  
 [out] `true` se `pPotentialParentFrame` è l'elemento padre del frame corrente; in caso contrario, `false`.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Lo stato padre è stato restituito correttamente.|  
|E_FAIL|Non è stato possibile restituire lo stato padre.|  
|E_INVALIDARG|`pPotentialParentFrame` o `pIsParent` è null.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 `IsMatchingParentFrame` restituisce `true` se l'oggetto frame passato al metodo è l'elemento padre dell'oggetto frame su cui è stato chiamato il metodo. Se si chiama il metodo su un frame che non è figlio del frame specificato, viene restituito un errore.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
