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
ms.openlocfilehash: c3ebe0bcd546feeeb0aa8c962f2b4c8b0562cb6f
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760446"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="82125-102">Metodo ICorThreadpool::CorBindIoCompletionCallback</span><span class="sxs-lookup"><span data-stu-id="82125-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="82125-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="82125-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82125-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82125-104">Syntax</span></span>  
  
```cpp  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="82125-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82125-105">Requirements</span></span>  
 <span data-ttu-id="82125-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82125-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82125-107">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="82125-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82125-108">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="82125-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82125-109">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82125-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82125-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82125-110">See also</span></span>

- [<span data-ttu-id="82125-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="82125-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
