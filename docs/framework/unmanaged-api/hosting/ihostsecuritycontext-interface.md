---
title: Interfaccia IHostSecurityContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext
helpviewer_keywords: IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1d3c616ced761b696f50e9207e6fad312f06c31c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="c2aa2-102">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="c2aa2-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="c2aa2-103">Consente a common language runtime (CLR) per gestire le informazioni di contesto di sicurezza implementate dall'host.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2aa2-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c2aa2-104">Methods</span></span>  
  
|<span data-ttu-id="c2aa2-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c2aa2-105">Method</span></span>|<span data-ttu-id="c2aa2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2aa2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2aa2-107">Capture (metodo)</span><span class="sxs-lookup"><span data-stu-id="c2aa2-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="c2aa2-108">Ottiene un clone di `IHostSecurityContext` istanza restituita da una chiamata a [IHostSecurityManager::](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="c2aa2-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2aa2-109">Note</span><span class="sxs-lookup"><span data-stu-id="c2aa2-109">Remarks</span></span>  
 <span data-ttu-id="c2aa2-110">Un host può controllare l'accesso di codice ai token di thread da codice CLR e utente.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="c2aa2-111">Può inoltre garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con accesso di codice con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="c2aa2-112">`IHostSecurityContext`incapsula queste informazioni di contesto di sicurezza, che risulta opache al runtime.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="c2aa2-113">Il runtime acquisisce queste informazioni tramite `Capture`, e lo sposta in invio elemento di lavoro del pool di thread, esecuzione dei finalizzatori e i costruttori di modulo e la classe.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2aa2-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2aa2-114">Requirements</span></span>  
 <span data-ttu-id="c2aa2-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2aa2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2aa2-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="c2aa2-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2aa2-117">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2aa2-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2aa2-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2aa2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2aa2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2aa2-119">See Also</span></span>  
 [<span data-ttu-id="c2aa2-120">ICLRHostProtectionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c2aa2-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="c2aa2-121">IHostSecurityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c2aa2-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="c2aa2-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="c2aa2-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
