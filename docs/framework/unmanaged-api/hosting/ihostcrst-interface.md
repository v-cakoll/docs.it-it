---
title: Interfaccia IHostCrst
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f2ef8299911905d651ad5c3076dc9c74f397f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438919"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="68d2c-102">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="68d2c-102">IHostCrst Interface</span></span>
<span data-ttu-id="68d2c-103">Serve come rappresentazione dell'host di una sezione critica di threading.</span><span class="sxs-lookup"><span data-stu-id="68d2c-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68d2c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="68d2c-104">Methods</span></span>  
  
|<span data-ttu-id="68d2c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="68d2c-105">Method</span></span>|<span data-ttu-id="68d2c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68d2c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68d2c-107">Metodo Enter</span><span class="sxs-lookup"><span data-stu-id="68d2c-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="68d2c-108">Entra nella sezione critica.</span><span class="sxs-lookup"><span data-stu-id="68d2c-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="68d2c-109">Metodo Leave</span><span class="sxs-lookup"><span data-stu-id="68d2c-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="68d2c-110">Esce dalla sezione critica.</span><span class="sxs-lookup"><span data-stu-id="68d2c-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="68d2c-111">Metodo SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="68d2c-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="68d2c-112">Imposta il conteggio di selezione per la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="68d2c-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="68d2c-113">Metodo TryEnter</span><span class="sxs-lookup"><span data-stu-id="68d2c-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="68d2c-114">Tenta di accedere immediatamente sezione critica e i report l'esito.</span><span class="sxs-lookup"><span data-stu-id="68d2c-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68d2c-115">Note</span><span class="sxs-lookup"><span data-stu-id="68d2c-115">Remarks</span></span>  
 <span data-ttu-id="68d2c-116">`IHostCrst` consente a common language runtime (CLR) per comunicare direttamente con la rappresentazione dall'host di una sezione critica, anziché usare funzioni Win32, ad esempio `EnterCriticalSection` o `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="68d2c-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68d2c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="68d2c-117">Requirements</span></span>  
 <span data-ttu-id="68d2c-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68d2c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68d2c-119">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="68d2c-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68d2c-120">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="68d2c-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68d2c-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68d2c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d2c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68d2c-122">See Also</span></span>  
 [<span data-ttu-id="68d2c-123">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="68d2c-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="68d2c-124">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="68d2c-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="68d2c-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="68d2c-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
