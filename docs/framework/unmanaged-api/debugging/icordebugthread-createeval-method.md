---
title: Metodo ICorDebugThread::CreateEval
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e2d99d85a6e6b09558e5941d08a7f522aaf66cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421817"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="e79cf-102">Metodo ICorDebugThread::CreateEval</span><span class="sxs-lookup"><span data-stu-id="e79cf-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="e79cf-103">Crea un oggetto ICorDebugEval che raccoglie ed espone la funzionalità di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="e79cf-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e79cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e79cf-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e79cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e79cf-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="e79cf-106">[out] Un puntatore all'indirizzo di un `ICorDebugEval` che raccoglie ed espone la funzionalità di questo thread.</span><span class="sxs-lookup"><span data-stu-id="e79cf-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e79cf-107">Note</span><span class="sxs-lookup"><span data-stu-id="e79cf-107">Remarks</span></span>  
 <span data-ttu-id="e79cf-108">L'oggetto di valutazione determinerà una nuova catena sul thread prima di effettuare il relativo calcolo.</span><span class="sxs-lookup"><span data-stu-id="e79cf-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="e79cf-109">In questo modo si interromperà il calcolo viene eseguito sul thread fino al completamento della valutazione.</span><span class="sxs-lookup"><span data-stu-id="e79cf-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e79cf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e79cf-110">Requirements</span></span>  
 <span data-ttu-id="e79cf-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e79cf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e79cf-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e79cf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e79cf-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e79cf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e79cf-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e79cf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
