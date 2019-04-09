---
title: Metodo ICorThreadpool::CorBindIoCompletionCallback
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorBindIoCompletionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3faffbf9dc85c563dac84fc2e4e4d849db5d42d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148525"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="42ca7-102">Metodo ICorThreadpool::CorBindIoCompletionCallback</span><span class="sxs-lookup"><span data-stu-id="42ca7-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="42ca7-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="42ca7-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ca7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42ca7-104">Syntax</span></span>  
  
```  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="42ca7-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42ca7-105">Requirements</span></span>  
 <span data-ttu-id="42ca7-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42ca7-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42ca7-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42ca7-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42ca7-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="42ca7-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="42ca7-109">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="42ca7-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="42ca7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42ca7-110">See also</span></span>

- [<span data-ttu-id="42ca7-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="42ca7-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
