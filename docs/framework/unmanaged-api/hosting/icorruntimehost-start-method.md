---
title: Metodo ICorRuntimeHost::Start
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: c450d83669a3bc548c15ed5800dc73438b9a84a6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127686"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="28381-102">Metodo ICorRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="28381-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="28381-103">Avvia il Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="28381-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28381-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28381-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="28381-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="28381-105">Return Value</span></span>  
  
|<span data-ttu-id="28381-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28381-106">HRESULT</span></span>|<span data-ttu-id="28381-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28381-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28381-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="28381-108">S_OK</span></span>|<span data-ttu-id="28381-109">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="28381-109">The operation was successful.</span></span>|  
|<span data-ttu-id="28381-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="28381-110">S_FALSE</span></span>|<span data-ttu-id="28381-111">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="28381-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="28381-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="28381-112">E_FAIL</span></span>|<span data-ttu-id="28381-113">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="28381-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="28381-114">Se un metodo restituisce E_FAIL, il CLR non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="28381-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="28381-115">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="28381-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="28381-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="28381-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="28381-117">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="28381-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28381-118">Note</span><span class="sxs-lookup"><span data-stu-id="28381-118">Remarks</span></span>  
 <span data-ttu-id="28381-119">In genere non è necessario chiamare il metodo `Start`, perché CLR viene avviato automaticamente alla prima richiesta di esecuzione del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="28381-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28381-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28381-120">Requirements</span></span>  
 <span data-ttu-id="28381-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28381-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28381-122">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="28381-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28381-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="28381-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28381-124">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="28381-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28381-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28381-125">See also</span></span>

- [<span data-ttu-id="28381-126">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="28381-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
