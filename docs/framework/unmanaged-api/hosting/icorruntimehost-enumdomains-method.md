---
title: Metodo ICorRuntimeHost::EnumDomains
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e4db2330c6d46610bbb3da8b732b1c098659c97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729080"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="572a4-102">Metodo ICorRuntimeHost::EnumDomains</span><span class="sxs-lookup"><span data-stu-id="572a4-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="572a4-103">Ottiene un enumeratore per i domini nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="572a4-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="572a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="572a4-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="572a4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="572a4-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="572a4-106">[out] Enumeratore per i domini.</span><span class="sxs-lookup"><span data-stu-id="572a4-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="572a4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="572a4-107">Return Value</span></span>  
  
|<span data-ttu-id="572a4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="572a4-108">HRESULT</span></span>|<span data-ttu-id="572a4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="572a4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="572a4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="572a4-110">S_OK</span></span>|<span data-ttu-id="572a4-111">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="572a4-111">The operation was successful.</span></span>|  
|<span data-ttu-id="572a4-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="572a4-112">S_FALSE</span></span>|<span data-ttu-id="572a4-113">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="572a4-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="572a4-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="572a4-114">E_FAIL</span></span>|<span data-ttu-id="572a4-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="572a4-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="572a4-116">Se un metodo viene restituito E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="572a4-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="572a4-117">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="572a4-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="572a4-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="572a4-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="572a4-119">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="572a4-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="572a4-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="572a4-120">Requirements</span></span>  
 <span data-ttu-id="572a4-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="572a4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="572a4-122">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="572a4-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="572a4-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="572a4-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="572a4-124">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="572a4-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="572a4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="572a4-125">See also</span></span>
- [<span data-ttu-id="572a4-126">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="572a4-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
