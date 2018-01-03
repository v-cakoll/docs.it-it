---
title: Metodo ICorDebugEval::Abort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.Abort
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 064febeec32e5c43b6b73ef2b3a44625f151eb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="d2de9-102">Metodo ICorDebugEval::Abort</span><span class="sxs-lookup"><span data-stu-id="d2de9-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="d2de9-103">Interrompe il calcolo di che questo oggetto ICorDebugEval attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d2de9-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2de9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2de9-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d2de9-105">Note</span><span class="sxs-lookup"><span data-stu-id="d2de9-105">Remarks</span></span>  
 <span data-ttu-id="d2de9-106">Se la valutazione è annidata e non è quella più recente, il `Abort` metodo potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="d2de9-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2de9-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2de9-107">Requirements</span></span>  
 <span data-ttu-id="d2de9-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2de9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2de9-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d2de9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2de9-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2de9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2de9-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2de9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
