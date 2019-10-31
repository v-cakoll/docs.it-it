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
ms.openlocfilehash: 5fcf8bc861b2ef0b8ea9f5a5e46585564cc26615
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127708"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="9ea02-102">Metodo ICorRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="9ea02-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="9ea02-103">Arresta l'esecuzione del codice nel runtime per il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="9ea02-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ea02-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9ea02-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9ea02-105">Return Value</span></span>  
  
|<span data-ttu-id="9ea02-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ea02-106">HRESULT</span></span>|<span data-ttu-id="9ea02-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ea02-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ea02-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ea02-108">S_OK</span></span>|<span data-ttu-id="9ea02-109">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="9ea02-109">The operation was successful.</span></span>|  
|<span data-ttu-id="9ea02-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9ea02-110">S_FALSE</span></span>|<span data-ttu-id="9ea02-111">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="9ea02-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="9ea02-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ea02-112">E_FAIL</span></span>|<span data-ttu-id="9ea02-113">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9ea02-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="9ea02-114">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="9ea02-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="9ea02-115">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9ea02-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9ea02-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ea02-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ea02-117">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9ea02-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ea02-118">Note</span><span class="sxs-lookup"><span data-stu-id="9ea02-118">Remarks</span></span>  
 <span data-ttu-id="9ea02-119">In genere non è necessario chiamare il metodo `Stop`, perché l'esecuzione del codice viene arrestata alla chiusura del processo.</span><span class="sxs-lookup"><span data-stu-id="9ea02-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ea02-120">Dopo una chiamata a `Stop`, il CLR non può essere reinizializzato nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="9ea02-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea02-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9ea02-121">Requirements</span></span>  
 <span data-ttu-id="9ea02-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ea02-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ea02-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9ea02-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ea02-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9ea02-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ea02-125">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="9ea02-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea02-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ea02-126">See also</span></span>

- [<span data-ttu-id="9ea02-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9ea02-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
