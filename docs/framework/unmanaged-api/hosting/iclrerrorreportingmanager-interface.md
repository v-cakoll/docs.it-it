---
title: Interfaccia ICLRErrorReportingManager
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a9d9cff0360e4eb27584fe0f22c1c20396ff8f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966251"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="2e1a4-102">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="2e1a4-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="2e1a4-103">Fornisce metodi che consentono all'host di configurare dump di stack personalizzati per la segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="2e1a4-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e1a4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2e1a4-104">Methods</span></span>  
  
|<span data-ttu-id="2e1a4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2e1a4-105">Method</span></span>|<span data-ttu-id="2e1a4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e1a4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e1a4-107">Metodo BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="2e1a4-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="2e1a4-108">Specifica la configurazione dei dump dello stack personalizzati per la segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="2e1a4-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="2e1a4-109">Metodo EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="2e1a4-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="2e1a4-110">Cancella la configurazione del dump dello stack personalizzato impostata da una chiamata precedente a `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="2e1a4-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="2e1a4-111">Metodo GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="2e1a4-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="2e1a4-112">Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="2e1a4-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e1a4-113">Note</span><span class="sxs-lookup"><span data-stu-id="2e1a4-113">Remarks</span></span>  
 <span data-ttu-id="2e1a4-114">Il `BeginCustomDump` metodo imposta la configurazione del dump dello stack personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2e1a4-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="2e1a4-115">Il `EndCustomDump` metodo cancella la configurazione del dump dello stack personalizzato e libera qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="2e1a4-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="2e1a4-116">Deve essere chiamato dopo il completamento del dump personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2e1a4-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2e1a4-117">La mancata `EndCustomDump` chiamata causa la perdita della memoria.</span><span class="sxs-lookup"><span data-stu-id="2e1a4-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e1a4-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e1a4-118">Requirements</span></span>  
 <span data-ttu-id="2e1a4-119">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e1a4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e1a4-120">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2e1a4-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e1a4-121">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2e1a4-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e1a4-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e1a4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e1a4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e1a4-123">See also</span></span>

- [<span data-ttu-id="2e1a4-124">Enumerazione ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="2e1a4-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="2e1a4-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="2e1a4-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
