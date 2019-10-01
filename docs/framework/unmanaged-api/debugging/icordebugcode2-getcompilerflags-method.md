---
title: Metodo ICorDebugCode2::GetCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1605ee92c8743606ff0e958f112a2d90af43e03a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700710"
---
# <a name="icordebugcode2getcompilerflags-method"></a>Metodo ICorDebugCode2::GetCompilerFlags

Ottiene i flag che specificano le condizioni in base alle quali l'oggetto di codice è stato compilato o generato JIT usando il generatore di immagini native (Ngen. exe).

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a>Parametri

 `pdwFlags`  
 out Puntatore a un valore dell'enumerazione [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) che specifica il comportamento del compilatore JIT o del generatore di immagini native.

## <a name="requirements"></a>Requisiti

 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Intestazione:** CorDebug. idl, CorDebug. h

 **Libreria** CorGuids.lib

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
 
