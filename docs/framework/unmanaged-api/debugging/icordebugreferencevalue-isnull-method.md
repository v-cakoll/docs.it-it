---
title: Metodo ICorDebugReferenceValue::IsNull
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
ms.openlocfilehash: 9d5047b1d44f836d10b659f18cf885eba3b0e973
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139825"
---
# <a name="icordebugreferencevalueisnull-method"></a>Metodo ICorDebugReferenceValue::IsNull
Ottiene un valore che indica se questo ICorDebugReferenceValue è un valore null, nel qual caso il `ICorDebugReferenceValue` non punta a un oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbNull`  
 out Puntatore a un valore booleano che viene `true` se l'oggetto `ICorDebugReferenceValue` è null; in caso contrario, `pbNull` è `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
