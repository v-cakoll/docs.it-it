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
ms.openlocfilehash: bf19d322d8e4d0d05993d22b2aa7e46bda7b5a1d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780071"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="0d63f-102">Metodo ICorRuntimeHost::NextDomain</span><span class="sxs-lookup"><span data-stu-id="0d63f-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="0d63f-103">Ottiene un puntatore di interfaccia al dominio successivo nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0d63f-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d63f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d63f-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d63f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d63f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="0d63f-106">[in] Enumeratore che è stata ottenuta tramite una chiamata a [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="0d63f-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="0d63f-107">[out] Un puntatore a interfaccia per il <xref:System._AppDomain?displayProperty=nameWithType> tipo che rappresenta il dominio successivo nell'enumerazione oppure null se non esistono altri domini.</span><span class="sxs-lookup"><span data-stu-id="0d63f-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d63f-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0d63f-108">Return Value</span></span>  
  
|<span data-ttu-id="0d63f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d63f-109">HRESULT</span></span>|<span data-ttu-id="0d63f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d63f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d63f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d63f-111">S_OK</span></span>|<span data-ttu-id="0d63f-112">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0d63f-112">The operation was successful.</span></span>|  
|<span data-ttu-id="0d63f-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0d63f-113">S_FALSE</span></span>|<span data-ttu-id="0d63f-114">L'operazione non è stato completato o non sono presenti più domini nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0d63f-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="0d63f-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d63f-115">E_FAIL</span></span>|<span data-ttu-id="0d63f-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0d63f-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="0d63f-117">Se un metodo viene restituito E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="0d63f-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="0d63f-118">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0d63f-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0d63f-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d63f-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d63f-120">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d63f-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d63f-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d63f-121">Requirements</span></span>  
 <span data-ttu-id="0d63f-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d63f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d63f-123">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d63f-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d63f-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0d63f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d63f-125">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="0d63f-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d63f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d63f-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="0d63f-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0d63f-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
