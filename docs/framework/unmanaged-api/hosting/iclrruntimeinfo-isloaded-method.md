---
title: Metodo ICLRRuntimeInfo::IsLoaded
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7615f5dad1666685333011503c5bef4c98a6a8bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149877"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="ef2bb-102">Metodo ICLRRuntimeInfo::IsLoaded</span><span class="sxs-lookup"><span data-stu-id="ef2bb-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="ef2bb-103">Indica se common language runtime (CLR) è associato il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia viene caricata in un processo.</span><span class="sxs-lookup"><span data-stu-id="ef2bb-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="ef2bb-104">Un runtime può essere caricato senza essere avviato.</span><span class="sxs-lookup"><span data-stu-id="ef2bb-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef2bb-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef2bb-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef2bb-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef2bb-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="ef2bb-107">[in] Handle per il processo.</span><span class="sxs-lookup"><span data-stu-id="ef2bb-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="ef2bb-108">[out] `true` se CLR viene caricato nel processo; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ef2bb-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef2bb-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ef2bb-109">Return Value</span></span>  
 <span data-ttu-id="ef2bb-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="ef2bb-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ef2bb-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef2bb-111">HRESULT</span></span>|<span data-ttu-id="ef2bb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef2bb-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef2bb-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef2bb-113">S_OK</span></span>|<span data-ttu-id="ef2bb-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ef2bb-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="ef2bb-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ef2bb-115">E_POINTER</span></span>|`pbLoaded` <span data-ttu-id="ef2bb-116">è null.</span><span class="sxs-lookup"><span data-stu-id="ef2bb-116">is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef2bb-117">Note</span><span class="sxs-lookup"><span data-stu-id="ef2bb-117">Remarks</span></span>  
 <span data-ttu-id="ef2bb-118">Questo metodo è compatibile con le funzioni e le interfacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef2bb-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
-   <span data-ttu-id="ef2bb-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interfaccia (l'API di hosting .NET Framework versione 1).</span><span class="sxs-lookup"><span data-stu-id="ef2bb-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
-   <span data-ttu-id="ef2bb-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia (nell'API di hosting .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="ef2bb-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
-   <span data-ttu-id="ef2bb-121">Deprecated `CorBindTo*` funzioni (vedere [funzioni di Hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) nell'API di hosting di .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="ef2bb-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="ef2bb-122">Un host può chiamare uno dei deprecate `CorBindTo*` funzioni, ad esempio il [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) funzione per creare un'istanza di una versione specifica di CLR.</span><span class="sxs-lookup"><span data-stu-id="ef2bb-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="ef2bb-123">L'host è possibile quindi chiamare il [ICLRMetaHost:: GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) metodo e specificare lo stesso numero di versione per ottenere un [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ef2bb-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="ef2bb-124">Se l'host chiama quindi il `IsLoaded` metodo sull'oggetto restituito [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia `pbLoaded` restituisce `true`; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="ef2bb-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef2bb-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef2bb-125">Requirements</span></span>  
 <span data-ttu-id="ef2bb-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef2bb-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef2bb-127">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ef2bb-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ef2bb-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ef2bb-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ef2bb-129">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ef2bb-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ef2bb-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef2bb-130">See also</span></span>

- [<span data-ttu-id="ef2bb-131">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="ef2bb-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ef2bb-132">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ef2bb-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ef2bb-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="ef2bb-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
