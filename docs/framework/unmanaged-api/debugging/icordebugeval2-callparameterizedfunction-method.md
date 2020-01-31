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
ms.openlocfilehash: ab31ab8f83a71372c8e12b460458a26996f65ff5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782984"
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
 `CallParameterizedFunction` è simile a [ICorDebugEval:: CallFunction](icordebugeval-callfunction-method.md) , ad eccezione del fatto che la funzione potrebbe trovarsi all'interno di una classe con parametri di tipo, può prendere parametri di tipo o entrambi. Gli argomenti di tipo devono essere specificati per primi per la classe e quindi per la funzione.  
  
 Se la funzione si trova in un dominio applicazione diverso, si verificherà una transizione. Tuttavia, tutti gli argomenti relativi al tipo e al valore devono trovarsi nel dominio dell'applicazione di destinazione.  
  
 La valutazione della funzione può essere eseguita solo in scenari limitati. Se `CallParameterizedFunction` o `ICorDebugEval::CallFunction` ha esito negativo, il valore HRESULT restituito indicherà il motivo più generale possibile dell'errore.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
