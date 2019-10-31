---
title: Metodo ICorDebugEval2::CallParameterizedFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: b521c96d26202119dad6fedb61cbd9da8b3c2e52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137634"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>Metodo ICorDebugEval2::CallParameterizedFunction
Imposta una chiamata all'oggetto ICorDebugFunction specificato, che può essere annidato all'interno di una classe il cui costruttore accetta <xref:System.Type> parametri o accetta <xref:System.Type> parametri.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pFunction`  
 in Puntatore a un oggetto `ICorDebugFunction` che rappresenta la funzione da chiamare.  
  
 `nTypeArgs`  
 in Numero di argomenti accettati dalla funzione.  
  
 `ppTypeArgs`  
 in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento della funzione.  
  
 `nArgs`  
 in Numero di valori passati nella funzione.  
  
 `ppArgs`  
 in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugValue che rappresenta un valore passato in un argomento della funzione.  
  
## <a name="remarks"></a>Note  
 `CallParameterizedFunction` è simile a [ICorDebugEval:: CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) , ad eccezione del fatto che la funzione potrebbe trovarsi all'interno di una classe con parametri di tipo, può prendere parametri di tipo o entrambi. Gli argomenti di tipo devono essere specificati per primi per la classe e quindi per la funzione.  
  
 Se la funzione si trova in un dominio applicazione diverso, si verificherà una transizione. Tuttavia, tutti gli argomenti relativi al tipo e al valore devono trovarsi nel dominio dell'applicazione di destinazione.  
  
 La valutazione della funzione può essere eseguita solo in scenari limitati. Se `CallParameterizedFunction` o `ICorDebugEval::CallFunction` ha esito negativo, il valore HRESULT restituito indicherà il motivo più generale possibile dell'errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
