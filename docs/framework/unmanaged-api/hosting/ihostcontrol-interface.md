---
title: Interfaccia IHostControl
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 014e5c9951091046ae07374794743e82affcd5ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967732"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="d3ae9-102">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="d3ae9-102">IHostControl Interface</span></span>
<span data-ttu-id="d3ae9-103">Fornisce metodi per la configurazione del caricamento degli assembly e per determinare quali hosting interfacce l'host supporta.</span><span class="sxs-lookup"><span data-stu-id="d3ae9-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3ae9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d3ae9-104">Methods</span></span>  
  
|<span data-ttu-id="d3ae9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d3ae9-105">Method</span></span>|<span data-ttu-id="d3ae9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3ae9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3ae9-107">Metodo GetHostManager</span><span class="sxs-lookup"><span data-stu-id="d3ae9-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="d3ae9-108">Ottiene un puntatore a interfaccia per l'implementazione dell'host dell'interfaccia con l'oggetto specificato `IID`.</span><span class="sxs-lookup"><span data-stu-id="d3ae9-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="d3ae9-109">Metodo SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="d3ae9-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="d3ae9-110">Notifica all'host che è stato creato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3ae9-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3ae9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3ae9-111">Requirements</span></span>  
 <span data-ttu-id="d3ae9-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3ae9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3ae9-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3ae9-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3ae9-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d3ae9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3ae9-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ae9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ae9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3ae9-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="d3ae9-117">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d3ae9-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="d3ae9-118">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="d3ae9-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d3ae9-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d3ae9-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
