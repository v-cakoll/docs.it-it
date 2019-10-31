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
ms.openlocfilehash: e2eddfab68e5c9e2ebffe2c96c9348f3cd799c7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127758"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="cc5fd-102">Metodo ICorRuntimeHost::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="cc5fd-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="cc5fd-103">Reimposta un enumeratore di dominio all'inizio dell'elenco di domini.</span><span class="sxs-lookup"><span data-stu-id="cc5fd-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc5fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc5fd-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc5fd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc5fd-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="cc5fd-106">in Enumeratore da reimpostare.</span><span class="sxs-lookup"><span data-stu-id="cc5fd-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc5fd-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cc5fd-107">Return Value</span></span>  
  
|<span data-ttu-id="cc5fd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc5fd-108">HRESULT</span></span>|<span data-ttu-id="cc5fd-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc5fd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc5fd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc5fd-110">S_OK</span></span>|<span data-ttu-id="cc5fd-111">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="cc5fd-111">The operation was successful.</span></span>|  
|<span data-ttu-id="cc5fd-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="cc5fd-112">S_FALSE</span></span>|<span data-ttu-id="cc5fd-113">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="cc5fd-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="cc5fd-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc5fd-114">E_FAIL</span></span>|<span data-ttu-id="cc5fd-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="cc5fd-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="cc5fd-116">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="cc5fd-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="cc5fd-117">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cc5fd-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cc5fd-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cc5fd-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cc5fd-119">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="cc5fd-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc5fd-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc5fd-120">Requirements</span></span>  
 <span data-ttu-id="cc5fd-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc5fd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc5fd-122">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cc5fd-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc5fd-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cc5fd-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc5fd-124">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="cc5fd-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc5fd-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc5fd-125">See also</span></span>

- [<span data-ttu-id="cc5fd-126">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="cc5fd-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="cc5fd-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="cc5fd-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
