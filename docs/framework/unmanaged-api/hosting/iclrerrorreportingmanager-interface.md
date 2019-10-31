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
ms.openlocfilehash: 49a60b6b9b076138d8ff1f8a15041e9a6bacfede
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129251"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="ca4fa-102">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="ca4fa-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="ca4fa-103">Fornisce metodi che consentono all'host di configurare dump di stack personalizzati per la segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="ca4fa-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca4fa-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ca4fa-104">Methods</span></span>  
  
|<span data-ttu-id="ca4fa-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ca4fa-105">Method</span></span>|<span data-ttu-id="ca4fa-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca4fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca4fa-107">Metodo BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="ca4fa-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="ca4fa-108">Specifica la configurazione dei dump dello stack personalizzati per la segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="ca4fa-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="ca4fa-109">Metodo EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="ca4fa-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="ca4fa-110">Cancella la configurazione del dump dello stack personalizzato impostata da una chiamata precedente a `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="ca4fa-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="ca4fa-111">Metodo GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="ca4fa-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="ca4fa-112">Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="ca4fa-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca4fa-113">Note</span><span class="sxs-lookup"><span data-stu-id="ca4fa-113">Remarks</span></span>  
 <span data-ttu-id="ca4fa-114">Il metodo `BeginCustomDump` imposta la configurazione del dump dello stack personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ca4fa-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="ca4fa-115">Il metodo `EndCustomDump` Cancella la configurazione del dump dello stack personalizzato e libera qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="ca4fa-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="ca4fa-116">Deve essere chiamato dopo il completamento del dump personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ca4fa-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ca4fa-117">La mancata chiamata di `EndCustomDump` causa la perdita della memoria.</span><span class="sxs-lookup"><span data-stu-id="ca4fa-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca4fa-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca4fa-118">Requirements</span></span>  
 <span data-ttu-id="ca4fa-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca4fa-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca4fa-120">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ca4fa-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca4fa-121">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ca4fa-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca4fa-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca4fa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca4fa-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca4fa-123">See also</span></span>

- [<span data-ttu-id="ca4fa-124">Enumerazione ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="ca4fa-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="ca4fa-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ca4fa-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
