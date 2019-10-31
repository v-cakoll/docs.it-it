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
ms.openlocfilehash: dfdcb9b8aedeb3ccbbd27864e79ce43338942922
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133354"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="53606-102">Metodo ICorRuntimeHost::UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="53606-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="53606-103">Scarica il dominio applicazione specificato dal processo corrente.</span><span class="sxs-lookup"><span data-stu-id="53606-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53606-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53606-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53606-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="53606-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="53606-106">in Puntatore di tipo <xref:System._AppDomain?displayProperty=nameWithType> che rappresenta il dominio da scaricare.</span><span class="sxs-lookup"><span data-stu-id="53606-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53606-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="53606-107">Return Value</span></span>  
  
|<span data-ttu-id="53606-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53606-108">HRESULT</span></span>|<span data-ttu-id="53606-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53606-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53606-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="53606-110">S_OK</span></span>|<span data-ttu-id="53606-111">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="53606-111">The operation was successful.</span></span>|  
|<span data-ttu-id="53606-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="53606-112">S_FALSE</span></span>|<span data-ttu-id="53606-113">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="53606-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="53606-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53606-114">E_FAIL</span></span>|<span data-ttu-id="53606-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="53606-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="53606-116">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="53606-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="53606-117">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="53606-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="53606-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="53606-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="53606-119">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="53606-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53606-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53606-120">Requirements</span></span>  
 <span data-ttu-id="53606-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53606-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53606-122">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="53606-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53606-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="53606-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53606-124">**Versione .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="53606-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53606-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53606-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="53606-126">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="53606-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
