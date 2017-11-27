---
title: Coclasse CorRuntimeHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRuntimeHost
helpviewer_keywords: CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3d7a272aff3a3c7d32042b76d37fdb15c9dcad4d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="ffec4-102">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ffec4-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="ffec4-103">Fornisce interfacce per la gestione delle applicazioni che vengono eseguite da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="ffec4-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffec4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ffec4-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="ffec4-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="ffec4-105">Interfaces</span></span>  
  
|<span data-ttu-id="ffec4-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="ffec4-106">Interface</span></span>|<span data-ttu-id="ffec4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffec4-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ffec4-108">ICorConfiguration (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ffec4-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="ffec4-109">Fornisce metodi per la configurazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ffec4-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="ffec4-110">ICorRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ffec4-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="ffec4-111">Fornisce metodi che consentono all'host avviare e arrestare in modo esplicito, common language runtime per creare e configurare i domini applicazione, per accedere al dominio predefinito e per enumerare tutti i domini in esecuzione nel processo.</span><span class="sxs-lookup"><span data-stu-id="ffec4-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="ffec4-112">IDebuggerInfo (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ffec4-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="ffec4-113">Fornisce metodi per ottenere informazioni sullo stato dei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="ffec4-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="ffec4-114">IGCHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ffec4-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="ffec4-115">Fornisce metodi per ottenere informazioni sul sistema di garbage collection e per controllare alcuni aspetti dell'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ffec4-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="ffec4-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="ffec4-116">"IValidator"</span></span>|<span data-ttu-id="ffec4-117">Fornisce metodi per la convalida delle immagini di tipo PE e la creazione di report dettagliati di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="ffec4-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffec4-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ffec4-118">Requirements</span></span>  
 <span data-ttu-id="ffec4-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffec4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffec4-120">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="ffec4-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ffec4-121">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ffec4-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffec4-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffec4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffec4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffec4-123">See Also</span></span>  
 [<span data-ttu-id="ffec4-124">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="ffec4-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
