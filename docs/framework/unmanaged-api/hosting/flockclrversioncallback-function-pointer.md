---
title: Puntatore alla funzione FLockClrVersionCallback
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
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 90b3bd053eb2e1161d6bb107afe9b3c627b1b207
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="7cd1c-102">Puntatore alla funzione FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="7cd1c-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="7cd1c-103">Punta a una funzione che il common language runtime (CLR) chiama per indicare che l'inizializzazione è avviato o completato.</span><span class="sxs-lookup"><span data-stu-id="7cd1c-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="7cd1c-104">Questo puntatore a funzione è stato deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cd1c-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cd1c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7cd1c-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="7cd1c-106">Note</span><span class="sxs-lookup"><span data-stu-id="7cd1c-106">Remarks</span></span>  
 <span data-ttu-id="7cd1c-107">Questa funzione è implementata dall'host.</span><span class="sxs-lookup"><span data-stu-id="7cd1c-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cd1c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7cd1c-108">Requirements</span></span>  
 <span data-ttu-id="7cd1c-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cd1c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cd1c-110">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7cd1c-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7cd1c-111">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="7cd1c-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="7cd1c-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cd1c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd1c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cd1c-113">See Also</span></span>  
 [<span data-ttu-id="7cd1c-114">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="7cd1c-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 [<span data-ttu-id="7cd1c-115">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="7cd1c-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
