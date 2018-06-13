---
title: Metodo ICorRuntimeHost::CreateDomainEx
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e851cf16e4b23b1f8510c4d96b23c01eb726a77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438054"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="943bc-102">Metodo ICorRuntimeHost::CreateDomainEx</span><span class="sxs-lookup"><span data-stu-id="943bc-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="943bc-103">Crea un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="943bc-103">Creates an application domain.</span></span> <span data-ttu-id="943bc-104">Il chiamante riceve un puntatore a interfaccia di tipo <xref:System._AppDomain>, a un'istanza di tipo <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="943bc-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="943bc-105">Questo metodo consente al chiamante di passare un'istanza di IAppDomainSetup per configurare le funzionalità aggiuntive dell'oggetto restituito <xref:System._AppDomain> istanza.</span><span class="sxs-lookup"><span data-stu-id="943bc-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="943bc-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="943bc-106">Syntax</span></span>  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="943bc-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="943bc-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="943bc-108">[in] Parametro facoltativo utilizzato per assegnare un nome descrittivo per il dominio.</span><span class="sxs-lookup"><span data-stu-id="943bc-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="943bc-109">Questo nome descrittivo può essere visualizzato nelle interfacce utente, ad esempio i debugger per identificare il dominio.</span><span class="sxs-lookup"><span data-stu-id="943bc-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="943bc-110">[in] Un puntatore a interfaccia facoltativo di tipo `IAppDomainSetup`, ottenuto da una chiamata al [ICorRuntimeHost:: CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="943bc-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="943bc-111">[in] Matrice facoltativa di puntatori a `IIdentity` istanze che rappresentano evidenze mappate tramite criteri di sicurezza per stabilire un set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="943bc-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="943bc-112">Un `IIdentity` oggetto può essere ottenuto chiamando il [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="943bc-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="943bc-113">[out] Un puntatore a interfaccia di tipo <xref:System._AppDomain> a un'istanza di <xref:System.AppDomain?displayProperty=nameWithType> che può essere utilizzato per controllare ulteriormente il dominio.</span><span class="sxs-lookup"><span data-stu-id="943bc-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="943bc-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="943bc-114">Return Value</span></span>  
  
|<span data-ttu-id="943bc-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="943bc-115">HRESULT</span></span>|<span data-ttu-id="943bc-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="943bc-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="943bc-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="943bc-117">S_OK</span></span>|<span data-ttu-id="943bc-118">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="943bc-118">The operation was successful.</span></span>|  
|<span data-ttu-id="943bc-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="943bc-119">S_FALSE</span></span>|<span data-ttu-id="943bc-120">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="943bc-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="943bc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="943bc-121">E_FAIL</span></span>|<span data-ttu-id="943bc-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="943bc-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="943bc-123">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="943bc-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="943bc-124">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="943bc-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="943bc-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="943bc-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="943bc-126">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="943bc-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="943bc-127">Note</span><span class="sxs-lookup"><span data-stu-id="943bc-127">Remarks</span></span>  
 <span data-ttu-id="943bc-128">`CreateDomainEx` estende le funzionalità di [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) consentendo al chiamante di passare un `IAppDomainSetup` istanza con i valori delle proprietà per configurare il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="943bc-128">`CreateDomainEx` extends the capabilities of [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="943bc-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="943bc-129">Requirements</span></span>  
 <span data-ttu-id="943bc-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="943bc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="943bc-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="943bc-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="943bc-132">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="943bc-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="943bc-133">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="943bc-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943bc-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="943bc-134">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [<span data-ttu-id="943bc-135">Metodo CreateDomain</span><span class="sxs-lookup"><span data-stu-id="943bc-135">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)  
 [<span data-ttu-id="943bc-136">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="943bc-136">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
