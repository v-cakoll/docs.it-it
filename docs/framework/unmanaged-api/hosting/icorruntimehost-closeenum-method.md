---
title: Metodo ICorRuntimeHost::CloseEnum
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bfddd1d8f6fed105224cb2294d68f3f0bc016403
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762159"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="73987-102">Metodo ICorRuntimeHost::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="73987-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="73987-103">Reimposta un enumeratore di dominio fino all'inizio dell'elenco dei domini.</span><span class="sxs-lookup"><span data-stu-id="73987-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73987-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73987-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73987-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="73987-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="73987-106">[in] L'enumeratore reimpostare.</span><span class="sxs-lookup"><span data-stu-id="73987-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73987-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="73987-107">Return Value</span></span>  
  
|<span data-ttu-id="73987-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73987-108">HRESULT</span></span>|<span data-ttu-id="73987-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73987-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73987-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="73987-110">S_OK</span></span>|<span data-ttu-id="73987-111">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="73987-111">The operation was successful.</span></span>|  
|<span data-ttu-id="73987-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="73987-112">S_FALSE</span></span>|<span data-ttu-id="73987-113">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="73987-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="73987-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73987-114">E_FAIL</span></span>|<span data-ttu-id="73987-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="73987-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="73987-116">Se un metodo viene restituito E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="73987-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="73987-117">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="73987-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="73987-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73987-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73987-119">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="73987-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73987-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73987-120">Requirements</span></span>  
 <span data-ttu-id="73987-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73987-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73987-122">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="73987-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73987-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="73987-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73987-124">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="73987-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73987-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73987-125">See also</span></span>

- [<span data-ttu-id="73987-126">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="73987-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="73987-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="73987-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
