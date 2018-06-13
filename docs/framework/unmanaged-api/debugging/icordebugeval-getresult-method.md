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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e160eddf667b542929c8dd3790de666a8e8bb77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413059"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="6ac5a-102">Metodo ICorDebugEval::GetResult</span><span class="sxs-lookup"><span data-stu-id="6ac5a-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="6ac5a-103">Ottiene i risultati della valutazione.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ac5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ac5a-104">Syntax</span></span>  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ac5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ac5a-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="6ac5a-106">[out] Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta i risultati della valutazione, se la valutazione viene completata.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ac5a-107">Note</span><span class="sxs-lookup"><span data-stu-id="6ac5a-107">Remarks</span></span>  
 <span data-ttu-id="6ac5a-108">Il `GetResult` metodo è valido solo dopo il completamento della valutazione.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="6ac5a-109">Se la valutazione viene completata regolarmente, `ppResult` specifica i risultati.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="6ac5a-110">Se termina con un'eccezione, il risultato è l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="6ac5a-111">Se la valutazione per un nuovo oggetto, il risultato è il riferimento al nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ac5a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ac5a-112">Requirements</span></span>  
 <span data-ttu-id="6ac5a-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ac5a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ac5a-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6ac5a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ac5a-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6ac5a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ac5a-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ac5a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
