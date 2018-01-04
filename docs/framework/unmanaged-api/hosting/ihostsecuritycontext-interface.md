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
ms.workload: dotnet
ms.openlocfilehash: 8ee464e47ad6e333b507c199e1857309f640a37b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="6d10f-102">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="6d10f-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="6d10f-103">Consente a common language runtime (CLR) per gestire le informazioni di contesto di sicurezza implementate dall'host.</span><span class="sxs-lookup"><span data-stu-id="6d10f-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d10f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6d10f-104">Methods</span></span>  
  
|<span data-ttu-id="6d10f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6d10f-105">Method</span></span>|<span data-ttu-id="6d10f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d10f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d10f-107">Metodo Capture</span><span class="sxs-lookup"><span data-stu-id="6d10f-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="6d10f-108">Ottiene un clone di `IHostSecurityContext` istanza restituita da una chiamata a [IHostSecurityManager::](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="6d10f-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d10f-109">Note</span><span class="sxs-lookup"><span data-stu-id="6d10f-109">Remarks</span></span>  
 <span data-ttu-id="6d10f-110">Un host può controllare l'accesso di codice ai token di thread da codice CLR e utente.</span><span class="sxs-lookup"><span data-stu-id="6d10f-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="6d10f-111">Può inoltre garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con accesso di codice con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="6d10f-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="6d10f-112">`IHostSecurityContext`incapsula queste informazioni di contesto di sicurezza, che risulta opache al runtime.</span><span class="sxs-lookup"><span data-stu-id="6d10f-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="6d10f-113">Il runtime acquisisce queste informazioni tramite `Capture`, e lo sposta in invio elemento di lavoro del pool di thread, esecuzione dei finalizzatori e i costruttori di modulo e la classe.</span><span class="sxs-lookup"><span data-stu-id="6d10f-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d10f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d10f-114">Requirements</span></span>  
 <span data-ttu-id="6d10f-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d10f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d10f-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6d10f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d10f-117">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d10f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d10f-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d10f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d10f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d10f-119">See Also</span></span>  
 [<span data-ttu-id="6d10f-120">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="6d10f-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="6d10f-121">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="6d10f-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="6d10f-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="6d10f-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
