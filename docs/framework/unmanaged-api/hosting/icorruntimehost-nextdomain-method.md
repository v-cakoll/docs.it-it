---
title: Metodo ICorRuntimeHost::NextDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abb2e2902737749fd9dc1f148a340e28da772e59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439020"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="74d29-102">Metodo ICorRuntimeHost::NextDomain</span><span class="sxs-lookup"><span data-stu-id="74d29-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="74d29-103">Ottiene un puntatore a interfaccia per il dominio successivo nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="74d29-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d29-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74d29-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74d29-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74d29-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="74d29-106">[in] Enumeratore che è stato ottenuto tramite una chiamata a [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="74d29-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="74d29-107">[out] Un puntatore a interfaccia per il <xref:System._AppDomain?displayProperty=nameWithType> tipo che rappresenta il dominio successivo nell'enumerazione oppure null se non esistono altri domini.</span><span class="sxs-lookup"><span data-stu-id="74d29-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74d29-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="74d29-108">Return Value</span></span>  
  
|<span data-ttu-id="74d29-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74d29-109">HRESULT</span></span>|<span data-ttu-id="74d29-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74d29-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74d29-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="74d29-111">S_OK</span></span>|<span data-ttu-id="74d29-112">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="74d29-112">The operation was successful.</span></span>|  
|<span data-ttu-id="74d29-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="74d29-113">S_FALSE</span></span>|<span data-ttu-id="74d29-114">Impossibile completare l'operazione oppure non sono presenti più domini nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="74d29-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="74d29-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74d29-115">E_FAIL</span></span>|<span data-ttu-id="74d29-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="74d29-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="74d29-117">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="74d29-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="74d29-118">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="74d29-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="74d29-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74d29-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74d29-120">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="74d29-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74d29-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74d29-121">Requirements</span></span>  
 <span data-ttu-id="74d29-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74d29-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74d29-123">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="74d29-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74d29-124">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="74d29-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74d29-125">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="74d29-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d29-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74d29-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="74d29-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="74d29-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
