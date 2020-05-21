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
ms.openlocfilehash: 079164d15141983711e976e0209cc22c818d9cd9
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760420"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="ee41c-102">Metodo ICorRuntimeHost::NextDomain</span><span class="sxs-lookup"><span data-stu-id="ee41c-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="ee41c-103">Ottiene un puntatore a interfaccia al dominio successivo nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ee41c-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee41c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee41c-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee41c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee41c-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ee41c-106">in Enumeratore ottenuto tramite una chiamata a [EnumDomains](icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="ee41c-106">[in] The enumerator that was obtained through a call to [EnumDomains](icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="ee41c-107">out Puntatore di interfaccia al <xref:System._AppDomain?displayProperty=nameWithType> tipo che rappresenta il dominio successivo nell'enumerazione, o null, se non esistono altri domini.</span><span class="sxs-lookup"><span data-stu-id="ee41c-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee41c-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ee41c-108">Return Value</span></span>  
  
|<span data-ttu-id="ee41c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee41c-109">HRESULT</span></span>|<span data-ttu-id="ee41c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee41c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee41c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee41c-111">S_OK</span></span>|<span data-ttu-id="ee41c-112">L'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ee41c-112">The operation was successful.</span></span>|  
|<span data-ttu-id="ee41c-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ee41c-113">S_FALSE</span></span>|<span data-ttu-id="ee41c-114">Non è stato possibile completare l'operazione oppure non sono presenti altri domini nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ee41c-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="ee41c-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ee41c-115">E_FAIL</span></span>|<span data-ttu-id="ee41c-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ee41c-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ee41c-117">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="ee41c-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="ee41c-118">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ee41c-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ee41c-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ee41c-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ee41c-120">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ee41c-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee41c-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee41c-121">Requirements</span></span>  
 <span data-ttu-id="ee41c-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee41c-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee41c-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ee41c-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee41c-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee41c-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee41c-125">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="ee41c-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee41c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee41c-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="ee41c-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ee41c-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
