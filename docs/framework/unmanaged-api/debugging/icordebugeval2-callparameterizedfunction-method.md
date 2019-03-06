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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cba4eb2b76d7057a5ed66a35342a79615cb8539f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487724"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>Metodo ICorDebugEval2::CallParameterizedFunction
Imposta una chiamata alla funzione ICorDebugFunction specificato, che può essere nidificata in una classe il cui costruttore accetta <xref:System.Type> accettano parametri oppure può stesso <xref:System.Type> parametri.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 [in] Un puntatore a un `ICorDebugFunction` oggetto che rappresenta la funzione da chiamare.  
  
 `nTypeArgs`  
 [in] Il numero di argomenti che la funzione accetta.  
  
 `ppTypeArgs`  
 [in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di funzione.  
  
 `nArgs`  
 [in] Il numero di valori passati nella funzione.  
  
 `ppArgs`  
 [in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugValue che rappresenta un valore passato in una funzione.  
  
## <a name="remarks"></a>Note  
 `CallParameterizedFunction` è simile a [CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) ad eccezione del fatto che la funzione può trovarsi all'interno di una classe con i parametri di tipo, può accettare direttamente i parametri di tipo, o entrambi. Gli argomenti di tipo devono essere forniti prima della classe, quindi per la funzione.  
  
 Se la funzione è in un altro dominio applicazione, si verificherà una transizione. Tuttavia, tutti gli argomenti tipo e il valore devono essere nel dominio dell'applicazione di destinazione.  
  
 Valutazione della funzione può essere eseguita solo in alcuni scenari. Se `CallParameterizedFunction` o `ICorDebugEval::CallFunction` ha esito negativo, il valore HRESULT restituito indicherà il motivo più generale possibili per errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
