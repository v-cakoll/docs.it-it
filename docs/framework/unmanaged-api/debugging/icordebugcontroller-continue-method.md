---
title: Metodo ICorDebugController::Continue
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
ms.openlocfilehash: 14356a12c944ef93dba5e7b818d3ee5cf5adc607
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125427"
---
# <a name="icordebugcontrollercontinue-method"></a>Metodo ICorDebugController::Continue

Riprende l'esecuzione di thread gestiti dopo una chiamata al [metodo Stop](icordebugcontroller-stop-method.md).

## <a name="syntax"></a>Sintassi

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a>Parametri

`fIsOutOfBand`  
in Impostare su `true` se si continua da un evento fuori banda; in caso contrario, impostare su `false`.

## <a name="remarks"></a>Note

`Continue` continua il processo dopo una chiamata al metodo `ICorDebugController::Stop`.

Quando si esegue il debug in modalità mista, non chiamare `Continue` sul thread di evento Win32 a meno che non si continui da un evento fuori banda.

Un *evento in banda* può essere un evento gestito o un evento non gestito normale durante il quale il debugger supporta l'interazione con lo stato gestito del processo. In questo caso, il debugger riceve il callback [ICorDebugUnmanagedCallback::D ebugevent](icordebugunmanagedcallback-debugevent-method.md) con il relativo parametro `fOutOfBand` impostato su `false`.

Un *evento fuori banda* è un evento non gestito durante il quale l'interazione con lo stato gestito del processo è Impossibile quando il processo viene interrotto a causa dell'evento. In questo caso, il debugger riceve il callback `ICorDebugUnmanagedCallback::DebugEvent` con il relativo parametro `fOutOfBand` impostato su `true`.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
