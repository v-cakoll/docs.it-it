---
title: Metodo ICLRDomainManager::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c2927195b650f1098292f3d59cd887e084aea21
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490060"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="ad6d8-102">Metodo ICLRDomainManager::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="ad6d8-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="ad6d8-103">Specifica il tipo, derivato dal <xref:System.AppDomainManager?displayProperty=nameWithType> (classe), l'applicazione del gestore del dominio che verrà usato per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="ad6d8-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad6d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad6d8-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad6d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad6d8-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="ad6d8-106">[in] Il nome visualizzato dell'assembly che contiene il tipo di gestione del dominio applicazione; Per esempio: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="ad6d8-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="ad6d8-107">[in] Il nome del tipo del gestore di dominio dell'applicazione, incluso lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ad6d8-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="ad6d8-108">[in] Una combinazione di [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) valori di enumerazione che forniscono informazioni sulla gestione dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad6d8-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad6d8-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ad6d8-109">Return Value</span></span>  
 <span data-ttu-id="ad6d8-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="ad6d8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ad6d8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad6d8-111">HRESULT</span></span>|<span data-ttu-id="ad6d8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad6d8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad6d8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad6d8-113">S_OK</span></span>|<span data-ttu-id="ad6d8-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ad6d8-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="ad6d8-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ad6d8-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ad6d8-116">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad6d8-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad6d8-117">Note</span><span class="sxs-lookup"><span data-stu-id="ad6d8-117">Remarks</span></span>  
 <span data-ttu-id="ad6d8-118">Attualmente, l'unico valore definito per `dwInitializeDomainFlags` viene `eInitializeNewDomainFlags_NoSecurityChanges`, indicherà che il gestore del dominio applicazione non modifica le impostazioni di sicurezza durante l'esecuzione di common language runtime (CLR) di <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="ad6d8-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ad6d8-119">In questo modo Common Language Runtime ottimizzare il caricamento degli assembly con il parametro condizionale <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attributo (APTCA).</span><span class="sxs-lookup"><span data-stu-id="ad6d8-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="ad6d8-120">Se la chiusura transitiva di questo set di assembly è grande, ciò può comportare un miglioramento significativo nel tempo di avvio.</span><span class="sxs-lookup"><span data-stu-id="ad6d8-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ad6d8-121">Se l'host specifica `eInitializeNewDomainFlags_NoSecurityChanges` per il gestore del dominio dell'applicazione, un <xref:System.InvalidOperationException> viene generata un'eccezione se viene eseguito un tentativo di modificare la sicurezza del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad6d8-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="ad6d8-122">Chiama il [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)metodo è equivalente alla chiamata `ICLRDomainManager::SetAppDomainManagerType` con `eInitializeNewDomainFlags_None`.</span><span class="sxs-lookup"><span data-stu-id="ad6d8-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad6d8-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad6d8-123">Requirements</span></span>  
 <span data-ttu-id="ad6d8-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad6d8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad6d8-125">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ad6d8-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ad6d8-126">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ad6d8-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad6d8-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad6d8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad6d8-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad6d8-128">See also</span></span>
- [<span data-ttu-id="ad6d8-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="ad6d8-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="ad6d8-130">Interfaccia ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="ad6d8-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [<span data-ttu-id="ad6d8-131">Enumerazione EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="ad6d8-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
