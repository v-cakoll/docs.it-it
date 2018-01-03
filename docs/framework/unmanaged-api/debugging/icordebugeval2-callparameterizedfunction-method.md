---
title: Metodo ICorDebugEval2::CallParameterizedFunction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CallParameterizedFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 055ded7f3309ff1011d1ca390daf353cba870376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>Metodo ICorDebugEval2::CallParameterizedFunction
Imposta una chiamata alla funzione ICorDebugFunction specificata, che può essere annidata all'interno di una classe il cui costruttore accetta <xref:System.Type> accettano parametri oppure può stesso <xref:System.Type> parametri.  
  
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
  
#### <a name="parameters"></a>Parametri  
 `pFunction`  
 [in] Un puntatore a un `ICorDebugFunction` oggetto che rappresenta la funzione da chiamare.  
  
 `nTypeArgs`  
 [in] Il numero di argomenti che la funzione accetta.  
  
 `ppTypeArgs`  
 [in] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di funzione.  
  
 `nArgs`  
 [in] Il numero di valori passato nella funzione.  
  
 `ppArgs`  
 [in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugValue che rappresenta un valore passato un argomento di funzione.  
  
## <a name="remarks"></a>Note  
 `CallParameterizedFunction`è ad esempio [ICorDebugEval::](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) ad eccezione del fatto che la funzione può trovarsi all'interno di una classe con parametri di tipo, può accettare direttamente i parametri di tipo, o entrambi. Gli argomenti di tipo devono essere forniti prima della classe, quindi per la funzione.  
  
 Se la funzione è in un altro dominio applicazione, si verificherà una transizione. Tuttavia, tutti gli argomenti di tipo e il valore devono essere nel dominio dell'applicazione di destinazione.  
  
 La valutazione della funzione può essere eseguita solo in scenari limitati. Se `CallParameterizedFunction` o `ICorDebugEval::CallFunction` ha esito negativo, il valore HRESULT restituito indicherà il motivo più generale possibile dell'errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
