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
ms.openlocfilehash: 720d9c4fb9b997538ee2bb18ac7987350f6bfb57
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="43a49-102">Metodo ICorDebugEval2::CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="43a49-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="43a49-103">Imposta una chiamata alla funzione ICorDebugFunction specificata, che può essere annidata all'interno di una classe il cui costruttore accetta <xref:System.Type> accettano parametri oppure può stesso <xref:System.Type> parametri.</span><span class="sxs-lookup"><span data-stu-id="43a49-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43a49-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43a49-104">Syntax</span></span>  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43a49-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43a49-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="43a49-106">[in] Un puntatore a un `ICorDebugFunction` oggetto che rappresenta la funzione da chiamare.</span><span class="sxs-lookup"><span data-stu-id="43a49-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="43a49-107">[in] Il numero di argomenti che la funzione accetta.</span><span class="sxs-lookup"><span data-stu-id="43a49-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="43a49-108">[in] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="43a49-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="43a49-109">[in] Il numero di valori passato nella funzione.</span><span class="sxs-lookup"><span data-stu-id="43a49-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="43a49-110">[in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugValue che rappresenta un valore passato un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="43a49-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43a49-111">Note</span><span class="sxs-lookup"><span data-stu-id="43a49-111">Remarks</span></span>  
 <span data-ttu-id="43a49-112">`CallParameterizedFunction`è ad esempio [ICorDebugEval::](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) ad eccezione del fatto che la funzione può trovarsi all'interno di una classe con parametri di tipo, può accettare direttamente i parametri di tipo, o entrambi.</span><span class="sxs-lookup"><span data-stu-id="43a49-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="43a49-113">Gli argomenti di tipo devono essere forniti prima della classe, quindi per la funzione.</span><span class="sxs-lookup"><span data-stu-id="43a49-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="43a49-114">Se la funzione è in un altro dominio applicazione, si verificherà una transizione.</span><span class="sxs-lookup"><span data-stu-id="43a49-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="43a49-115">Tuttavia, tutti gli argomenti di tipo e il valore devono essere nel dominio dell'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="43a49-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="43a49-116">La valutazione della funzione può essere eseguita solo in scenari limitati.</span><span class="sxs-lookup"><span data-stu-id="43a49-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="43a49-117">Se `CallParameterizedFunction` o `ICorDebugEval::CallFunction` ha esito negativo, il valore HRESULT restituito indicherà il motivo più generale possibile dell'errore.</span><span class="sxs-lookup"><span data-stu-id="43a49-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43a49-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43a49-118">Requirements</span></span>  
 <span data-ttu-id="43a49-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43a49-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43a49-120">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="43a49-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43a49-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43a49-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43a49-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43a49-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
