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
ms.openlocfilehash: bac29b5950f1547c5c60ac716d40d2ef4b1a2cc2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842480"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="bd914-102">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="bd914-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="bd914-103">Fornisce metodi che consentono al Common Language Runtime (CLR) di configurare il pool di thread e di accodare gli elementi di lavoro al pool di thread.</span><span class="sxs-lookup"><span data-stu-id="bd914-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bd914-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="bd914-104">Methods</span></span>  
  
|<span data-ttu-id="bd914-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="bd914-105">Method</span></span>|<span data-ttu-id="bd914-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd914-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd914-107">Metodo GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="bd914-107">GetAvailableThreads Method</span></span>](ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="bd914-108">Ottiene il numero di thread nel pool di thread che non stanno attualmente elaborando elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bd914-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="bd914-109">Metodo GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="bd914-109">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="bd914-110">Ottiene il numero massimo di thread che l'host gestisce simultaneamente nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="bd914-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="bd914-111">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="bd914-111">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="bd914-112">Ottiene il numero minimo di thread inattivi gestiti dall'host in previsione di richieste.</span><span class="sxs-lookup"><span data-stu-id="bd914-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="bd914-113">Metodo QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="bd914-113">QueueUserWorkItem Method</span></span>](ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="bd914-114">Accoda una funzione per l'esecuzione e fornisce un oggetto contenente i dati che devono essere utilizzati dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="bd914-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="bd914-115">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="bd914-115">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="bd914-116">Imposta il numero massimo di thread che l'host è in grado di gestire nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="bd914-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="bd914-117">Metodo SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="bd914-117">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="bd914-118">Imposta il numero minimo di thread inattivi che l'host deve gestire in previsione di richieste.</span><span class="sxs-lookup"><span data-stu-id="bd914-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd914-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bd914-119">Remarks</span></span>  
 <span data-ttu-id="bd914-120">L'host non è necessario per configurare il pool di thread usando i valori specificati nelle chiamate ai `SetMaxThreads` metodi e `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="bd914-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="bd914-121">In questo caso, l'host deve restituire un valore HRESULT di E_NOTIMPL da questi metodi.</span><span class="sxs-lookup"><span data-stu-id="bd914-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd914-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd914-122">Requirements</span></span>  
 <span data-ttu-id="bd914-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd914-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd914-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bd914-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd914-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bd914-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd914-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd914-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd914-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd914-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="bd914-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="bd914-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
