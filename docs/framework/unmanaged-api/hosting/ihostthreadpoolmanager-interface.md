---
title: Interfaccia IHostThreadPoolManager
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7fc0a271a9c62406d2942f387a5458e21211116
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522726"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="bf653-102">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="bf653-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="bf653-103">Fornisce metodi che consentono a common language runtime (CLR) per configurare il pool di thread e accodare elementi di lavoro al pool di thread.</span><span class="sxs-lookup"><span data-stu-id="bf653-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf653-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="bf653-104">Methods</span></span>  
  
|<span data-ttu-id="bf653-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="bf653-105">Method</span></span>|<span data-ttu-id="bf653-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf653-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf653-107">Metodo GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="bf653-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="bf653-108">Ottiene il numero di thread nel pool di thread che non stanno elaborando gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bf653-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="bf653-109">Metodo GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="bf653-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="bf653-110">Ottiene il numero massimo di thread che gestisce l'host contemporaneamente nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="bf653-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="bf653-111">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="bf653-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="bf653-112">Ottiene il numero minimo di thread inattivi che gestisce l'host in previsione delle richieste.</span><span class="sxs-lookup"><span data-stu-id="bf653-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="bf653-113">Metodo QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="bf653-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="bf653-114">Accoda una funzione per l'esecuzione e fornisce un oggetto contenente dati da utilizzare dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="bf653-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="bf653-115">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="bf653-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="bf653-116">Imposta il numero massimo di thread che l'host può mantenere nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="bf653-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="bf653-117">Metodo SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="bf653-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="bf653-118">Imposta il numero minimo di thread inattivi che l'host devono essere conservati in previsione delle richieste.</span><span class="sxs-lookup"><span data-stu-id="bf653-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf653-119">Note</span><span class="sxs-lookup"><span data-stu-id="bf653-119">Remarks</span></span>  
 <span data-ttu-id="bf653-120">L'host non è necessario configurare il pool di thread usando i valori specificati nelle chiamate al `SetMaxThreads` e `SetMinThreads` metodi.</span><span class="sxs-lookup"><span data-stu-id="bf653-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="bf653-121">In questo caso, l'host deve restituire un valore HRESULT E_NOTIMPL da questi metodi.</span><span class="sxs-lookup"><span data-stu-id="bf653-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf653-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf653-122">Requirements</span></span>  
 <span data-ttu-id="bf653-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf653-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf653-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bf653-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf653-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bf653-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf653-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf653-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf653-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf653-127">See also</span></span>
- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="bf653-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="bf653-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
