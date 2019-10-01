---
title: Metodo ICorDebugCode::IsIL
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a81f4a53954c559ab12e27bcf039b7b1a1804cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700789"
---
# <a name="icordebugcodeisil-method"></a>Metodo ICorDebugCode::IsIL

Ottiene un valore che indica se questo "ICorDebugCode" rappresenta il codice compilato in MSIL (Microsoft Intermediate Language).

## <a name="syntax"></a>Sintassi

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a>Parametri
 `pbIL`  
 [out] `true` se questo `ICorDebugCode` rappresenta il codice compilato in MSIL; in caso contrario, `false`.

## <a name="requirements"></a>Requisiti

 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  

 **Intestazione:** CorDebug. idl, CorDebug. h  

 **Libreria** CorGuids.lib  

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
 
