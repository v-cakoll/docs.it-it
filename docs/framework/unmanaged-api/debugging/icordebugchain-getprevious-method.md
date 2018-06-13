---
title: Metodo ICorDebugChain::GetPrevious
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c0545440ed63ba914229249080ec9f6be8eb2b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402253"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="e231b-102">Metodo ICorDebugChain::GetPrevious</span><span class="sxs-lookup"><span data-stu-id="e231b-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="e231b-103">Ottiene la catena di frame precedente per il thread.</span><span class="sxs-lookup"><span data-stu-id="e231b-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e231b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e231b-104">Syntax</span></span>  
  
```  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e231b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e231b-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="e231b-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di frame per il thread precedente.</span><span class="sxs-lookup"><span data-stu-id="e231b-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="e231b-107">Se questa è la prima catena, `ppChain` è null.</span><span class="sxs-lookup"><span data-stu-id="e231b-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e231b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e231b-108">Requirements</span></span>  
 <span data-ttu-id="e231b-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e231b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e231b-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e231b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e231b-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e231b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e231b-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e231b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
