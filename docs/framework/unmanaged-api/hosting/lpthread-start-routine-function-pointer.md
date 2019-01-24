---
title: Puntatore alla funzione LPTHREAD_START_ROUTINE
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 395ba0eb2c47b52192d8058cc5020e45c00148e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689929"
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="ad878-102">Puntatore alla funzione LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="ad878-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="ad878-103">Punta a una funzione che notifica all'host che ha avviato un thread da eseguire.</span><span class="sxs-lookup"><span data-stu-id="ad878-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="ad878-104">Questo puntatore a funzione è stato deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad878-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad878-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad878-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad878-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad878-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="ad878-107">[in] Puntatore al codice che ha avviato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ad878-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad878-108">Note</span><span class="sxs-lookup"><span data-stu-id="ad878-108">Remarks</span></span>  
 <span data-ttu-id="ad878-109">La funzione a cui `LPTHREAD_START_ROUTINE` punti è una funzione di callback e devono essere implementati dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="ad878-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad878-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad878-110">Requirements</span></span>  
 <span data-ttu-id="ad878-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad878-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad878-112">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ad878-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad878-113">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="ad878-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="ad878-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad878-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad878-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad878-115">See also</span></span>
- [<span data-ttu-id="ad878-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="ad878-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
