---
title: Metodo IGCHost::Collect
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.Collect
api_location: mscoree.dll
api_type: COM
f1_keywords: Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d97a988db48cc9bfdf8cf1e260c28e0169eb73f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="igchostcollect-method"></a><span data-ttu-id="6d6e9-102">Metodo IGCHost::Collect</span><span class="sxs-lookup"><span data-stu-id="6d6e9-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="6d6e9-103">Forza una raccolta per la generazione specificata, indipendentemente dallo stato dell'operazione di garbage collection corrente.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d6e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d6e9-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d6e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6d6e9-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="6d6e9-106">[in] La generazione su cui eseguire l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="6d6e9-107">Il valore-1 indica che tutte le generazioni verranno eseguita una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d6e9-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d6e9-108">Requirements</span></span>  
 <span data-ttu-id="6d6e9-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d6e9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d6e9-110">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="6d6e9-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="6d6e9-111">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d6e9-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d6e9-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d6e9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6e9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d6e9-113">See Also</span></span>  
 [<span data-ttu-id="6d6e9-114">IGCHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6d6e9-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
