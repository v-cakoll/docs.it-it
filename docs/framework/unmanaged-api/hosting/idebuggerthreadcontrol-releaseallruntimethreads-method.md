---
title: Metodo IDebuggerThreadControl::ReleaseAllRuntimeThreads
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
ms.openlocfilehash: 50ffb33456f942a71089f9bc44daa07f6b77ab21
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805291"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="acf79-102">Metodo IDebuggerThreadControl::ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="acf79-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="acf79-103">Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread bloccati.</span><span class="sxs-lookup"><span data-stu-id="acf79-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="acf79-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="acf79-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="acf79-105">Remarks</span></span>  
 <span data-ttu-id="acf79-106">Il `ReleaseAllRuntimeThreads` metodo non verrà mai chiamato su un thread runtime.</span><span class="sxs-lookup"><span data-stu-id="acf79-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="acf79-107">Se l'host dispone di un thread di runtime bloccato, dovrebbe rilasciarlo ora.</span><span class="sxs-lookup"><span data-stu-id="acf79-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acf79-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="acf79-108">Requirements</span></span>  
 <span data-ttu-id="acf79-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acf79-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acf79-110">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="acf79-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acf79-111">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="acf79-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acf79-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acf79-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf79-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acf79-113">See also</span></span>

- [<span data-ttu-id="acf79-114">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="acf79-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
