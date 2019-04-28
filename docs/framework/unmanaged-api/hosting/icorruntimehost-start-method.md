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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e6521f8013bf92f073ab4b6808871c95ac2802b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700111"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="23875-102">Metodo ICorRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="23875-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="23875-103">Avvia common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="23875-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23875-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23875-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="23875-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="23875-105">Return Value</span></span>  
  
|<span data-ttu-id="23875-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23875-106">HRESULT</span></span>|<span data-ttu-id="23875-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23875-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23875-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="23875-108">S_OK</span></span>|<span data-ttu-id="23875-109">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="23875-109">The operation was successful.</span></span>|  
|<span data-ttu-id="23875-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="23875-110">S_FALSE</span></span>|<span data-ttu-id="23875-111">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="23875-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="23875-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23875-112">E_FAIL</span></span>|<span data-ttu-id="23875-113">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="23875-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="23875-114">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="23875-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="23875-115">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="23875-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="23875-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23875-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23875-117">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="23875-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23875-118">Note</span><span class="sxs-lookup"><span data-stu-id="23875-118">Remarks</span></span>  
 <span data-ttu-id="23875-119">In genere non è necessario chiamare il `Start` metodo, perché Common Language Runtime viene avviato automaticamente alla prima richiesta per eseguire codice gestito.</span><span class="sxs-lookup"><span data-stu-id="23875-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23875-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23875-120">Requirements</span></span>  
 <span data-ttu-id="23875-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23875-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23875-122">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23875-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23875-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="23875-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23875-124">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="23875-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23875-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23875-125">See also</span></span>

- [<span data-ttu-id="23875-126">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="23875-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
