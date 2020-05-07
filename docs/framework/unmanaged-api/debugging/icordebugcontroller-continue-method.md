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
ms.openlocfilehash: 0fd7dfc1a48e21abbc80692c110bee55beb68e6b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892856"
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
in Impostare su `true` se si continua da un evento fuori banda; in caso contrario, `false`impostare su.

## <a name="remarks"></a>Osservazioni

`Continue`continua il processo dopo una chiamata al `ICorDebugController::Stop` metodo.

Quando si esegue il debug in modalità mista, `Continue` non chiamare sul thread di evento Win32 a meno che non si continui da un evento fuori banda.

Un *evento in banda* può essere un evento gestito o un evento non gestito normale durante il quale il debugger supporta l'interazione con lo stato gestito del processo. In questo caso, il debugger riceve il callback [ICorDebugUnmanagedCallback::D ebugevent](icordebugunmanagedcallback-debugevent-method.md) con il `fOutOfBand` parametro impostato su `false`.

Un *evento fuori banda* è un evento non gestito durante il quale l'interazione con lo stato gestito del processo è Impossibile quando il processo viene interrotto a causa dell'evento. In questo caso, il debugger riceve il `ICorDebugUnmanagedCallback::DebugEvent` callback con il `fOutOfBand` parametro impostato su `true`.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
