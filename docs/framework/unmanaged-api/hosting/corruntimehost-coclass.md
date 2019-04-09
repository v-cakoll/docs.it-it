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
ms.openlocfilehash: 2143fc13db1757ac2fa8a9c5a43f104a0c519ca0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218563"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="d7ebb-102">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d7ebb-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="d7ebb-103">Fornisce interfacce per la gestione delle applicazioni che vengono eseguite da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="d7ebb-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7ebb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7ebb-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="d7ebb-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="d7ebb-105">Interfaces</span></span>  
  
|<span data-ttu-id="d7ebb-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="d7ebb-106">Interface</span></span>|<span data-ttu-id="d7ebb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7ebb-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="d7ebb-108">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d7ebb-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="d7ebb-109">Fornisce metodi per la configurazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d7ebb-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="d7ebb-110">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d7ebb-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="d7ebb-111">Fornisce metodi che consentono all'host avviare e arrestare in modo esplicito, common language runtime per creare e configurare domini dell'applicazione, accedere al dominio predefinito di enumerare tutti i domini in esecuzione nel processo.</span><span class="sxs-lookup"><span data-stu-id="d7ebb-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="d7ebb-112">Interfaccia IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="d7ebb-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="d7ebb-113">Fornisce metodi per ottenere informazioni sullo stato dei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="d7ebb-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="d7ebb-114">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="d7ebb-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="d7ebb-115">Fornisce metodi di recupero di informazioni sul sistema di garbage collection e di controllo di alcuni aspetti del processo di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="d7ebb-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="d7ebb-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="d7ebb-116">"IValidator"</span></span>|<span data-ttu-id="d7ebb-117">Fornisce metodi per la convalida delle immagini eseguibili portabili e report dettagliati degli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="d7ebb-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7ebb-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7ebb-118">Requirements</span></span>  
 <span data-ttu-id="d7ebb-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7ebb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7ebb-120">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="d7ebb-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d7ebb-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d7ebb-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d7ebb-122">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d7ebb-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d7ebb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7ebb-123">See also</span></span>

- [<span data-ttu-id="d7ebb-124">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="d7ebb-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
