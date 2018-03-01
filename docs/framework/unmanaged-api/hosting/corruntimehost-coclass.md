---
title: Coclasse CorRuntimeHost
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
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 23bee1a79dfb54a696495fdb61a7ba9ba4b4c143
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="7d770-102">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="7d770-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="7d770-103">Fornisce interfacce per la gestione delle applicazioni che vengono eseguite da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="7d770-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d770-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d770-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="7d770-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="7d770-105">Interfaces</span></span>  
  
|<span data-ttu-id="7d770-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="7d770-106">Interface</span></span>|<span data-ttu-id="7d770-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d770-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="7d770-108">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="7d770-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="7d770-109">Fornisce metodi per la configurazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7d770-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="7d770-110">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="7d770-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="7d770-111">Fornisce metodi che consentono all'host avviare e arrestare in modo esplicito, common language runtime per creare e configurare i domini applicazione, per accedere al dominio predefinito e per enumerare tutti i domini in esecuzione nel processo.</span><span class="sxs-lookup"><span data-stu-id="7d770-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="7d770-112">Interfaccia IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="7d770-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="7d770-113">Fornisce metodi per ottenere informazioni sullo stato dei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="7d770-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="7d770-114">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="7d770-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="7d770-115">Fornisce metodi per ottenere informazioni sul sistema di garbage collection e per controllare alcuni aspetti dell'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7d770-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="7d770-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="7d770-116">"IValidator"</span></span>|<span data-ttu-id="7d770-117">Fornisce metodi per la convalida delle immagini di tipo PE e la creazione di report dettagliati di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="7d770-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d770-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d770-118">Requirements</span></span>  
 <span data-ttu-id="7d770-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d770-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d770-120">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="7d770-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="7d770-121">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d770-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d770-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d770-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d770-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d770-123">See Also</span></span>  
 [<span data-ttu-id="7d770-124">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="7d770-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
