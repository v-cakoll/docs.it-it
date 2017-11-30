---
title: Interfaccia IHostSecurityManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager
helpviewer_keywords: IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b3d67328dbf68491d319e55e63a9c3540cd1ee4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="5cadf-102">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="5cadf-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="5cadf-103">Fornisce metodi che consentono l'accesso e controllo sul contesto di protezione del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5cadf-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5cadf-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5cadf-104">Methods</span></span>  
  
|<span data-ttu-id="5cadf-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5cadf-105">Method</span></span>|<span data-ttu-id="5cadf-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5cadf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5cadf-107">GetSecurityContext (metodo)</span><span class="sxs-lookup"><span data-stu-id="5cadf-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="5cadf-108">Ottiene l'oggetto richiesto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) dall'host.</span><span class="sxs-lookup"><span data-stu-id="5cadf-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="5cadf-109">ImpersonateLoggedOnUser (metodo)</span><span class="sxs-lookup"><span data-stu-id="5cadf-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="5cadf-110">Le richieste di codice da eseguire utilizzando le credenziali dell'identità dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="5cadf-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="5cadf-111">OpenThreadToken (metodo)</span><span class="sxs-lookup"><span data-stu-id="5cadf-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="5cadf-112">Apre il token di accesso discrezionale associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="5cadf-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="5cadf-113">RevertToSelf (metodo)</span><span class="sxs-lookup"><span data-stu-id="5cadf-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="5cadf-114">Termina la rappresentazione dell'identità dell'utente corrente e restituisce il token thread originale.</span><span class="sxs-lookup"><span data-stu-id="5cadf-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="5cadf-115">SetSecurityContext (metodo)</span><span class="sxs-lookup"><span data-stu-id="5cadf-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="5cadf-116">Imposta il contesto di sicurezza per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5cadf-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="5cadf-117">SetThreadToken (metodo)</span><span class="sxs-lookup"><span data-stu-id="5cadf-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="5cadf-118">Imposta un handle per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5cadf-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cadf-119">Note</span><span class="sxs-lookup"><span data-stu-id="5cadf-119">Remarks</span></span>  
 <span data-ttu-id="5cadf-120">Un host può controllare l'accesso di codice ai token di thread dal common language runtime (CLR) e codice utente.</span><span class="sxs-lookup"><span data-stu-id="5cadf-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="5cadf-121">Può inoltre garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con accesso di codice con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="5cadf-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="5cadf-122">`IHostSecurityContext`incapsula queste informazioni di contesto di sicurezza, sono opache a CLR.</span><span class="sxs-lookup"><span data-stu-id="5cadf-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="5cadf-123">Common Language Runtime gestisce il contesto di thread gestiti internamente.</span><span class="sxs-lookup"><span data-stu-id="5cadf-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="5cadf-124">Viene eseguita una query specifica del processo `IHostSecurityManager` nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cadf-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
-   <span data-ttu-id="5cadf-125">Nel thread finalizzatore, durante l'esecuzione del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="5cadf-125">On the finalizer thread, during finalizer execution.</span></span>  
  
-   <span data-ttu-id="5cadf-126">Durante l'esecuzione di costruttore di classe e modulo.</span><span class="sxs-lookup"><span data-stu-id="5cadf-126">During class and module constructor execution.</span></span>  
  
-   <span data-ttu-id="5cadf-127">In punti asincroni del thread di lavoro, nelle chiamate al [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="5cadf-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
-   <span data-ttu-id="5cadf-128">In manutenzione di porte di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="5cadf-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cadf-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cadf-129">Requirements</span></span>  
 <span data-ttu-id="5cadf-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cadf-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cadf-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="5cadf-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5cadf-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5cadf-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5cadf-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cadf-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cadf-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cadf-134">See Also</span></span>  
 [<span data-ttu-id="5cadf-135">IHostSecurityContext (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5cadf-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="5cadf-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5cadf-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
