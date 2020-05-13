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
ms.openlocfilehash: f66ef88646c314502dcb610cec8ce822cab1fca2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379287"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="d4b1d-102">Metodo ICorDebugThread::CreateEval</span><span class="sxs-lookup"><span data-stu-id="d4b1d-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="d4b1d-103">Crea un oggetto ICorDebugEval che raccoglie ed espone la funzionalità di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="d4b1d-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4b1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4b1d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4b1d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4b1d-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="d4b1d-106">out Puntatore all'indirizzo di un `ICorDebugEval` oggetto che raccoglie ed espone la funzionalità di questo thread.</span><span class="sxs-lookup"><span data-stu-id="d4b1d-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4b1d-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d4b1d-107">Remarks</span></span>  
 <span data-ttu-id="d4b1d-108">L'oggetto di valutazione effettuerà il push di una nuova catena nel thread prima di eseguire il calcolo.</span><span class="sxs-lookup"><span data-stu-id="d4b1d-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="d4b1d-109">Questa operazione interrompe il calcolo attualmente eseguito sul thread fino al completamento della valutazione.</span><span class="sxs-lookup"><span data-stu-id="d4b1d-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4b1d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4b1d-110">Requirements</span></span>  
 <span data-ttu-id="d4b1d-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4b1d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4b1d-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4b1d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4b1d-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4b1d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4b1d-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4b1d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
