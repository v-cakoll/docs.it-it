---
title: Metodo ICorDebugChain::GetCallee
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetCallee
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b584929d99e641e361de916c402a0d5723e53c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="cfa47-102">Metodo ICorDebugChain::GetCallee</span><span class="sxs-lookup"><span data-stu-id="cfa47-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="cfa47-103">Ottiene la catena di chiamata da questa catena.</span><span class="sxs-lookup"><span data-stu-id="cfa47-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa47-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfa47-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cfa47-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cfa47-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="cfa47-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di chiamata.</span><span class="sxs-lookup"><span data-stu-id="cfa47-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="cfa47-107">Se la catena è attualmente in esecuzione (ovvero, se la catena non è in attesa di una catena di chiamata), `ppChain` sarà null.</span><span class="sxs-lookup"><span data-stu-id="cfa47-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfa47-108">Note</span><span class="sxs-lookup"><span data-stu-id="cfa47-108">Remarks</span></span>  
 <span data-ttu-id="cfa47-109">Questa catena dovrà attendere la catena di chiamata restituire prima di riprendere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cfa47-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="cfa47-110">La catena di chiamate potrebbe essere in un altro thread nel caso di chiamate di marshalling cross-thread.</span><span class="sxs-lookup"><span data-stu-id="cfa47-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfa47-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cfa47-111">Requirements</span></span>  
 <span data-ttu-id="cfa47-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfa47-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa47-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="cfa47-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfa47-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfa47-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfa47-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa47-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
