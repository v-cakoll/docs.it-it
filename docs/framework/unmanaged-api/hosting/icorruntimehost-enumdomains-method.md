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
ms.openlocfilehash: a97471e1c257902633b7eb363c3cc51288c70917
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762253"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="b8285-102">Metodo ICorRuntimeHost::EnumDomains</span><span class="sxs-lookup"><span data-stu-id="b8285-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="b8285-103">Ottiene un enumeratore per i domini nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="b8285-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8285-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8285-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8285-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8285-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b8285-106">out Enumeratore per i domini.</span><span class="sxs-lookup"><span data-stu-id="b8285-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8285-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b8285-107">Return Value</span></span>  
  
|<span data-ttu-id="b8285-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8285-108">HRESULT</span></span>|<span data-ttu-id="b8285-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8285-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8285-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8285-110">S_OK</span></span>|<span data-ttu-id="b8285-111">L'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b8285-111">The operation was successful.</span></span>|  
|<span data-ttu-id="b8285-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b8285-112">S_FALSE</span></span>|<span data-ttu-id="b8285-113">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="b8285-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b8285-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8285-114">E_FAIL</span></span>|<span data-ttu-id="b8285-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b8285-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b8285-116">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="b8285-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b8285-117">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b8285-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b8285-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b8285-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b8285-119">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b8285-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8285-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8285-120">Requirements</span></span>  
 <span data-ttu-id="b8285-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8285-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8285-122">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b8285-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8285-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b8285-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8285-124">**Versione .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="b8285-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8285-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8285-125">See also</span></span>

- [<span data-ttu-id="b8285-126">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b8285-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
