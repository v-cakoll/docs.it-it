---
title: Metodo IAssemblyCacheItem::Commit
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f5cbb7c0b4e3ce6d66d30e812008fc3419d7d7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429092"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="123cf-102">Metodo IAssemblyCacheItem::Commit</span><span class="sxs-lookup"><span data-stu-id="123cf-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="123cf-103">Esegue il commit il riferimento di assembly memorizzati nella cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="123cf-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="123cf-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="123cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="123cf-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="123cf-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="123cf-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="123cf-107">[out, facoltativo] Un valore che indica il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="123cf-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="123cf-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="123cf-108">Requirements</span></span>  
 <span data-ttu-id="123cf-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="123cf-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="123cf-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="123cf-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="123cf-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="123cf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123cf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="123cf-112">See Also</span></span>  
 [<span data-ttu-id="123cf-113">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="123cf-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
