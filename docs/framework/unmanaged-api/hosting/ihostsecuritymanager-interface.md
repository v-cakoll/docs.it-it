---
title: Interfaccia IHostSecurityManager
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f45379fe8640ef7e7b3917bac8d10ca956d75ffb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223758"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="0b54d-102">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="0b54d-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="0b54d-103">Fornisce metodi che consentono l'accesso e controllo sul contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0b54d-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b54d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0b54d-104">Methods</span></span>  
  
|<span data-ttu-id="0b54d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0b54d-105">Method</span></span>|<span data-ttu-id="0b54d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b54d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b54d-107">Metodo GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="0b54d-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="0b54d-108">Ottiene l'oggetto richiesto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) dall'host.</span><span class="sxs-lookup"><span data-stu-id="0b54d-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="0b54d-109">Metodo ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="0b54d-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="0b54d-110">Le richieste che codice eseguito con le credenziali dell'identità dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="0b54d-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="0b54d-111">Metodo OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="0b54d-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="0b54d-112">Apre il token di accesso discrezionale associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="0b54d-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="0b54d-113">Metodo RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="0b54d-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="0b54d-114">Termina la rappresentazione dell'identità dell'utente corrente e restituisce il token del thread originale.</span><span class="sxs-lookup"><span data-stu-id="0b54d-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="0b54d-115">Metodo SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="0b54d-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="0b54d-116">Imposta il contesto di sicurezza per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0b54d-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="0b54d-117">Metodo SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="0b54d-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="0b54d-118">Imposta un handle per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0b54d-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b54d-119">Note</span><span class="sxs-lookup"><span data-stu-id="0b54d-119">Remarks</span></span>  
 <span data-ttu-id="0b54d-120">Un host può controllare l'accesso di codice ai token di thread dal common language runtime (CLR) e codice utente.</span><span class="sxs-lookup"><span data-stu-id="0b54d-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="0b54d-121">Inoltre possibile garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con l'accesso al codice con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="0b54d-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> `IHostSecurityContext` <span data-ttu-id="0b54d-122">incapsula questo informazioni sul contesto di sicurezza, è opache al CLR.</span><span class="sxs-lookup"><span data-stu-id="0b54d-122">encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="0b54d-123">Common Language Runtime gestisce il contesto di thread gestiti internamente.</span><span class="sxs-lookup"><span data-stu-id="0b54d-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="0b54d-124">Viene eseguita una query, specifico del processo `IHostSecurityManager` nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b54d-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
-   <span data-ttu-id="0b54d-125">Nel thread finalizzatore, durante l'esecuzione del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="0b54d-125">On the finalizer thread, during finalizer execution.</span></span>  
  
-   <span data-ttu-id="0b54d-126">Durante l'esecuzione dei costruttori di classe e modulo.</span><span class="sxs-lookup"><span data-stu-id="0b54d-126">During class and module constructor execution.</span></span>  
  
-   <span data-ttu-id="0b54d-127">In corrispondenza di punti asincroni sul thread di lavoro, nelle chiamate al [IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="0b54d-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
-   <span data-ttu-id="0b54d-128">Nella manutenzione di porte di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="0b54d-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b54d-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b54d-129">Requirements</span></span>  
 <span data-ttu-id="0b54d-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b54d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b54d-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b54d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b54d-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0b54d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0b54d-133">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0b54d-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b54d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b54d-134">See also</span></span>

- [<span data-ttu-id="0b54d-135">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="0b54d-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="0b54d-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="0b54d-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
