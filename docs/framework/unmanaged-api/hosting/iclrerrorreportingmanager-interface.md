---
title: Interfaccia ICLRErrorReportingManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager
helpviewer_keywords: ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 590cd87d6a566e9c8c3819fd1b250997938e9c35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="dbd8b-102">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="dbd8b-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="dbd8b-103">Fornisce metodi che consentono all'host configurare il dump dello stack personalizzati per la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="dbd8b-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dbd8b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="dbd8b-104">Methods</span></span>  
  
|<span data-ttu-id="dbd8b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="dbd8b-105">Method</span></span>|<span data-ttu-id="dbd8b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbd8b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dbd8b-107">BeginCustomDump (metodo)</span><span class="sxs-lookup"><span data-stu-id="dbd8b-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="dbd8b-108">Specifica la configurazione dei dump dello stack personalizzati per la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="dbd8b-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="dbd8b-109">EndCustomDump (metodo)</span><span class="sxs-lookup"><span data-stu-id="dbd8b-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="dbd8b-110">Cancella la configurazione di dump dello stack personalizzati che è stata impostata da una precedente chiamata a `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="dbd8b-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="dbd8b-111">GetBucketParametersForCurrentException (metodo)</span><span class="sxs-lookup"><span data-stu-id="dbd8b-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="dbd8b-112">Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="dbd8b-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbd8b-113">Note</span><span class="sxs-lookup"><span data-stu-id="dbd8b-113">Remarks</span></span>  
 <span data-ttu-id="dbd8b-114">Il `BeginCustomDump` metodo imposta la configurazione di dump dello stack personalizzati.</span><span class="sxs-lookup"><span data-stu-id="dbd8b-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="dbd8b-115">Il `EndCustomDump` metodo cancella la configurazione di dump dello stack personalizzati e rilascia qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="dbd8b-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="dbd8b-116">Deve essere chiamato dopo il dump personalizzato è stato completato.</span><span class="sxs-lookup"><span data-stu-id="dbd8b-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dbd8b-117">Errore durante la chiamata `EndCustomDump` provoca perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="dbd8b-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbd8b-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dbd8b-118">Requirements</span></span>  
 <span data-ttu-id="dbd8b-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbd8b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbd8b-120">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="dbd8b-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbd8b-121">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dbd8b-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbd8b-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbd8b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd8b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbd8b-123">See Also</span></span>  
 [<span data-ttu-id="dbd8b-124">ECustomDumpItemKind (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="dbd8b-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="dbd8b-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="dbd8b-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
