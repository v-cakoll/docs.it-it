---
title: Metodo ICorDebugEval::GetResult
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 2d065d956319076d3b92eddafd4a2c25ffbfbac1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976265"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="fe38b-102">Metodo ICorDebugEval::GetResult</span><span class="sxs-lookup"><span data-stu-id="fe38b-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="fe38b-103">Ottiene i risultati della valutazione.</span><span class="sxs-lookup"><span data-stu-id="fe38b-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe38b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe38b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe38b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe38b-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="fe38b-106">out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta i risultati della valutazione, se la valutazione viene completata normalmente.</span><span class="sxs-lookup"><span data-stu-id="fe38b-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe38b-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fe38b-107">Remarks</span></span>  
 <span data-ttu-id="fe38b-108">Il `GetResult` metodo è valido solo dopo il completamento della valutazione.</span><span class="sxs-lookup"><span data-stu-id="fe38b-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="fe38b-109">Se la valutazione viene completata normalmente, `ppResult` specifica i risultati.</span><span class="sxs-lookup"><span data-stu-id="fe38b-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="fe38b-110">Se termina con un'eccezione, il risultato è l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="fe38b-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="fe38b-111">Se la valutazione era per un nuovo oggetto, il risultato è il riferimento al nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="fe38b-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe38b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe38b-112">Requirements</span></span>  
 <span data-ttu-id="fe38b-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe38b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe38b-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe38b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe38b-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe38b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe38b-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe38b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
