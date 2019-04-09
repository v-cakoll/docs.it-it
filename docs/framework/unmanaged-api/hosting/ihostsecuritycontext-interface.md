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
ms.openlocfilehash: 9d71b7e1265110a70329377ce8ab7430e1943c49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124029"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="f8cfd-102">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="f8cfd-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="f8cfd-103">Consente a common language runtime (CLR) per gestire le informazioni di contesto di sicurezza implementate dall'host.</span><span class="sxs-lookup"><span data-stu-id="f8cfd-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8cfd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f8cfd-104">Methods</span></span>  
  
|<span data-ttu-id="f8cfd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f8cfd-105">Method</span></span>|<span data-ttu-id="f8cfd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8cfd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8cfd-107">Metodo Capture</span><span class="sxs-lookup"><span data-stu-id="f8cfd-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="f8cfd-108">Ottiene un clone del `IHostSecurityContext` istanza restituita da una chiamata a [IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="f8cfd-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8cfd-109">Note</span><span class="sxs-lookup"><span data-stu-id="f8cfd-109">Remarks</span></span>  
 <span data-ttu-id="f8cfd-110">Un host può controllare tutti gli accessi di codice ai token di thread da codice CLR e utente.</span><span class="sxs-lookup"><span data-stu-id="f8cfd-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="f8cfd-111">Inoltre possibile garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con l'accesso al codice con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="f8cfd-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> `IHostSecurityContext` <span data-ttu-id="f8cfd-112">incapsula questo informazioni sul contesto di sicurezza, che risulta opachi al runtime.</span><span class="sxs-lookup"><span data-stu-id="f8cfd-112">encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="f8cfd-113">Il runtime consente di acquisire queste informazioni usando `Capture`, e lo sposta in invio elemento di lavoro del pool di thread, l'esecuzione del finalizzatore e costruttori di classe e modulo.</span><span class="sxs-lookup"><span data-stu-id="f8cfd-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8cfd-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8cfd-114">Requirements</span></span>  
 <span data-ttu-id="f8cfd-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8cfd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8cfd-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f8cfd-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8cfd-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f8cfd-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f8cfd-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f8cfd-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8cfd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8cfd-119">See also</span></span>

- [<span data-ttu-id="f8cfd-120">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="f8cfd-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="f8cfd-121">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="f8cfd-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="f8cfd-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="f8cfd-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
