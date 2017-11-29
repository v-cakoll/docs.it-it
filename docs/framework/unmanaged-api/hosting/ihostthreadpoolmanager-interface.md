---
title: Interfaccia IHostThreadPoolManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager
helpviewer_keywords: IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2773042c695320ab1e90d4c5d341e2df5f0f778f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="8f5ab-102">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="8f5ab-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="8f5ab-103">Fornisce metodi che consentono di common language runtime (CLR) per configurare il pool di thread e per accodare gli elementi di lavoro al pool di thread.</span><span class="sxs-lookup"><span data-stu-id="8f5ab-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f5ab-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8f5ab-104">Methods</span></span>  
  
|<span data-ttu-id="8f5ab-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8f5ab-105">Method</span></span>|<span data-ttu-id="8f5ab-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f5ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f5ab-107">GetAvailableThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="8f5ab-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="8f5ab-108">Ottiene il numero di thread nel pool di thread che non stanno elaborando gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8f5ab-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="8f5ab-109">GetMaxThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="8f5ab-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="8f5ab-110">Ottiene il numero massimo di thread gestiti dall'host contemporaneamente nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="8f5ab-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="8f5ab-111">GetMinThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="8f5ab-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="8f5ab-112">Ottiene il numero minimo di thread inattivi gestiti dall'host prima di richieste.</span><span class="sxs-lookup"><span data-stu-id="8f5ab-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="8f5ab-113">QueueUserWorkItem (metodo)</span><span class="sxs-lookup"><span data-stu-id="8f5ab-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="8f5ab-114">Accoda una funzione per l'esecuzione e fornisce un oggetto contenente dati da utilizzare per la funzione.</span><span class="sxs-lookup"><span data-stu-id="8f5ab-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="8f5ab-115">SetMaxThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="8f5ab-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="8f5ab-116">Imposta il numero massimo di thread che l'host può mantenere nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="8f5ab-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="8f5ab-117">SetMinThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="8f5ab-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="8f5ab-118">Imposta il numero minimo di thread inattivi che l'host devono essere conservati in previsione delle richieste.</span><span class="sxs-lookup"><span data-stu-id="8f5ab-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f5ab-119">Note</span><span class="sxs-lookup"><span data-stu-id="8f5ab-119">Remarks</span></span>  
 <span data-ttu-id="8f5ab-120">L'host non è necessario configurare il pool di thread utilizzando i valori specificati in chiamate al `SetMaxThreads` e `SetMinThreads` metodi.</span><span class="sxs-lookup"><span data-stu-id="8f5ab-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="8f5ab-121">In questo caso, l'host deve restituire un valore HRESULT di E_NOTIMPL da questi metodi.</span><span class="sxs-lookup"><span data-stu-id="8f5ab-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f5ab-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f5ab-122">Requirements</span></span>  
 <span data-ttu-id="8f5ab-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f5ab-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f5ab-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8f5ab-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f5ab-125">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f5ab-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f5ab-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f5ab-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f5ab-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f5ab-127">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="8f5ab-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="8f5ab-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
