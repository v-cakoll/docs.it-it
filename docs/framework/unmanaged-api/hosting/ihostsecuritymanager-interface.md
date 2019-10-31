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
ms.openlocfilehash: 9b7cc41848e41976f388e38bf22c9ea0f90abbae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121485"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="5c206-102">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="5c206-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="5c206-103">Fornisce metodi che consentono l'accesso e il controllo sul contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5c206-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c206-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5c206-104">Methods</span></span>  
  
|<span data-ttu-id="5c206-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5c206-105">Method</span></span>|<span data-ttu-id="5c206-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c206-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c206-107">Metodo GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="5c206-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="5c206-108">Ottiene l'oggetto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) richiesto dall'host.</span><span class="sxs-lookup"><span data-stu-id="5c206-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="5c206-109">Metodo ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="5c206-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="5c206-110">Richiede che il codice venga eseguito utilizzando le credenziali dell'identità utente corrente.</span><span class="sxs-lookup"><span data-stu-id="5c206-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="5c206-111">Metodo OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="5c206-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="5c206-112">Apre il token di accesso discrezionale associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="5c206-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="5c206-113">Metodo RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="5c206-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="5c206-114">Termina la rappresentazione dell'identità dell'utente corrente e restituisce il token del thread originale.</span><span class="sxs-lookup"><span data-stu-id="5c206-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="5c206-115">Metodo SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="5c206-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="5c206-116">Imposta il contesto di sicurezza per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5c206-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="5c206-117">Metodo SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="5c206-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="5c206-118">Imposta un handle per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5c206-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c206-119">Note</span><span class="sxs-lookup"><span data-stu-id="5c206-119">Remarks</span></span>  
 <span data-ttu-id="5c206-120">Un host è in grado di controllare l'accesso al codice a token di thread sia dal Common Language Runtime (CLR) sia dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="5c206-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="5c206-121">Può inoltre garantire che le informazioni complete sul contesto di sicurezza vengano passate tra le operazioni asincrone o i punti di codice con accesso limitato al codice.</span><span class="sxs-lookup"><span data-stu-id="5c206-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="5c206-122">`IHostSecurityContext` incapsula le informazioni sul contesto di sicurezza, che è opaco per CLR.</span><span class="sxs-lookup"><span data-stu-id="5c206-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="5c206-123">CLR gestisce internamente il contesto del thread gestito.</span><span class="sxs-lookup"><span data-stu-id="5c206-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="5c206-124">Viene eseguita una query sul `IHostSecurityManager` specifico del processo nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c206-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="5c206-125">Nel thread del finalizzatore, durante l'esecuzione del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="5c206-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="5c206-126">Durante l'esecuzione del costruttore della classe e del modulo.</span><span class="sxs-lookup"><span data-stu-id="5c206-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="5c206-127">In corrispondenza di punti asincroni nel thread di lavoro, in chiamate al metodo [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c206-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="5c206-128">In manutenzione delle porte di completamento I/O.</span><span class="sxs-lookup"><span data-stu-id="5c206-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c206-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c206-129">Requirements</span></span>  
 <span data-ttu-id="5c206-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c206-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c206-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5c206-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c206-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c206-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c206-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c206-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c206-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c206-134">See also</span></span>

- [<span data-ttu-id="5c206-135">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="5c206-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="5c206-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5c206-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
