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
ms.openlocfilehash: 3073f391efd483a161d9e7bc3787a6ce180aa28c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133372"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="13f9e-102">Metodo ICorThreadpool::CorBindIoCompletionCallback</span><span class="sxs-lookup"><span data-stu-id="13f9e-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="13f9e-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="13f9e-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13f9e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13f9e-104">Syntax</span></span>  
  
```cpp  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="13f9e-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13f9e-105">Requirements</span></span>  
 <span data-ttu-id="13f9e-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13f9e-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13f9e-107">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="13f9e-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13f9e-108">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="13f9e-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13f9e-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13f9e-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f9e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13f9e-110">See also</span></span>

- [<span data-ttu-id="13f9e-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="13f9e-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
