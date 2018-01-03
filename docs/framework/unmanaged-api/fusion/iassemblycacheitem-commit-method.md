---
title: Metodo IAssemblyCacheItem::Commit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCacheItem.Commit
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3e1907fa3be4992573f84b4810f7504f3af78397
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="fc8c8-102">Metodo IAssemblyCacheItem::Commit</span><span class="sxs-lookup"><span data-stu-id="fc8c8-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="fc8c8-103">Esegue il commit il riferimento di assembly memorizzati nella cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="fc8c8-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc8c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc8c8-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc8c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc8c8-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="fc8c8-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="fc8c8-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="fc8c8-107">[out, facoltativo] Un valore che indica il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="fc8c8-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc8c8-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc8c8-108">Requirements</span></span>  
 <span data-ttu-id="fc8c8-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc8c8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc8c8-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fc8c8-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fc8c8-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc8c8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc8c8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc8c8-112">See Also</span></span>  
 [<span data-ttu-id="fc8c8-113">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="fc8c8-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
