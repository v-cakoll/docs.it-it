---
title: Metodo ICorRuntimeHost::UnloadDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 492a60d3c8d18bec4e99ae778686fec6e8724248
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700241"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="32a78-102">Metodo ICorRuntimeHost::UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="32a78-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="32a78-103">Scarica il dominio applicazione specificato dal processo corrente.</span><span class="sxs-lookup"><span data-stu-id="32a78-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32a78-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32a78-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32a78-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="32a78-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="32a78-106">[in] Un puntatore di tipo <xref:System._AppDomain?displayProperty=nameWithType> che rappresenta il dominio per essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="32a78-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32a78-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="32a78-107">Return Value</span></span>  
  
|<span data-ttu-id="32a78-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32a78-108">HRESULT</span></span>|<span data-ttu-id="32a78-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32a78-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32a78-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="32a78-110">S_OK</span></span>|<span data-ttu-id="32a78-111">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="32a78-111">The operation was successful.</span></span>|  
|<span data-ttu-id="32a78-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="32a78-112">S_FALSE</span></span>|<span data-ttu-id="32a78-113">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="32a78-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="32a78-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32a78-114">E_FAIL</span></span>|<span data-ttu-id="32a78-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="32a78-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="32a78-116">Se un metodo viene restituito E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="32a78-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="32a78-117">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="32a78-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="32a78-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32a78-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32a78-119">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="32a78-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32a78-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32a78-120">Requirements</span></span>  
 <span data-ttu-id="32a78-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32a78-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32a78-122">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32a78-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32a78-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="32a78-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32a78-124">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="32a78-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32a78-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32a78-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="32a78-126">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="32a78-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
