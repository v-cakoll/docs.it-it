---
title: Interfaccia ICLRErrorReportingManager
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
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1ac362432a5d0c613f4ee1409ee15d92bfef3aeb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="dea16-102">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="dea16-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="dea16-103">Fornisce metodi che consentono all'host configurare il dump dello stack personalizzati per la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="dea16-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dea16-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="dea16-104">Methods</span></span>  
  
|<span data-ttu-id="dea16-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="dea16-105">Method</span></span>|<span data-ttu-id="dea16-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dea16-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dea16-107">Metodo BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="dea16-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="dea16-108">Specifica la configurazione dei dump dello stack personalizzati per la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="dea16-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="dea16-109">Metodo EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="dea16-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="dea16-110">Cancella la configurazione di dump dello stack personalizzati che è stata impostata da una precedente chiamata a `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="dea16-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="dea16-111">Metodo GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="dea16-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="dea16-112">Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="dea16-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dea16-113">Note</span><span class="sxs-lookup"><span data-stu-id="dea16-113">Remarks</span></span>  
 <span data-ttu-id="dea16-114">Il `BeginCustomDump` metodo imposta la configurazione di dump dello stack personalizzati.</span><span class="sxs-lookup"><span data-stu-id="dea16-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="dea16-115">Il `EndCustomDump` metodo cancella la configurazione di dump dello stack personalizzati e rilascia qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="dea16-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="dea16-116">Deve essere chiamato dopo il dump personalizzato è stato completato.</span><span class="sxs-lookup"><span data-stu-id="dea16-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dea16-117">Errore durante la chiamata `EndCustomDump` provoca perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="dea16-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dea16-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dea16-118">Requirements</span></span>  
 <span data-ttu-id="dea16-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dea16-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dea16-120">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="dea16-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dea16-121">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dea16-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dea16-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dea16-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea16-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dea16-123">See Also</span></span>  
 [<span data-ttu-id="dea16-124">Enumerazione ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="dea16-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="dea16-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="dea16-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
