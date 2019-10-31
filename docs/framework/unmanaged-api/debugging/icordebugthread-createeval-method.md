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
ms.openlocfilehash: 0c622e0eba27f501446d2b7d9d264ee0834e869c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133622"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="0367c-102">Metodo ICorDebugThread::CreateEval</span><span class="sxs-lookup"><span data-stu-id="0367c-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="0367c-103">Crea un oggetto ICorDebugEval che raccoglie ed espone la funzionalità di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="0367c-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0367c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0367c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0367c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0367c-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="0367c-106">out Puntatore all'indirizzo di un `ICorDebugEval` oggetto che raccoglie ed espone la funzionalità di questo thread.</span><span class="sxs-lookup"><span data-stu-id="0367c-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0367c-107">Note</span><span class="sxs-lookup"><span data-stu-id="0367c-107">Remarks</span></span>  
 <span data-ttu-id="0367c-108">L'oggetto di valutazione effettuerà il push di una nuova catena nel thread prima di eseguire il calcolo.</span><span class="sxs-lookup"><span data-stu-id="0367c-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="0367c-109">Questa operazione interrompe il calcolo attualmente eseguito sul thread fino al completamento della valutazione.</span><span class="sxs-lookup"><span data-stu-id="0367c-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0367c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0367c-110">Requirements</span></span>  
 <span data-ttu-id="0367c-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0367c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0367c-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0367c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0367c-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0367c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0367c-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0367c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
