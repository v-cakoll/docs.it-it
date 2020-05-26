---
title: Metodo IDebuggerThreadControl::StartBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
ms.openlocfilehash: 878dba37728734a777d2f95226b60bfbe9aae16a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805275"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="95be3-102">Metodo IDebuggerThreadControl::StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="95be3-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="95be3-103">Notifica all'host che i servizi di debug stanno per iniziare a bloccare tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="95be3-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95be3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95be3-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95be3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95be3-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="95be3-106">[in] Riservato per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="95be3-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95be3-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="95be3-107">Remarks</span></span>  
 <span data-ttu-id="95be3-108">Il `StartBlockingForDebugger` metodo può essere chiamato su un thread runtime.</span><span class="sxs-lookup"><span data-stu-id="95be3-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95be3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95be3-109">Requirements</span></span>  
 <span data-ttu-id="95be3-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95be3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95be3-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="95be3-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95be3-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="95be3-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95be3-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95be3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95be3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95be3-114">See also</span></span>

- [<span data-ttu-id="95be3-115">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="95be3-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
