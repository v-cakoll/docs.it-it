---
title: Metodo IGCHost::Collect
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bce005a677dcb74c176a6dddfb2726f6b1fd0e8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436907"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="d5651-102">Metodo IGCHost::Collect</span><span class="sxs-lookup"><span data-stu-id="d5651-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="d5651-103">Forza una raccolta per la generazione specificata, indipendentemente dallo stato dell'operazione di garbage collection corrente.</span><span class="sxs-lookup"><span data-stu-id="d5651-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5651-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5651-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5651-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5651-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="d5651-106">[in] La generazione su cui eseguire l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="d5651-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="d5651-107">Il valore-1 indica che tutte le generazioni verranno eseguita una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="d5651-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5651-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5651-108">Requirements</span></span>  
 <span data-ttu-id="d5651-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5651-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5651-110">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="d5651-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="d5651-111">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d5651-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5651-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5651-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5651-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5651-113">See Also</span></span>  
 [<span data-ttu-id="d5651-114">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="d5651-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
