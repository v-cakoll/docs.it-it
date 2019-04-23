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
ms.openlocfilehash: 2c3ff0c91713a6bb7449791bae6a754c43659335
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225274"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="bc25a-102">Metodo ICorRuntimeHost::NextDomain</span><span class="sxs-lookup"><span data-stu-id="bc25a-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="bc25a-103">Ottiene un puntatore di interfaccia al dominio successivo nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bc25a-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc25a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc25a-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc25a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bc25a-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="bc25a-106">[in] Enumeratore che è stata ottenuta tramite una chiamata a [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="bc25a-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="bc25a-107">[out] Un puntatore a interfaccia per il <xref:System._AppDomain?displayProperty=nameWithType> tipo che rappresenta il dominio successivo nell'enumerazione oppure null se non esistono altri domini.</span><span class="sxs-lookup"><span data-stu-id="bc25a-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc25a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bc25a-108">Return Value</span></span>  
  
|<span data-ttu-id="bc25a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc25a-109">HRESULT</span></span>|<span data-ttu-id="bc25a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc25a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc25a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc25a-111">S_OK</span></span>|<span data-ttu-id="bc25a-112">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="bc25a-112">The operation was successful.</span></span>|  
|<span data-ttu-id="bc25a-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="bc25a-113">S_FALSE</span></span>|<span data-ttu-id="bc25a-114">L'operazione non è stato completato o non sono presenti più domini nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bc25a-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="bc25a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bc25a-115">E_FAIL</span></span>|<span data-ttu-id="bc25a-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="bc25a-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="bc25a-117">Se un metodo viene restituito E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="bc25a-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="bc25a-118">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bc25a-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bc25a-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bc25a-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bc25a-120">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bc25a-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc25a-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bc25a-121">Requirements</span></span>  
 <span data-ttu-id="bc25a-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc25a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc25a-123">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bc25a-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc25a-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bc25a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc25a-125">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="bc25a-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc25a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc25a-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="bc25a-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="bc25a-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
