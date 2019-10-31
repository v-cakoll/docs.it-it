---
title: Metodo ICorDebugArrayValue::GetElementAtPosition
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
ms.openlocfilehash: 10584442d7e0bd61e6decaf2b494dfe39f339d6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088422"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a>Metodo ICorDebugArrayValue::GetElementAtPosition
Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come matrice unidimensionale in base zero.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `nPosition`  
 in Posizione dell'elemento da recuperare.  
  
 `ppValue`  
 out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento.  
  
## <a name="remarks"></a>Note  
 Il layout di una matrice MULTIDIMENSIONE segue lo C++ stile del layout della matrice.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
