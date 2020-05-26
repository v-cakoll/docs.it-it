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
ms.openlocfilehash: b2c334c7a757c2f4044d08787bdae93ffc2804e4
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803888"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="57fba-102">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="57fba-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="57fba-103">Fornisce metodi che consentono l'accesso e il controllo sul contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="57fba-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57fba-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="57fba-104">Methods</span></span>  
  
|<span data-ttu-id="57fba-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="57fba-105">Method</span></span>|<span data-ttu-id="57fba-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57fba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57fba-107">Metodo GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="57fba-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="57fba-108">Ottiene l'oggetto [IHostSecurityContext](ihostsecuritycontext-interface.md) richiesto dall'host.</span><span class="sxs-lookup"><span data-stu-id="57fba-108">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="57fba-109">Metodo ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="57fba-109">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="57fba-110">Richiede che il codice venga eseguito utilizzando le credenziali dell'identità utente corrente.</span><span class="sxs-lookup"><span data-stu-id="57fba-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="57fba-111">Metodo OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="57fba-111">OpenThreadToken Method</span></span>](ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="57fba-112">Apre il token di accesso discrezionale associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="57fba-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="57fba-113">Metodo RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="57fba-113">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="57fba-114">Termina la rappresentazione dell'identità dell'utente corrente e restituisce il token del thread originale.</span><span class="sxs-lookup"><span data-stu-id="57fba-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="57fba-115">Metodo SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="57fba-115">SetSecurityContext Method</span></span>](ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="57fba-116">Imposta il contesto di sicurezza per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="57fba-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="57fba-117">Metodo SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="57fba-117">SetThreadToken Method</span></span>](ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="57fba-118">Imposta un handle per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="57fba-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57fba-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="57fba-119">Remarks</span></span>  
 <span data-ttu-id="57fba-120">Un host è in grado di controllare l'accesso al codice a token di thread sia dal Common Language Runtime (CLR) sia dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="57fba-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="57fba-121">Può inoltre garantire che le informazioni complete sul contesto di sicurezza vengano passate tra le operazioni asincrone o i punti di codice con accesso limitato al codice.</span><span class="sxs-lookup"><span data-stu-id="57fba-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="57fba-122">`IHostSecurityContext`incapsula queste informazioni sul contesto di sicurezza, che è opaco per CLR.</span><span class="sxs-lookup"><span data-stu-id="57fba-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="57fba-123">CLR gestisce internamente il contesto del thread gestito.</span><span class="sxs-lookup"><span data-stu-id="57fba-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="57fba-124">Viene eseguita una query sul processo specifico `IHostSecurityManager` nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="57fba-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="57fba-125">Nel thread del finalizzatore, durante l'esecuzione del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="57fba-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="57fba-126">Durante l'esecuzione del costruttore della classe e del modulo.</span><span class="sxs-lookup"><span data-stu-id="57fba-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="57fba-127">In corrispondenza di punti asincroni nel thread di lavoro, in chiamate al metodo [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) .</span><span class="sxs-lookup"><span data-stu-id="57fba-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="57fba-128">In manutenzione delle porte di completamento I/O.</span><span class="sxs-lookup"><span data-stu-id="57fba-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57fba-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57fba-129">Requirements</span></span>  
 <span data-ttu-id="57fba-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57fba-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57fba-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="57fba-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57fba-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="57fba-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57fba-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57fba-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57fba-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57fba-134">See also</span></span>

- [<span data-ttu-id="57fba-135">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="57fba-135">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="57fba-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="57fba-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
