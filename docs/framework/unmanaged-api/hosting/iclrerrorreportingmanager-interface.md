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
ms.openlocfilehash: dbe4129cf4160a1a9b31bc6f418095ea4b392d57
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616996"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="f028f-102">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="f028f-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="f028f-103">Fornisce metodi che consentono all'host di configurare dump di stack personalizzati per la segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="f028f-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f028f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f028f-104">Methods</span></span>  
  
|<span data-ttu-id="f028f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f028f-105">Method</span></span>|<span data-ttu-id="f028f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f028f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f028f-107">Metodo BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="f028f-107">BeginCustomDump Method</span></span>](iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="f028f-108">Specifica la configurazione dei dump dello stack personalizzati per la segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="f028f-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="f028f-109">Metodo EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="f028f-109">EndCustomDump Method</span></span>](iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="f028f-110">Cancella la configurazione del dump dello stack personalizzato impostata da una chiamata precedente a `BeginCustomDump` .</span><span class="sxs-lookup"><span data-stu-id="f028f-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="f028f-111">Metodo GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="f028f-111">GetBucketParametersForCurrentException Method</span></span>](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="f028f-112">Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="f028f-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f028f-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f028f-113">Remarks</span></span>  
 <span data-ttu-id="f028f-114">Il `BeginCustomDump` metodo imposta la configurazione del dump dello stack personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f028f-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="f028f-115">Il `EndCustomDump` metodo cancella la configurazione del dump dello stack personalizzato e libera qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="f028f-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="f028f-116">Deve essere chiamato dopo il completamento del dump personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f028f-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f028f-117">La mancata chiamata `EndCustomDump` causa la perdita della memoria.</span><span class="sxs-lookup"><span data-stu-id="f028f-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f028f-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f028f-118">Requirements</span></span>  
 <span data-ttu-id="f028f-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f028f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f028f-120">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f028f-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f028f-121">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f028f-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f028f-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f028f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f028f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f028f-123">See also</span></span>

- [<span data-ttu-id="f028f-124">Enumerazione ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="f028f-124">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="f028f-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="f028f-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
