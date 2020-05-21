---
title: Metodo ICorRuntimeHost::Stop
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
ms.openlocfilehash: 4117c1297f02032fda80520a7709833217ec94b1
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762695"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="e1ad8-102">Metodo ICorRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="e1ad8-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="e1ad8-103">Arresta l'esecuzione del codice nel runtime per il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="e1ad8-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1ad8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1ad8-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e1ad8-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1ad8-105">Return Value</span></span>  
  
|<span data-ttu-id="e1ad8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1ad8-106">HRESULT</span></span>|<span data-ttu-id="e1ad8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1ad8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1ad8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1ad8-108">S_OK</span></span>|<span data-ttu-id="e1ad8-109">L'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e1ad8-109">The operation was successful.</span></span>|  
|<span data-ttu-id="e1ad8-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e1ad8-110">S_FALSE</span></span>|<span data-ttu-id="e1ad8-111">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e1ad8-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e1ad8-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1ad8-112">E_FAIL</span></span>|<span data-ttu-id="e1ad8-113">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e1ad8-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e1ad8-114">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="e1ad8-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e1ad8-115">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e1ad8-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e1ad8-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e1ad8-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e1ad8-117">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e1ad8-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1ad8-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e1ad8-118">Remarks</span></span>  
 <span data-ttu-id="e1ad8-119">In genere non è necessario chiamare il `Stop` metodo, perché l'esecuzione del codice viene arrestata quando il processo viene terminato.</span><span class="sxs-lookup"><span data-stu-id="e1ad8-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1ad8-120">Dopo una chiamata a `Stop` , il CLR non può essere reinizializzato nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="e1ad8-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1ad8-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1ad8-121">Requirements</span></span>  
 <span data-ttu-id="e1ad8-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1ad8-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1ad8-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e1ad8-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1ad8-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e1ad8-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1ad8-125">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e1ad8-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ad8-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1ad8-126">See also</span></span>

- [<span data-ttu-id="e1ad8-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e1ad8-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
