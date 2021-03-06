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
ms.openlocfilehash: 72bcc2479f7b6f41b384fc2517f0b04694663398
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976148"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>Metodo ICorDebugEval2::CallParameterizedFunction
Imposta una chiamata al ICorDebugFunction specificato, che può essere annidato all'interno di una classe il cui <xref:System.Type> costruttore accetta parametri oppure accetta <xref:System.Type> parametri.  
  
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
 in Puntatore a un `ICorDebugFunction` oggetto che rappresenta la funzione da chiamare.  
  
 `nTypeArgs`  
 in Numero di argomenti accettati dalla funzione.  
  
 `ppTypeArgs`  
 in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento della funzione.  
  
 `nArgs`  
 in Numero di valori passati nella funzione.  
  
 `ppArgs`  
 in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugValue che rappresenta un valore passato in un argomento della funzione.  
  
## <a name="remarks"></a>Osservazioni  
 `CallParameterizedFunction`è simile a [ICorDebugEval:: CallFunction](icordebugeval-callfunction-method.md) ad eccezione del fatto che la funzione potrebbe trovarsi all'interno di una classe con parametri di tipo, può prendere parametri di tipo o entrambi. Gli argomenti di tipo devono essere specificati per primi per la classe e quindi per la funzione.  
  
 Se la funzione si trova in un dominio applicazione diverso, si verificherà una transizione. Tuttavia, tutti gli argomenti relativi al tipo e al valore devono trovarsi nel dominio dell'applicazione di destinazione.  
  
 La valutazione della funzione può essere eseguita solo in scenari limitati. Se `CallParameterizedFunction` o `ICorDebugEval::CallFunction` ha esito negativo, il valore HRESULT restituito indicherà il motivo più generale possibile per l'errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
