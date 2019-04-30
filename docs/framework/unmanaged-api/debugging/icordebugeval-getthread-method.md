---
title: Metodo ICorDebugEval::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64cc5b6e7c6fe44080b35dc07f029ad311b88ca7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989053"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="8ca31-102">Metodo ICorDebugEval::GetThread</span><span class="sxs-lookup"><span data-stu-id="8ca31-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="8ca31-103">Ottiene il thread in cui questa valutazione è in esecuzione o verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="8ca31-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ca31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ca31-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ca31-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ca31-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="8ca31-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="8ca31-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ca31-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ca31-107">Requirements</span></span>  
 <span data-ttu-id="8ca31-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ca31-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ca31-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ca31-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ca31-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ca31-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ca31-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ca31-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
