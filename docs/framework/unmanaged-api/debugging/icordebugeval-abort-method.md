---
title: Metodo ICorDebugEval::Abort
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: 98a9b285323bc3ad94b4f555e72a4b3242519801
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976291"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="0e9d9-102">Metodo ICorDebugEval::Abort</span><span class="sxs-lookup"><span data-stu-id="0e9d9-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="0e9d9-103">Interrompe il calcolo attualmente effettuato dall'oggetto ICorDebugEval.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e9d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e9d9-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0e9d9-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0e9d9-105">Remarks</span></span>  
 <span data-ttu-id="0e9d9-106">Se la valutazione è annidata e non è quella più recente, il `Abort` metodo potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e9d9-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e9d9-107">Requirements</span></span>  
 <span data-ttu-id="0e9d9-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e9d9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e9d9-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e9d9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e9d9-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e9d9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e9d9-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e9d9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
