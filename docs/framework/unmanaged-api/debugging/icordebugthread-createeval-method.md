---
title: Metodo ICorDebugThread::CreateEval
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.CreateEval
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aebabf12e6dcf12f0e1e1f24ec2ad69ea55ec86c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="8cad9-102">Metodo ICorDebugThread::CreateEval</span><span class="sxs-lookup"><span data-stu-id="8cad9-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="8cad9-103">Crea un oggetto ICorDebugEval che raccoglie ed espone la funzionalità di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="8cad9-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cad9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8cad9-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8cad9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8cad9-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="8cad9-106">[out] Un puntatore all'indirizzo di un `ICorDebugEval` che raccoglie ed espone la funzionalità di questo thread.</span><span class="sxs-lookup"><span data-stu-id="8cad9-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cad9-107">Note</span><span class="sxs-lookup"><span data-stu-id="8cad9-107">Remarks</span></span>  
 <span data-ttu-id="8cad9-108">L'oggetto di valutazione determinerà una nuova catena sul thread prima di effettuare il relativo calcolo.</span><span class="sxs-lookup"><span data-stu-id="8cad9-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="8cad9-109">In questo modo si interromperà il calcolo viene eseguito sul thread fino al completamento della valutazione.</span><span class="sxs-lookup"><span data-stu-id="8cad9-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cad9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8cad9-110">Requirements</span></span>  
 <span data-ttu-id="8cad9-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cad9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cad9-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8cad9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cad9-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cad9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cad9-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cad9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
