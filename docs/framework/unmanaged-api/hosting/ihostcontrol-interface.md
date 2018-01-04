---
title: Interfaccia IHostControl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl
helpviewer_keywords: IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d0eaecef4cc34549c7d37953a5c8144bdd983692
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="cb4d6-102">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="cb4d6-102">IHostControl Interface</span></span>
<span data-ttu-id="cb4d6-103">Fornisce metodi per la configurazione del caricamento degli assembly e per determinare quali hosting interfacce host supporta.</span><span class="sxs-lookup"><span data-stu-id="cb4d6-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb4d6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cb4d6-104">Methods</span></span>  
  
|<span data-ttu-id="cb4d6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cb4d6-105">Method</span></span>|<span data-ttu-id="cb4d6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb4d6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb4d6-107">Metodo GetHostManager</span><span class="sxs-lookup"><span data-stu-id="cb4d6-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="cb4d6-108">Ottiene un puntatore a interfaccia per l'implementazione dell'host dell'interfaccia con l'oggetto specificato `IID`.</span><span class="sxs-lookup"><span data-stu-id="cb4d6-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="cb4d6-109">Metodo SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="cb4d6-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="cb4d6-110">Notifica all'host che è stato creato un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb4d6-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb4d6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb4d6-111">Requirements</span></span>  
 <span data-ttu-id="cb4d6-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb4d6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb4d6-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="cb4d6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb4d6-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb4d6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb4d6-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb4d6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb4d6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb4d6-116">See Also</span></span>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="cb4d6-117">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="cb4d6-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="cb4d6-118">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="cb4d6-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="cb4d6-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="cb4d6-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
