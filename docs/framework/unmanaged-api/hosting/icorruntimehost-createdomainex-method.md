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
ms.openlocfilehash: 4e5856fbcda83c1dd30559c6f59f63495faea78d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762344"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="72972-102">Metodo ICorRuntimeHost::CreateDomainEx</span><span class="sxs-lookup"><span data-stu-id="72972-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="72972-103">Crea un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="72972-103">Creates an application domain.</span></span> <span data-ttu-id="72972-104">Il chiamante riceve un puntatore di interfaccia, di tipo <xref:System._AppDomain> , in un'istanza di tipo <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="72972-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="72972-105">Questo metodo consente al chiamante di passare un'istanza di IAppDomainSetup per configurare funzionalità aggiuntive dell'istanza restituita <xref:System._AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="72972-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72972-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72972-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72972-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="72972-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="72972-108">in Parametro facoltativo utilizzato per assegnare un nome descrittivo al dominio.</span><span class="sxs-lookup"><span data-stu-id="72972-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="72972-109">Questo nome descrittivo può essere visualizzato nelle interfacce utente, ad esempio i debugger, per identificare il dominio.</span><span class="sxs-lookup"><span data-stu-id="72972-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="72972-110">in Puntatore di interfaccia facoltativo di tipo `IAppDomainSetup` , ottenuto da una chiamata al metodo [ICorRuntimeHost:: CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) .</span><span class="sxs-lookup"><span data-stu-id="72972-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="72972-111">in Matrice facoltativa di puntatori a `IIdentity` istanze che rappresentano l'evidenza mappata tramite i criteri di sicurezza per stabilire un set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="72972-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="72972-112">Un `IIdentity` oggetto può essere ottenuto chiamando il metodo [CreateEvidence](icorruntimehost-createevidence-method.md) .</span><span class="sxs-lookup"><span data-stu-id="72972-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="72972-113">out Puntatore a un'interfaccia di tipo <xref:System._AppDomain> a un'istanza di <xref:System.AppDomain?displayProperty=nameWithType> che può essere utilizzata per controllare ulteriormente il dominio.</span><span class="sxs-lookup"><span data-stu-id="72972-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72972-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="72972-114">Return Value</span></span>  
  
|<span data-ttu-id="72972-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72972-115">HRESULT</span></span>|<span data-ttu-id="72972-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72972-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72972-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="72972-117">S_OK</span></span>|<span data-ttu-id="72972-118">L'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="72972-118">The operation was successful.</span></span>|  
|<span data-ttu-id="72972-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="72972-119">S_FALSE</span></span>|<span data-ttu-id="72972-120">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="72972-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="72972-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="72972-121">E_FAIL</span></span>|<span data-ttu-id="72972-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="72972-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="72972-123">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="72972-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="72972-124">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="72972-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="72972-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="72972-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="72972-126">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="72972-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72972-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="72972-127">Remarks</span></span>  
 <span data-ttu-id="72972-128">`CreateDomainEx`estende le funzionalità di [CreateDomain](icorruntimehost-createdomain-method.md) consentendo al chiamante di passare un' `IAppDomainSetup` istanza di con i valori delle proprietà per la configurazione del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="72972-128">`CreateDomainEx` extends the capabilities of [CreateDomain](icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72972-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72972-129">Requirements</span></span>  
 <span data-ttu-id="72972-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72972-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72972-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="72972-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72972-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="72972-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72972-133">**Versione .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="72972-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72972-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72972-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="72972-135">Metodo CreateDomain</span><span class="sxs-lookup"><span data-stu-id="72972-135">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="72972-136">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="72972-136">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
