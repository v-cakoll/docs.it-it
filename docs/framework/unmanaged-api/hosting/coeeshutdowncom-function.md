---
title: Funzione CoEEShutDownCOM
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74548df512f68761b006e064a6db968e82b03813
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779127"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="13754-102">Funzione CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="13754-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="13754-103">Forza common language runtime (CLR) per rilasciare tutti i puntatori di interfaccia che vengono mantenuti all'interno di runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="13754-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="13754-104">Questo ha l'effetto di rilascio di tutte le cache RCW.</span><span class="sxs-lookup"><span data-stu-id="13754-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="13754-105">Questa funzione globale è obsoleta in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="13754-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="13754-106">Usare invece il punto di ingresso per un runtime specifico.</span><span class="sxs-lookup"><span data-stu-id="13754-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13754-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13754-107">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="13754-108">Note</span><span class="sxs-lookup"><span data-stu-id="13754-108">Remarks</span></span>  
 <span data-ttu-id="13754-109">Il `CoEEShutDownCOM` funzione prima di tutto rilascia tutti i RCW in tutti i contesti e in tutte le cache e quindi rimuove qualsiasi notifica di chiusura esistente nel programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="13754-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="13754-110">Non lo scaricamento di DLL si verifica.</span><span class="sxs-lookup"><span data-stu-id="13754-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="13754-111">Questa funzione influisce su tutti i runtime caricati nel processo.</span><span class="sxs-lookup"><span data-stu-id="13754-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="13754-112">A partire da .NET Framework 4, chiamare il punto di ingresso per questa funzione runtime specifico che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="13754-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="13754-113">Per ottenere il punto di ingresso, chiamare il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) (metodo) e specificare "CoEEShutDownCOM".</span><span class="sxs-lookup"><span data-stu-id="13754-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13754-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13754-114">Requirements</span></span>  
 <span data-ttu-id="13754-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13754-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13754-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="13754-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13754-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="13754-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13754-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13754-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13754-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13754-119">See also</span></span>

- [<span data-ttu-id="13754-120">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="13754-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
