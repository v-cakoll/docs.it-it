---
title: Metodo ICLRMetaHost::GetRuntime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type: apiref
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 849668f10eba81ba1667ac6518ab699e4bca3bcb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="96e95-102">Metodo ICLRMetaHost::GetRuntime</span><span class="sxs-lookup"><span data-stu-id="96e95-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="96e95-103">Ottiene il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia che corrisponde a una particolare versione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="96e95-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="96e95-104">Questo metodo sostituisce il [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funzione utilizzato con il [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span><span class="sxs-lookup"><span data-stu-id="96e95-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96e95-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96e95-105">Syntax</span></span>  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96e95-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="96e95-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="96e95-107">[in] La versione di compilazione di .NET Framework archiviata nei metadati, nel formato "v*A*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="96e95-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="96e95-108">*Oggetto*, *B*, e *X* sono numeri decimali che corrispondono alla versione principale, la versione secondaria e il numero di build.</span><span class="sxs-lookup"><span data-stu-id="96e95-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96e95-109">Questo parametro deve corrispondere al nome di directory per la versione di .NET Framework, così come viene visualizzato in C:\Windows\Microsoft.NET\Framework o C:\Windows\Microsoft.NET\Framework64.</span><span class="sxs-lookup"><span data-stu-id="96e95-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="96e95-110">I valori di esempio sono "v 1.0.3705", "ASP.NET v 1.1.4322", "v 2.0.50727" e "v 4.0. *X*", dove *X* dipende dal numero di build installato.</span><span class="sxs-lookup"><span data-stu-id="96e95-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="96e95-111">Il prefisso "v" è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="96e95-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="96e95-112">[in] L'identificatore per l'interfaccia desiderata.</span><span class="sxs-lookup"><span data-stu-id="96e95-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="96e95-113">Attualmente, l'unico valore valido per questo parametro è IID_ICLRRuntimeInfo.</span><span class="sxs-lookup"><span data-stu-id="96e95-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="96e95-114">[out] Un puntatore al [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia che corrisponde al runtime richiesto.</span><span class="sxs-lookup"><span data-stu-id="96e95-114">[out] A pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96e95-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="96e95-115">Return Value</span></span>  
 <span data-ttu-id="96e95-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="96e95-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="96e95-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96e95-117">HRESULT</span></span>|<span data-ttu-id="96e95-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96e95-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96e95-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="96e95-119">S_OK</span></span>|<span data-ttu-id="96e95-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="96e95-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="96e95-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="96e95-121">E_POINTER</span></span>|<span data-ttu-id="96e95-122">`pwzVersion` o `ppRuntime` è null.</span><span class="sxs-lookup"><span data-stu-id="96e95-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96e95-123">Note</span><span class="sxs-lookup"><span data-stu-id="96e95-123">Remarks</span></span>  
 <span data-ttu-id="96e95-124">Questo metodo interagisce in modo coerente con le interfacce legacy, ad esempio il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interfaccia e le funzioni legacy, ad esempio deprecate `CorBindTo*` funzioni (vedere [deprecato Hosting funzioni CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) nell'API di hosting di .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="96e95-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="96e95-125">Vale a dire i runtime caricati con l'API legacy sono visibili alla nuova API e runtime caricati con la nuova API sono visibili alle API legacy.</span><span class="sxs-lookup"><span data-stu-id="96e95-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span> <span data-ttu-id="96e95-126">.</span><span class="sxs-lookup"><span data-stu-id="96e95-126">.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96e95-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96e95-127">Requirements</span></span>  
 <span data-ttu-id="96e95-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96e95-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96e95-129">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="96e95-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="96e95-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96e95-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96e95-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96e95-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e95-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96e95-132">See Also</span></span>  
 [<span data-ttu-id="96e95-133">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="96e95-133">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="96e95-134">Interfacce di hosting CLR deprecate e coclassi</span><span class="sxs-lookup"><span data-stu-id="96e95-134">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 [<span data-ttu-id="96e95-135">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="96e95-135">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="96e95-136">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="96e95-136">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [<span data-ttu-id="96e95-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="96e95-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
