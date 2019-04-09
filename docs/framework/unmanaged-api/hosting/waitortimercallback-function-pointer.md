---
title: Puntatore alla funzione WAITORTIMERCALLBACK
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8cf12fc6828c5e439a6a86532f22b8a598a9f03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120991"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="c5c39-102">Puntatore alla funzione WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="c5c39-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="c5c39-103">Punta a una funzione che notifica all'host che un handle di attesa (<xref:System.Threading.WaitHandle>) è stato segnalato o timeout.</span><span class="sxs-lookup"><span data-stu-id="c5c39-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="c5c39-104">Questo puntatore a funzione è stato deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5c39-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5c39-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5c39-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5c39-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c5c39-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="c5c39-107">[in] Un puntatore a un oggetto che contiene le informazioni definite dall'host.</span><span class="sxs-lookup"><span data-stu-id="c5c39-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="c5c39-108">[in] `true` se l'handle di attesa si è verificato un timeout, o `false` se è stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="c5c39-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5c39-109">Note</span><span class="sxs-lookup"><span data-stu-id="c5c39-109">Remarks</span></span>  
 <span data-ttu-id="c5c39-110">La funzione a cui `WAITORTIMERCALLBACK` punti è una funzione di callback e devono essere implementati dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="c5c39-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5c39-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5c39-111">Requirements</span></span>  
 <span data-ttu-id="c5c39-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5c39-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5c39-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c5c39-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5c39-114">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="c5c39-114">**Library:** MSCorWks.dll</span></span>  
  
 **<span data-ttu-id="c5c39-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c5c39-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5c39-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5c39-116">See also</span></span>

- [<span data-ttu-id="c5c39-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="c5c39-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
