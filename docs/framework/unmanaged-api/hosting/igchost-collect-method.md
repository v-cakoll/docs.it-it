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
ms.openlocfilehash: 9c4fa79f4918412720592bce449a001a349ae657
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766559"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="1fc1f-102">Metodo IGCHost::Collect</span><span class="sxs-lookup"><span data-stu-id="1fc1f-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="1fc1f-103">Forza una raccolta Garbage Collection per la generazione specificata, indipendentemente dallo stato di garbage collection corrente.</span><span class="sxs-lookup"><span data-stu-id="1fc1f-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fc1f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fc1f-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fc1f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1fc1f-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="1fc1f-106">[in] La generazione in cui eseguire l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1fc1f-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="1fc1f-107">Il valore -1 indica che tutte le generazioni verrà eseguita una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1fc1f-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fc1f-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1fc1f-108">Requirements</span></span>  
 <span data-ttu-id="1fc1f-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fc1f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fc1f-110">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="1fc1f-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="1fc1f-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1fc1f-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1fc1f-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fc1f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc1f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fc1f-113">See also</span></span>

- [<span data-ttu-id="1fc1f-114">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="1fc1f-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
