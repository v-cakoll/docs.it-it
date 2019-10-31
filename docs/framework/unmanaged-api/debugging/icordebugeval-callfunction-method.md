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
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="ce08a-102">Metodo ICorDebugEval::CallFunction</span><span class="sxs-lookup"><span data-stu-id="ce08a-102">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="ce08a-103">Imposta una chiamata alla funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="ce08a-103">Sets up a call to the specified function.</span></span>

<span data-ttu-id="ce08a-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="ce08a-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ce08a-105">Usare invece [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ce08a-105">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="ce08a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce08a-106">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="ce08a-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce08a-107">Parameters</span></span>

`pFunction`\
<span data-ttu-id="ce08a-108">in Puntatore a un oggetto ICorDebugFunction che specifica la funzione da chiamare.</span><span class="sxs-lookup"><span data-stu-id="ce08a-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="ce08a-109">in Numero di argomenti per la funzione.</span><span class="sxs-lookup"><span data-stu-id="ce08a-109">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="ce08a-110">in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugValue che specifica un argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="ce08a-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="ce08a-111">Note</span><span class="sxs-lookup"><span data-stu-id="ce08a-111">Remarks</span></span>

<span data-ttu-id="ce08a-112">Se la funzione è virtuale, `CallFunction` eseguirà il dispatch virtuale.</span><span class="sxs-lookup"><span data-stu-id="ce08a-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="ce08a-113">Se la funzione si trova in un dominio applicazione diverso, si verificherà una transizione purché tutti gli argomenti si trovino anche in tale dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce08a-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="ce08a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce08a-114">Requirements</span></span>

<span data-ttu-id="ce08a-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce08a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ce08a-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce08a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="ce08a-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce08a-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="ce08a-118">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="ce08a-118">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="ce08a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce08a-119">See also</span></span>

- [<span data-ttu-id="ce08a-120">Metodo CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="ce08a-120">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)
