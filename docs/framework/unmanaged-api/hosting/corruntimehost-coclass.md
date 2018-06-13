---
title: Coclasse CorRuntimeHost
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9b9b8a728932caa085bba1665dc97faf02be8fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431380"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="4c0d6-102">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4c0d6-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="4c0d6-103">Fornisce interfacce per la gestione delle applicazioni che vengono eseguite da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="4c0d6-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c0d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c0d6-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="4c0d6-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="4c0d6-105">Interfaces</span></span>  
  
|<span data-ttu-id="4c0d6-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="4c0d6-106">Interface</span></span>|<span data-ttu-id="4c0d6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c0d6-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="4c0d6-108">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c0d6-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="4c0d6-109">Fornisce metodi per la configurazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4c0d6-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="4c0d6-110">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4c0d6-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="4c0d6-111">Fornisce metodi che consentono all'host avviare e arrestare in modo esplicito, common language runtime per creare e configurare i domini applicazione, per accedere al dominio predefinito e per enumerare tutti i domini in esecuzione nel processo.</span><span class="sxs-lookup"><span data-stu-id="4c0d6-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="4c0d6-112">Interfaccia IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="4c0d6-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="4c0d6-113">Fornisce metodi per ottenere informazioni sullo stato dei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="4c0d6-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="4c0d6-114">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="4c0d6-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="4c0d6-115">Fornisce metodi per ottenere informazioni sul sistema di garbage collection e per controllare alcuni aspetti dell'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="4c0d6-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="4c0d6-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="4c0d6-116">"IValidator"</span></span>|<span data-ttu-id="4c0d6-117">Fornisce metodi per la convalida delle immagini di tipo PE e la creazione di report dettagliati di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="4c0d6-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4c0d6-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c0d6-118">Requirements</span></span>  
 <span data-ttu-id="4c0d6-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c0d6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c0d6-120">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="4c0d6-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="4c0d6-121">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4c0d6-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c0d6-122">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c0d6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c0d6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c0d6-123">See Also</span></span>  
 [<span data-ttu-id="4c0d6-124">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="4c0d6-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
