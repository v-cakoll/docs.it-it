---
title: Interfaccia IHostSecurityManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 44f2272c0f4e1423c222a004559d7bbd58237d82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="a4aab-102">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="a4aab-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="a4aab-103">Fornisce metodi che consentono l'accesso e controllo sul contesto di protezione del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a4aab-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4aab-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a4aab-104">Methods</span></span>  
  
|<span data-ttu-id="a4aab-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a4aab-105">Method</span></span>|<span data-ttu-id="a4aab-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4aab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4aab-107">Metodo GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="a4aab-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="a4aab-108">Ottiene l'oggetto richiesto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) dall'host.</span><span class="sxs-lookup"><span data-stu-id="a4aab-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="a4aab-109">Metodo ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="a4aab-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="a4aab-110">Le richieste di codice da eseguire utilizzando le credenziali dell'identità dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="a4aab-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="a4aab-111">Metodo OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="a4aab-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="a4aab-112">Apre il token di accesso discrezionale associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="a4aab-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="a4aab-113">Metodo RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="a4aab-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="a4aab-114">Termina la rappresentazione dell'identità dell'utente corrente e restituisce il token thread originale.</span><span class="sxs-lookup"><span data-stu-id="a4aab-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="a4aab-115">Metodo SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="a4aab-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="a4aab-116">Imposta il contesto di sicurezza per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a4aab-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="a4aab-117">Metodo SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="a4aab-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="a4aab-118">Imposta un handle per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a4aab-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4aab-119">Note</span><span class="sxs-lookup"><span data-stu-id="a4aab-119">Remarks</span></span>  
 <span data-ttu-id="a4aab-120">Un host può controllare l'accesso di codice ai token di thread dal common language runtime (CLR) e codice utente.</span><span class="sxs-lookup"><span data-stu-id="a4aab-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="a4aab-121">Può inoltre garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con accesso di codice con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="a4aab-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="a4aab-122">`IHostSecurityContext`incapsula queste informazioni di contesto di sicurezza, sono opache a CLR.</span><span class="sxs-lookup"><span data-stu-id="a4aab-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="a4aab-123">Common Language Runtime gestisce il contesto di thread gestiti internamente.</span><span class="sxs-lookup"><span data-stu-id="a4aab-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="a4aab-124">Viene eseguita una query specifica del processo `IHostSecurityManager` nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4aab-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
-   <span data-ttu-id="a4aab-125">Nel thread finalizzatore, durante l'esecuzione del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="a4aab-125">On the finalizer thread, during finalizer execution.</span></span>  
  
-   <span data-ttu-id="a4aab-126">Durante l'esecuzione di costruttore di classe e modulo.</span><span class="sxs-lookup"><span data-stu-id="a4aab-126">During class and module constructor execution.</span></span>  
  
-   <span data-ttu-id="a4aab-127">In punti asincroni del thread di lavoro, nelle chiamate al [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="a4aab-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
-   <span data-ttu-id="a4aab-128">In manutenzione di porte di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="a4aab-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4aab-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4aab-129">Requirements</span></span>  
 <span data-ttu-id="a4aab-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4aab-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4aab-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a4aab-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4aab-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4aab-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4aab-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4aab-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4aab-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4aab-134">See Also</span></span>  
 [<span data-ttu-id="a4aab-135">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="a4aab-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="a4aab-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="a4aab-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
