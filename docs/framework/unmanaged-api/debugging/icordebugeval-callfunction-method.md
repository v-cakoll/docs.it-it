---
title: Metodo ICorDebugEval::CallFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
ms.openlocfilehash: 4ac26ef4449dc02230f26b1247616b4587d217b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085164"
---
# <a name="icordebugevalcallfunction-method"></a>Metodo ICorDebugEval::CallFunction

Imposta una chiamata alla funzione specificata.

Questo metodo è obsoleto nella versione .NET Framework 2,0. Usare invece [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) .

## <a name="syntax"></a>Sintassi

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a>Parametri

`pFunction`\
in Puntatore a un oggetto ICorDebugFunction che specifica la funzione da chiamare.

`nArgs`\
in Numero di argomenti per la funzione.

`ppArgs`\
in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugValue che specifica un argomento da passare alla funzione.

## <a name="remarks"></a>Note

Se la funzione è virtuale, `CallFunction` eseguirà il dispatch virtuale. Se la funzione si trova in un dominio applicazione diverso, si verificherà una transizione purché tutti gli argomenti si trovino anche in tale dominio applicazione.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni .NET Framework:** 1,1, 1,0

## <a name="see-also"></a>Vedere anche

- [Metodo CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md)
