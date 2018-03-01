---
title: Metodo ICorDebugChain::GetCaller
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 17c55358a1d502ce5946617556222282ac4c4fca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="6ff1a-102">Metodo ICorDebugChain::GetCaller</span><span class="sxs-lookup"><span data-stu-id="6ff1a-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="6ff1a-103">Ottiene la catena che ha chiamato questa catena.</span><span class="sxs-lookup"><span data-stu-id="6ff1a-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ff1a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ff1a-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ff1a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ff1a-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="6ff1a-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6ff1a-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="6ff1a-107">Se la catena è stata chiamata spontaneamente (come sarebbe se la catena o il debugger inizializzato lo stack di chiamate), `ppChain` sarà null.</span><span class="sxs-lookup"><span data-stu-id="6ff1a-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ff1a-108">Note</span><span class="sxs-lookup"><span data-stu-id="6ff1a-108">Remarks</span></span>  
 <span data-ttu-id="6ff1a-109">La catena di chiamata potrebbe essere in un thread differente, se è stato effettuato il marshalling della chiamata tra thread.</span><span class="sxs-lookup"><span data-stu-id="6ff1a-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ff1a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ff1a-110">Requirements</span></span>  
 <span data-ttu-id="6ff1a-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ff1a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ff1a-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6ff1a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ff1a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ff1a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ff1a-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ff1a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
