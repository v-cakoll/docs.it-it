---
title: Metodo ICorDebugCode::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89df0e9be0600b51dcc8a68c5aba3f06e86e1b53
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700808"
---
# <a name="icordebugcodegetsize-method"></a>Metodo ICorDebugCode::GetSize

Ottiene la dimensione, in byte, del codice binario rappresentato da questo "ICorDebugCode".

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetSize (
    [out] ULONG32    *pcBytes
);
```

## <a name="parameters"></a>Parametri

 `pcBytes`  
 out Puntatore alla dimensione, in byte, del codice binario rappresentato da questo oggetto `ICorDebugCode`.

## <a name="requirements"></a>Requisiti

 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

 **Intestazione:** CorDebug. idl, CorDebug. h

 **Libreria** CorGuids.lib

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
 
