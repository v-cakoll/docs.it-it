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
ms.openlocfilehash: 924d032c42dca95b253acea167d55dd6e2b811e5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703331"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="0a99d-102">Metodo ICLRRuntimeHost::ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="0a99d-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="0a99d-103">Utilizzato negli scenari di distribuzione ClickOnce basati su manifesto per specificare l'applicazione da attivare in un nuovo dominio.</span><span class="sxs-lookup"><span data-stu-id="0a99d-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="0a99d-104">Per ulteriori informazioni su questi scenari, vedere [sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="0a99d-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a99d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a99d-105">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a99d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a99d-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="0a99d-107">in Nome completo dell'applicazione, come definito per <xref:System.ApplicationIdentity> .</span><span class="sxs-lookup"><span data-stu-id="0a99d-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="0a99d-108">in Numero di stringhe contenute nella `ppwzManifestPaths` matrice.</span><span class="sxs-lookup"><span data-stu-id="0a99d-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="0a99d-109">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0a99d-109">[in] Optional.</span></span> <span data-ttu-id="0a99d-110">Matrice di stringhe che contiene i percorsi dei manifesti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0a99d-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="0a99d-111">in Numero di stringhe contenute nella `ppwzActivationData` matrice.</span><span class="sxs-lookup"><span data-stu-id="0a99d-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="0a99d-112">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0a99d-112">[in] Optional.</span></span> <span data-ttu-id="0a99d-113">Matrice di stringhe che contiene i dati di attivazione dell'applicazione, ad esempio la parte della stringa di query dell'URL per le applicazioni distribuite sul Web.</span><span class="sxs-lookup"><span data-stu-id="0a99d-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="0a99d-114">out Valore restituito dal punto di ingresso dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0a99d-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a99d-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0a99d-115">Return Value</span></span>  
  
|<span data-ttu-id="0a99d-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a99d-116">HRESULT</span></span>|<span data-ttu-id="0a99d-117">Description</span><span class="sxs-lookup"><span data-stu-id="0a99d-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a99d-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a99d-118">S_OK</span></span>|<span data-ttu-id="0a99d-119">`ExecuteApplication`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0a99d-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="0a99d-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a99d-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a99d-121">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0a99d-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0a99d-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0a99d-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0a99d-123">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0a99d-123">The call timed out.</span></span>|  
|<span data-ttu-id="0a99d-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0a99d-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0a99d-125">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="0a99d-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0a99d-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0a99d-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0a99d-127">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0a99d-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0a99d-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a99d-128">E_FAIL</span></span>|<span data-ttu-id="0a99d-129">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0a99d-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0a99d-130">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0a99d-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0a99d-131">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0a99d-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a99d-132">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0a99d-132">Remarks</span></span>  
 <span data-ttu-id="0a99d-133">`ExecuteApplication`viene usato per attivare le applicazioni ClickOnce in un dominio applicazione appena creato.</span><span class="sxs-lookup"><span data-stu-id="0a99d-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="0a99d-134">Il `pReturnValue` parametro di output viene impostato sul valore restituito dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0a99d-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="0a99d-135">Se si fornisce un valore null per, non ha `pReturnValue` `ExecuteApplication` esito negativo, ma non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="0a99d-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0a99d-136">Non chiamare il metodo [Start](iclrruntimehost-start-method.md) del metodo prima di chiamare il `ExecuteApplication` metodo per attivare un'applicazione basata su manifesto.</span><span class="sxs-lookup"><span data-stu-id="0a99d-136">Do not call the [Start Method](iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="0a99d-137">Se il `Start` metodo viene chiamato per primo, la `ExecuteApplication` chiamata al metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0a99d-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a99d-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a99d-138">Requirements</span></span>  
 <span data-ttu-id="0a99d-139">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a99d-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a99d-140">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0a99d-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a99d-141">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0a99d-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a99d-142">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a99d-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a99d-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a99d-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="0a99d-144">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0a99d-144">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="0a99d-145">Metodo SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="0a99d-145">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="0a99d-146">Procedura dettagliata: download di assembly su richiesta con l'API della distribuzione ClickOnce tramite la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="0a99d-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
