---
title: Metodo ICLRRuntimeHost::ExecuteApplication
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56a49b3d08b58da109924267e6c23c188efefe29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436072"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="e4779-102">Metodo ICLRRuntimeHost::ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="e4779-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="e4779-103">Utilizzato in scenari di distribuzione basato su manifesto ClickOnce per specificare l'attivazione in un nuovo dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4779-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="e4779-104">Per ulteriori informazioni su questi scenari, vedere [protezione di applicazioni ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="e4779-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4779-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4779-105">Syntax</span></span>  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4779-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e4779-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="e4779-107">[in] Il nome completo dell'applicazione, come definito per <xref:System.ApplicationIdentity>.</span><span class="sxs-lookup"><span data-stu-id="e4779-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="e4779-108">[in] Il numero di stringhe contenute nel `ppwzManifestPaths` matrice.</span><span class="sxs-lookup"><span data-stu-id="e4779-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="e4779-109">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e4779-109">[in] Optional.</span></span> <span data-ttu-id="e4779-110">Matrice di stringhe che contiene i percorsi di manifesto per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4779-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="e4779-111">[in] Il numero di stringhe contenute nel `ppwzActivationData` matrice.</span><span class="sxs-lookup"><span data-stu-id="e4779-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="e4779-112">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e4779-112">[in] Optional.</span></span> <span data-ttu-id="e4779-113">Matrice di stringhe contenente i dati di attivazione dell'applicazione, ad esempio parte della stringa di query dell'URL per le applicazioni distribuite sul Web.</span><span class="sxs-lookup"><span data-stu-id="e4779-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="e4779-114">[out] Il valore restituito dal punto di ingresso dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4779-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4779-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e4779-115">Return Value</span></span>  
  
|<span data-ttu-id="e4779-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e4779-116">HRESULT</span></span>|<span data-ttu-id="e4779-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4779-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4779-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="e4779-118">S_OK</span></span>|<span data-ttu-id="e4779-119">`ExecuteApplication` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e4779-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="e4779-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e4779-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e4779-121">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e4779-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e4779-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e4779-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e4779-123">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e4779-123">The call timed out.</span></span>|  
|<span data-ttu-id="e4779-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4779-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e4779-125">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="e4779-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e4779-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e4779-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e4779-127">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e4779-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e4779-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e4779-128">E_FAIL</span></span>|<span data-ttu-id="e4779-129">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e4779-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e4779-130">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e4779-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e4779-131">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e4779-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4779-132">Note</span><span class="sxs-lookup"><span data-stu-id="e4779-132">Remarks</span></span>  
 <span data-ttu-id="e4779-133">`ExecuteApplication` Consente di attivare applicazioni ClickOnce in un dominio applicazione appena creato.</span><span class="sxs-lookup"><span data-stu-id="e4779-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="e4779-134">Il `pReturnValue` parametro di output è impostato sul valore restituito dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4779-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="e4779-135">Se si specifica un valore null per `pReturnValue`, `ExecuteApplication` ha esito positivo, ma non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="e4779-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e4779-136">Non chiamare il [metodo Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo prima di chiamare il `ExecuteApplication` metodo per attivare un'applicazione basata su manifesto.</span><span class="sxs-lookup"><span data-stu-id="e4779-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="e4779-137">Se il `Start` metodo viene chiamato per primo, il `ExecuteApplication` chiamata al metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e4779-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4779-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4779-138">Requirements</span></span>  
 <span data-ttu-id="e4779-139">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4779-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4779-140">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e4779-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4779-141">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e4779-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4779-142">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4779-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4779-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4779-143">See Also</span></span>  
 <xref:System.ActivationContext>  
 <xref:System.AppDomainManager>  
 <xref:System.ApplicationIdentity>  
 [<span data-ttu-id="e4779-144">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e4779-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="e4779-145">Metodo SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="e4779-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)  
 [<span data-ttu-id="e4779-146">Procedura dettagliata: download di assembly su richiesta con l'API della distribuzione ClickOnce tramite la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="e4779-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
