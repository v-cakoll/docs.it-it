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
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="5a4ca-102">Metodo ICorDebugEval2::CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="5a4ca-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="5a4ca-103">Imposta una chiamata all'oggetto ICorDebugFunction specificato, che può essere annidato all'interno di una classe il cui costruttore accetta <xref:System.Type> parametri o accetta <xref:System.Type> parametri.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a4ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a4ca-104">Syntax</span></span>  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a4ca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a4ca-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="5a4ca-106">in Puntatore a un oggetto `ICorDebugFunction` che rappresenta la funzione da chiamare.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="5a4ca-107">in Numero di argomenti accettati dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="5a4ca-108">in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="5a4ca-109">in Numero di valori passati nella funzione.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="5a4ca-110">in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugValue che rappresenta un valore passato in un argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a4ca-111">Note</span><span class="sxs-lookup"><span data-stu-id="5a4ca-111">Remarks</span></span>  
 <span data-ttu-id="5a4ca-112">`CallParameterizedFunction` è simile a [ICorDebugEval:: CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) , ad eccezione del fatto che la funzione potrebbe trovarsi all'interno di una classe con parametri di tipo, può prendere parametri di tipo o entrambi.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="5a4ca-113">Gli argomenti di tipo devono essere specificati per primi per la classe e quindi per la funzione.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="5a4ca-114">Se la funzione si trova in un dominio applicazione diverso, si verificherà una transizione.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="5a4ca-115">Tuttavia, tutti gli argomenti relativi al tipo e al valore devono trovarsi nel dominio dell'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="5a4ca-116">La valutazione della funzione può essere eseguita solo in scenari limitati.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="5a4ca-117">Se `CallParameterizedFunction` o `ICorDebugEval::CallFunction` ha esito negativo, il valore HRESULT restituito indicherà il motivo più generale possibile dell'errore.</span><span class="sxs-lookup"><span data-stu-id="5a4ca-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a4ca-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a4ca-118">Requirements</span></span>  
 <span data-ttu-id="5a4ca-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a4ca-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a4ca-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a4ca-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a4ca-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a4ca-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a4ca-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a4ca-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
