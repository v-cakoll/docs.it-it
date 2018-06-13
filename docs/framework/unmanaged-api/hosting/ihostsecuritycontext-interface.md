---
title: Interfaccia IHostSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c2500f013584ef4722ceaaaee91d5db54991639
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439299"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="ad226-102">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="ad226-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="ad226-103">Consente a common language runtime (CLR) per gestire le informazioni di contesto di sicurezza implementate dall'host.</span><span class="sxs-lookup"><span data-stu-id="ad226-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad226-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ad226-104">Methods</span></span>  
  
|<span data-ttu-id="ad226-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ad226-105">Method</span></span>|<span data-ttu-id="ad226-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad226-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad226-107">Metodo Capture</span><span class="sxs-lookup"><span data-stu-id="ad226-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="ad226-108">Ottiene un clone di `IHostSecurityContext` istanza restituita da una chiamata a [IHostSecurityManager::](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="ad226-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad226-109">Note</span><span class="sxs-lookup"><span data-stu-id="ad226-109">Remarks</span></span>  
 <span data-ttu-id="ad226-110">Un host può controllare l'accesso di codice ai token di thread da codice CLR e utente.</span><span class="sxs-lookup"><span data-stu-id="ad226-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="ad226-111">Può inoltre garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con accesso di codice con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="ad226-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="ad226-112">`IHostSecurityContext` incapsula questa informazioni sul contesto di sicurezza, risulta opachi al runtime.</span><span class="sxs-lookup"><span data-stu-id="ad226-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="ad226-113">Il runtime acquisisce queste informazioni tramite `Capture`, e lo sposta in invio elemento di lavoro del pool di thread, esecuzione dei finalizzatori e i costruttori di modulo e la classe.</span><span class="sxs-lookup"><span data-stu-id="ad226-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad226-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad226-114">Requirements</span></span>  
 <span data-ttu-id="ad226-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad226-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad226-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="ad226-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad226-117">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ad226-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad226-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad226-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad226-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad226-119">See Also</span></span>  
 [<span data-ttu-id="ad226-120">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="ad226-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="ad226-121">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="ad226-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="ad226-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ad226-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
