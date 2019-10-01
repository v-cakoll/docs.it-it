---
title: Metodo ICorDebugCode::GetVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b6fd6e8043f1c62da8994b43a9b9af45fb2e3c0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700815"
---
# <a name="icordebugcodegetversionnumber-method"></a>Metodo ICorDebugCode::GetVersionNumber

Ottiene il numero in base 1 che identifica la versione del codice rappresentato da "ICorDebugCode".

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a>Parametri

 `nVersion`  
 out Puntatore al numero di versione del codice.

## <a name="remarks"></a>Note

 Il numero di versione viene incrementato ogni volta che viene eseguita un'operazione di modifica e continuazione (EnC) sul codice.

## <a name="requirements"></a>Requisiti

 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
