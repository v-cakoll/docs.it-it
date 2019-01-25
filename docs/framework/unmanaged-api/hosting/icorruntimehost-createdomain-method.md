---
title: Metodo ICorRuntimeHost::CreateDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf0a29222e8f5dfcfbbdfabc6c64d43e2e6a943a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694880"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="6c43f-102">Metodo ICorRuntimeHost::CreateDomain</span><span class="sxs-lookup"><span data-stu-id="6c43f-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="6c43f-103">Crea un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6c43f-103">Creates an application domain.</span></span> <span data-ttu-id="6c43f-104">Il chiamante riceve un puntatore a interfaccia typu <xref:System._AppDomain> a un'istanza del tipo <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6c43f-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c43f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c43f-105">Syntax</span></span>  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c43f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c43f-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="6c43f-107">[in] Un parametro facoltativo utilizzato per assegnare un nome descrittivo per il dominio.</span><span class="sxs-lookup"><span data-stu-id="6c43f-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="6c43f-108">Questo nome descrittivo può essere visualizzato nelle interfacce utente, ad esempio ai debugger di identificare il dominio.</span><span class="sxs-lookup"><span data-stu-id="6c43f-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="6c43f-109">[in] Matrice facoltativa di puntatori a `IIdentity` istanze che rappresentano un'evidenza mappata tramite criteri di sicurezza per stabilire un set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="6c43f-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="6c43f-110">Un' `IIdentity` oggetto può essere ottenuto chiamando il [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="6c43f-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="6c43f-111">[out] Un puntatore a interfaccia typu <xref:System._AppDomain> a un'istanza di <xref:System.AppDomain?displayProperty=nameWithType> che può essere utilizzato per controllare ulteriormente il dominio.</span><span class="sxs-lookup"><span data-stu-id="6c43f-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c43f-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6c43f-112">Return Value</span></span>  
  
|<span data-ttu-id="6c43f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c43f-113">HRESULT</span></span>|<span data-ttu-id="6c43f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c43f-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c43f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c43f-115">S_OK</span></span>|<span data-ttu-id="6c43f-116">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="6c43f-116">The operation was successful.</span></span>|  
|<span data-ttu-id="6c43f-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6c43f-117">S_FALSE</span></span>|<span data-ttu-id="6c43f-118">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="6c43f-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="6c43f-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6c43f-119">E_FAIL</span></span>|<span data-ttu-id="6c43f-120">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6c43f-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6c43f-121">Se un metodo viene restituito E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="6c43f-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="6c43f-122">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6c43f-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6c43f-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6c43f-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6c43f-124">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6c43f-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c43f-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c43f-125">Requirements</span></span>  
 <span data-ttu-id="6c43f-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c43f-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c43f-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c43f-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c43f-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6c43f-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c43f-129">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6c43f-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c43f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c43f-130">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="6c43f-131">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6c43f-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
